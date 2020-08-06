---
title: 'Tutorial: Crear un informe de forma libre (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 87288b59-faf2-4b1d-a8e4-a7582baedf2f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 515b0d2566efa4e11216a28648338c7ec43f3950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748609"
---
# <a name="tutorial-creating-a-free-form-report-report-builder"></a><span data-ttu-id="25087-102">Tutorial: Crear un informe de forma libre (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="25087-102">Tutorial: Creating a Free Form Report (Report Builder)</span></span>
  <span data-ttu-id="25087-103">Este tutorial le enseña a crear un informe de forma libre de SSRS que se asemeja a una carta de formularios.</span><span class="sxs-lookup"><span data-stu-id="25087-103">This tutorial teaches you how to create an SSRS free form report that resembles a forms letter.</span></span> <span data-ttu-id="25087-104">Puede organizar los elementos de informe para crear un formulario con cuadros de texto, imágenes y otras regiones de datos.</span><span class="sxs-lookup"><span data-stu-id="25087-104">You can arrange report items to create a form with text boxes, images and other data regions.</span></span>

 <span data-ttu-id="25087-105">El informe que creará en este tutorial se basa en los datos de ventas de ejemplo que se incluyen en el tutorial.</span><span class="sxs-lookup"><span data-stu-id="25087-105">The report you create in this tutorial is based on sample sales data that is included in the tutorial.</span></span> <span data-ttu-id="25087-106">El informe agrupa la información por territorio y muestra el nombre del administrador de ventas del territorio, así como una información de ventas detallada y sumaria.</span><span class="sxs-lookup"><span data-stu-id="25087-106">The report groups information by territory and displays the name of the sales manager for the territory as well as detailed and summary sales information.</span></span> <span data-ttu-id="25087-107">Utilizará la región de datos de la lista como la base para el informe de la forma libre y, a continuación, agregará un panel decorativo con una imagen, texto estático con datos insertados, una tabla para mostrar información detallada y, opcionalmente, gráficos circulares y de columnas que muestren la información resumida.</span><span class="sxs-lookup"><span data-stu-id="25087-107">You will use the list data region as the foundation for the free form report, and then add a decorative panel with an image, static text with data inserted, a table to show detailed information, and optionally, pie and column charts to display summary information.</span></span>

##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="25087-108">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="25087-108">What You Will Learn</span></span>
 <span data-ttu-id="25087-109">En este tutorial, aprenderá a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="25087-109">In this tutorial, you will learn how to do the following:</span></span>

-   [<span data-ttu-id="25087-110">Crear un informe en blanco, un origen de datos y un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="25087-110">Create a Blank Report, Data Source, and Dataset</span></span>](#BlankReport)

-   [<span data-ttu-id="25087-111">Agregar y configurar una lista</span><span class="sxs-lookup"><span data-stu-id="25087-111">Add and Configure a List</span></span>](#List)

-   [<span data-ttu-id="25087-112">Agregar gráficos</span><span class="sxs-lookup"><span data-stu-id="25087-112">Add Graphics</span></span>](#Graphics)

-   [<span data-ttu-id="25087-113">Agregar texto en forma libre</span><span class="sxs-lookup"><span data-stu-id="25087-113">Add Free Form Text</span></span>](#Text)

-   [<span data-ttu-id="25087-114">Agregar una tabla para mostrar detalles</span><span class="sxs-lookup"><span data-stu-id="25087-114">Add a Table to Show Details</span></span>](#Table)

-   [<span data-ttu-id="25087-115">Dar formato a datos</span><span class="sxs-lookup"><span data-stu-id="25087-115">Format Data</span></span>](#Format)

-   [<span data-ttu-id="25087-116">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="25087-116">Save the Report</span></span>](#Save)

### <a name="other-optional-steps"></a><span data-ttu-id="25087-117">Otros pasos opcionales</span><span class="sxs-lookup"><span data-stu-id="25087-117">Other Optional Steps</span></span>

-   [<span data-ttu-id="25087-118">Agregar una línea para separar áreas de informe</span><span class="sxs-lookup"><span data-stu-id="25087-118">Add a Line to Separate Areas of Report</span></span>](#Line)

-   [<span data-ttu-id="25087-119">Agregar visualización de datos resumidos</span><span class="sxs-lookup"><span data-stu-id="25087-119">Add Summary Data Visualization</span></span>](#Visualization)

 <span data-ttu-id="25087-120">Tiempo estimado para completar este tutorial: 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="25087-120">Estimated time to complete this tutorial: 20 minutes.</span></span>

## <a name="requirements"></a><span data-ttu-id="25087-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25087-121">Requirements</span></span>
 <span data-ttu-id="25087-122">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="25087-122">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>

##  <a name="1-create-a-blank-report-data-source-and-dataset"></a><a name="BlankReport"></a><span data-ttu-id="25087-123">1. crear un informe en blanco, un origen de datos y un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="25087-123">1. Create a Blank Report, Data Source, and Dataset</span></span>

> [!NOTE]
>  <span data-ttu-id="25087-124">En este tutorial, la consulta contiene los valores de los datos, de forma que el informe no necesite un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="25087-124">In this tutorial, the query contains the data values so that the report does not need an external data source.</span></span> <span data-ttu-id="25087-125">Es muy útil usar este tipo de datos internos para el aprendizaje, pero el método hace que la consulta sea larga.</span><span class="sxs-lookup"><span data-stu-id="25087-125">The use of this type of internal data is great for learning purposes, but the approach makes the query long.</span></span> <span data-ttu-id="25087-126">.</span><span class="sxs-lookup"><span data-stu-id="25087-126">.</span></span>

#### <a name="to-create-a-blank-report"></a><span data-ttu-id="25087-127">Para crear un informe en blanco</span><span class="sxs-lookup"><span data-stu-id="25087-127">To create a blank report</span></span>

1.  <span data-ttu-id="25087-128">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="25087-128">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25087-129">Debería aparecer el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="25087-129">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="25087-130">Si no hace, en el botón Generador de informes haga clic **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="25087-130">If it does not, from the Report Builder button, click **New**.</span></span>

2.  <span data-ttu-id="25087-131">En el panel izquierdo del cuadro de diálogo **Introducción** , compruebe que **Nuevo informe** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="25087-131">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>

3.  <span data-ttu-id="25087-132">En el panel derecho, haga clic en **Informe en blanco**.</span><span class="sxs-lookup"><span data-stu-id="25087-132">In the right pane, click **Blank Report**.</span></span>

#### <a name="to-create-a-new-data-source"></a><span data-ttu-id="25087-133">Para crear un nuevo vista origen de datos</span><span class="sxs-lookup"><span data-stu-id="25087-133">To create a new data source</span></span>

1.  <span data-ttu-id="25087-134">En el panel datos de informe, haga clic en **nuevo**y, a continuación, haga clic en **origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="25087-134">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>

2.  <span data-ttu-id="25087-135">En el `Name` cuadro, escriba: **ListDataSource**</span><span class="sxs-lookup"><span data-stu-id="25087-135">In the `Name` box, type: **ListDataSource**</span></span>

3.  <span data-ttu-id="25087-136">Haga clic en **Usar una conexión incrustada en mi informe**.</span><span class="sxs-lookup"><span data-stu-id="25087-136">Click **Use a connection embedded in my report**.</span></span>

4.  <span data-ttu-id="25087-137">Compruebe que el tipo de conexión es Microsoft SQL Server y, a continuación, en el cuadro **cadena de conexión** , escriba: \*\*origen de datos = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="25087-137">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>

     <span data-ttu-id="25087-138">\<servername>, por ejemplo Report001, especifica un equipo en el que se ha instalado una instancia del SQL Server Motor de base de datos.</span><span class="sxs-lookup"><span data-stu-id="25087-138">\<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="25087-139">Dado que los datos del informe no se extraen de una base de datos de SQL Server, no necesita incluir el nombre de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="25087-139">Because the report data is not extracted from a SQL Server database, you need not include the name of a database.</span></span> <span data-ttu-id="25087-140">Para analizar la consulta se utiliza la base de datos predeterminada en el servidor especificado.</span><span class="sxs-lookup"><span data-stu-id="25087-140">The default database on the specified server is used to parse the query.</span></span>

5.  <span data-ttu-id="25087-141">Haga clic en **Credenciales**e introduzca las credenciales necesarias para conectarse a la instancia del Motor de base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25087-141">Click **Credentials**, and enter the credentials needed to connect to the instance of the SQL Server Database Engine.</span></span>

6.  <span data-ttu-id="25087-142">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="25087-142">Click **OK**.</span></span>

#### <a name="to-create-a-new-dataset"></a><span data-ttu-id="25087-143">Para crear un nuevo conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="25087-143">To create a new dataset</span></span>

1.  <span data-ttu-id="25087-144">En el panel Datos de informe, haga clic en **Nuevo**y, a continuación, haga clic en **Conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="25087-144">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>

2.  <span data-ttu-id="25087-145">En el `Name` cuadro, escriba: **ListDataset.**</span><span class="sxs-lookup"><span data-stu-id="25087-145">In the `Name` box, type: **ListDataset.**</span></span>

3.  <span data-ttu-id="25087-146">Haga clic en **Usar un conjunto de datos insertado en el informe**y compruebe que el origen de datos es **ListDataSource**.</span><span class="sxs-lookup"><span data-stu-id="25087-146">Click **Use a dataset embedded in my report**, and verify that the data source is **ListDataSource**.</span></span>

4.  <span data-ttu-id="25087-147">Compruebe que el tipo de consulta **Texto** está seleccionado, y, a continuación, haga clic en **Diseñador de consultas**.</span><span class="sxs-lookup"><span data-stu-id="25087-147">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>

5.  <span data-ttu-id="25087-148">Haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="25087-148">Click **Edit as Text**.</span></span>

6.  <span data-ttu-id="25087-149">Copie y pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="25087-149">Copy and paste the following query into the query pane:</span></span>

    ```
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity
    ```

7.  <span data-ttu-id="25087-150">Haga clic en el icono Ejecutar para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="25087-150">Click Run icon to run the query.</span></span>

     <span data-ttu-id="25087-151">Los resultados de la consulta son los datos disponibles para mostrarse en su informe.</span><span class="sxs-lookup"><span data-stu-id="25087-151">The query results are the data available to display in your report.</span></span>

     <span data-ttu-id="25087-152">![Diseñador de consultas](../../2014/tutorials/media/tutorial-querydesigner.png "Diseñador de consultas")</span><span class="sxs-lookup"><span data-stu-id="25087-152">![Query Designer](../../2014/tutorials/media/tutorial-querydesigner.png "Query Designer")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="2-add-and-configure-a-list"></a><a name="List"></a><span data-ttu-id="25087-153">2. agregar y configurar una lista</span><span class="sxs-lookup"><span data-stu-id="25087-153">2. Add and Configure a List</span></span>
 [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="25087-154">proporciona tres plantillas de región de datos: tabla, matriz y lista.</span><span class="sxs-lookup"><span data-stu-id="25087-154">provides three data region templates: table, matrix, and list.</span></span> <span data-ttu-id="25087-155">Todas estas plantillas se basan en una región de datos Tablix.</span><span class="sxs-lookup"><span data-stu-id="25087-155">These templates are all based on a tablix data region.</span></span>

 <span data-ttu-id="25087-156">En este tutorial, utilizará una lista para mostrar la información de ventas de los territorios de ventas de un informe similar a un boletín.</span><span class="sxs-lookup"><span data-stu-id="25087-156">In this tutorial, you will use a list to display the sales information for sales territories in a report that resembles a newsletter.</span></span> <span data-ttu-id="25087-157">La información está agrupada por territorio.</span><span class="sxs-lookup"><span data-stu-id="25087-157">The information is grouped by territory.</span></span> <span data-ttu-id="25087-158">Agregará un nuevo grupo de filas que agrupa los datos por territorio y, a continuación, eliminará el grupo de filas de detalles integrado.</span><span class="sxs-lookup"><span data-stu-id="25087-158">You will add a new row group that groups data by territory, and then delete the built-in Details row group.</span></span> <span data-ttu-id="25087-159">La plantilla de lista es perfecta para crear informes de forma libre.</span><span class="sxs-lookup"><span data-stu-id="25087-159">The list template is ideal for creating free form reports.</span></span> <span data-ttu-id="25087-160">Para obtener más información, vea [las listas &#40;generador de informes y SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25087-160">For more information, see [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="25087-161">Este informe utiliza la Carta de tamaño del papel (8.5 X11) y márgenes de 1 pulgada.</span><span class="sxs-lookup"><span data-stu-id="25087-161">This report uses the paper size Letter (8.5 X11) and 1 inch margins.</span></span> <span data-ttu-id="25087-162">Una página de informe más alta de 9 pulgadas o más ancha de 6 1/2 pulgadas podría generar páginas en blanco.</span><span class="sxs-lookup"><span data-stu-id="25087-162">A report page taller than 9 inches or wider than 6 1/2 inches might generate blank pages.</span></span>

#### <a name="to-add-a-list"></a><span data-ttu-id="25087-163">Para agregar una lista</span><span class="sxs-lookup"><span data-stu-id="25087-163">To add a list</span></span>

1.  <span data-ttu-id="25087-164">En la pestaña **Insertar** de la cinta de opciones, en el área **Regiones de datos** , haga clic en **Lista** y, a continuación, arrastre la lista dentro del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="25087-164">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List** and then drag the list inside the report body.</span></span> <span data-ttu-id="25087-165">Haga la lista de 7 pulgadas de alto y 6,25 pulgadas de ancho.</span><span class="sxs-lookup"><span data-stu-id="25087-165">Make the list 7 inches tall and 6.25 inches wide.</span></span>

2.  <span data-ttu-id="25087-166">Haga clic dentro de la lista, haga clic con el botón secundario en la parte superior de la lista y luego haga clic en **Propiedades de Tablix**.</span><span class="sxs-lookup"><span data-stu-id="25087-166">Click inside the list, right-click the top of the list, and then click **Tablix Properties**.</span></span>

     <span data-ttu-id="25087-167">![Añadir lista](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Añadir lista")</span><span class="sxs-lookup"><span data-stu-id="25087-167">![Adding list](../../2014/tutorials/media/tutorial-addinglistwithnumbers.png "Adding list")</span></span>

3.  <span data-ttu-id="25087-168">En la lista desplegable **Nombre del conjunto de datos** , seleccione **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="25087-168">In the **Dataset name** drop-down list, select **ListDataset**.</span></span>

4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

5.  <span data-ttu-id="25087-169">Haga clic con el botón derecho dentro de la lista y luego haga clic en **Propiedades del rectángulo**.</span><span class="sxs-lookup"><span data-stu-id="25087-169">Right-click inside the list, and then click **Rectangle Properties**.</span></span>

     <span data-ttu-id="25087-170">![Comando de las propiedades del rectángulo](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Comando de las propiedades del rectángulo")</span><span class="sxs-lookup"><span data-stu-id="25087-170">![Rectangle Properties command](../../2014/tutorials/media/tutorial-rectanglepropertiescommand.png "Rectangle Properties command")</span></span>

6.  <span data-ttu-id="25087-171">En la pestaña **General** , active la casilla **Agregar un salto de página después** .</span><span class="sxs-lookup"><span data-stu-id="25087-171">On the **General** tab, select the **Add a page break after** checkbox.</span></span>

7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-new-row-group-and-to-delete-the-details-group"></a><span data-ttu-id="25087-172">Para agregar un nuevo grupo de filas y eliminar el grupo de detalles</span><span class="sxs-lookup"><span data-stu-id="25087-172">To add a new row group and to delete the Details group</span></span>

1.  <span data-ttu-id="25087-173">En el panel Grupos de filas, haga clic con el botón derecho en el grupo Detalles, seleccione **Agregar grupo**y, después, haga clic en **Grupo primario**.</span><span class="sxs-lookup"><span data-stu-id="25087-173">In the Row Groups pane, right-click the Details group, point to **Add Group**, and then click **Parent Group**.</span></span>

     <span data-ttu-id="25087-174">![Comando de grupo primario](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Comando de grupo primario")</span><span class="sxs-lookup"><span data-stu-id="25087-174">![Parent Group command](../../2014/tutorials/media/tutorial-parentgroupcommand.png "Parent Group command")</span></span>

2.  <span data-ttu-id="25087-175">En la lista desplegable, seleccione `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="25087-175">In the drop-down list, select `[Territory].`</span></span>

3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="25087-176">Se agregará una nueva columna a la lista.</span><span class="sxs-lookup"><span data-stu-id="25087-176">A column is added to the list.</span></span> <span data-ttu-id="25087-177">La columna contiene la celda `[Territory].`.</span><span class="sxs-lookup"><span data-stu-id="25087-177">The column contains the cell `[Territory].`</span></span>

4.  <span data-ttu-id="25087-178">Haga clic con el botón derecho en la columna Territory de la lista y, después, seleccione **Eliminar columnas**.</span><span class="sxs-lookup"><span data-stu-id="25087-178">Right-click the Territory column in the list, and then click **Delete Columns**.</span></span>

     <span data-ttu-id="25087-179">![Eliminar columnas](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Eliminar columnas")</span><span class="sxs-lookup"><span data-stu-id="25087-179">![Delete columns](../../2014/tutorials/media/tutorial-deletecolumnscommand.png "Delete columns")</span></span>

5.  <span data-ttu-id="25087-180">Haga clic en **Eliminar solo columnas**.</span><span class="sxs-lookup"><span data-stu-id="25087-180">Click **Delete Columns only**.</span></span>

     <span data-ttu-id="25087-181">![Eliminar columnas (cuadro de diálogo)](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Eliminar columnas, cuadro de diálogo")</span><span class="sxs-lookup"><span data-stu-id="25087-181">![Delete Columns dialog box](../../2014/tutorials/media/tutorial-deletecolumnsdialog.png "Delete Columns dialog box")</span></span>

6.  <span data-ttu-id="25087-182">En el panel Grupos de filas, haga clic con el botón secundario en el grupo **Detalles** y, luego, haga clic en **Eliminar grupo**.</span><span class="sxs-lookup"><span data-stu-id="25087-182">In the Row Groups pane, right-click the **Details** group, and then click **Delete Group**.</span></span>

     <span data-ttu-id="25087-183">![Eliminar grupo de detalles](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Eliminar grupo de detalles")</span><span class="sxs-lookup"><span data-stu-id="25087-183">![Delete Details Group](../../2014/tutorials/media/tutorial-deletedetailsgroup.png "Delete Details Group")</span></span>

7.  <span data-ttu-id="25087-184">Haga clic en **Eliminar solo el grupo**.</span><span class="sxs-lookup"><span data-stu-id="25087-184">Click **Delete Group only**.</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

##  <a name="3-add-graphics"></a><a name="Graphics"></a><span data-ttu-id="25087-185">3. agregar gráficos</span><span class="sxs-lookup"><span data-stu-id="25087-185">3. Add Graphics</span></span>
 <span data-ttu-id="25087-186">Uno de las ventajas de utilizar una región de datos de la lista es que puede agregar en cualquier parte los elementos de informe, como rectángulos y cuadros de texto, en lugar de limitarse a un diseño tabular.</span><span class="sxs-lookup"><span data-stu-id="25087-186">One of the advantages of using a list data region is that you can add report items such as rectangles and text boxes anywhere, instead of being limited to a tabular layout.</span></span> <span data-ttu-id="25087-187">Mejorará la apariencia del informe agregando un gráfico (un rectángulo relleno con un color).</span><span class="sxs-lookup"><span data-stu-id="25087-187">You will enhance the appearance of the report by adding a graphic (a rectangle filled with a color).</span></span>

#### <a name="to-add-graphic-elements-to-the-report"></a><span data-ttu-id="25087-188">Para agregar elementos gráficos al informe</span><span class="sxs-lookup"><span data-stu-id="25087-188">To add graphic elements to the report</span></span>

1.  <span data-ttu-id="25087-189">En la pestaña **Insertar** de la cinta de opciones, haga clic en **rectángulo**y, a continuación, arrastre un rectángulo hacia la esquina superior izquierda de la lista.</span><span class="sxs-lookup"><span data-stu-id="25087-189">On the **Insert** tab of the ribbon, click **Rectangle**,and then drag a rectangle to the upper left corner of the list.</span></span> <span data-ttu-id="25087-190">Haga el rectángulo de 7 pulgadas de alto y 1 de ancho.</span><span class="sxs-lookup"><span data-stu-id="25087-190">Make the rectangle 7 inches tall and 1 inch wide.</span></span>

2.  <span data-ttu-id="25087-191">Haga clic con el botón secundario en el rectángulo y, a continuación, haga clic en **Propiedades del rectángulo**.</span><span class="sxs-lookup"><span data-stu-id="25087-191">Right-click the rectangle, and then click **Rectangle Properties**.</span></span>

3.  <span data-ttu-id="25087-192">Haga clic en la pestaña **Rellenar** .</span><span class="sxs-lookup"><span data-stu-id="25087-192">Click the **Fill** tab.</span></span>

4.  <span data-ttu-id="25087-193">En la lista desplegable **Color de relleno** , haga clic en **Más colores**y, luego, seleccione el color **GrisOscuro** .</span><span class="sxs-lookup"><span data-stu-id="25087-193">In the **Fill color** drop-down list, click **More Colors**, and then select the **DarkGray** color.</span></span>

     <span data-ttu-id="25087-194">![Seleccionar el color de relleno](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Seleccionar el color de relleno")</span><span class="sxs-lookup"><span data-stu-id="25087-194">![Select fill color](../../2014/tutorials/media/tutorial-selectfillcolorwithnumbers.png "Select fill color")</span></span>

5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

6.  <span data-ttu-id="25087-195">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="25087-195">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="25087-196">La parte izquierda del informe incorpora ahora un gráfico vertical compuesto por un rectángulo gris pizarra.</span><span class="sxs-lookup"><span data-stu-id="25087-196">The left side of the report now has vertical graphic that consists of a dark gray rectangle.</span></span>

##  <a name="4-add-free-form-text"></a><a name="Text"></a><span data-ttu-id="25087-197">4. agregar texto de forma libre</span><span class="sxs-lookup"><span data-stu-id="25087-197">4. Add Free Form Text</span></span>
 <span data-ttu-id="25087-198">Un cuadro de texto contiene texto estático que se repite en cada página del informe, así como campos de datos.</span><span class="sxs-lookup"><span data-stu-id="25087-198">A text box contains static text that is repeated on each report page as well as data fields.</span></span>

#### <a name="to-add-text-to-the-report"></a><span data-ttu-id="25087-199">Para agregar texto al informe</span><span class="sxs-lookup"><span data-stu-id="25087-199">To add text to the report</span></span>

1.  <span data-ttu-id="25087-200">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="25087-200">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="25087-201">En la pestaña **Insertar** de la cinta de opciones, haga clic en **Cuadro de texto**y, después, arrastre un cuadro de texto hacia la esquina superior izquierda de la lista, pero dentro del rectángulo que agregó previamente.</span><span class="sxs-lookup"><span data-stu-id="25087-201">On the **Insert** tab of the ribbon, click **Text Box**, and then drag a text box to the upper left corner of the list, but inside of the rectangle you added previously.</span></span> <span data-ttu-id="25087-202">Haga el cuadro de texto de unas 3 pulgadas de alto y 5 de ancho.</span><span class="sxs-lookup"><span data-stu-id="25087-202">Make the text box about 3 inches tall and 5 inches wide.</span></span>

3.  <span data-ttu-id="25087-203">Coloque el cursor en la parte superior del cuadro de texto y, a continuación, escriba: **Boletín para** .</span><span class="sxs-lookup"><span data-stu-id="25087-203">Place the cursor in the upper part of the text box, and then type: **Newsletter for** .</span></span>

     <span data-ttu-id="25087-204">![Agregar un texto de encabezado del boletín](../../2014/tutorials/media/tutorial-newsletterfor.png "Agregar un texto de encabezado del boletín")</span><span class="sxs-lookup"><span data-stu-id="25087-204">![Add newsletter heading text](../../2014/tutorials/media/tutorial-newsletterfor.png "Add newsletter heading text")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25087-205">Asegúrese de incluir el espacio adicional después de la palabra "para".</span><span class="sxs-lookup"><span data-stu-id="25087-205">Be sure to include the extra space after the word "for".</span></span> <span data-ttu-id="25087-206">El espacio separa el texto y el campo que agregará en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="25087-206">The space separates the text and the field that you will add in the next step.</span></span>

4.  <span data-ttu-id="25087-207">Arrastre el campo Territory hasta el cuadro de texto y colóquelo después de que el texto que escribió en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="25087-207">Drag the Territory field to the text box and place it after the text you typed in step 3.</span></span>

     <span data-ttu-id="25087-208">![Añadir campo territorial](../../2014/tutorials/media/tutorial-addterritorialfield.png "Añadir campo territorial")</span><span class="sxs-lookup"><span data-stu-id="25087-208">![Add Territorial field](../../2014/tutorials/media/tutorial-addterritorialfield.png "Add Territorial field")</span></span>

5.  <span data-ttu-id="25087-209">Seleccione todo el texto, haga clic con el botón secundario y, a continuación, haga clic en **Propiedades de texto**.</span><span class="sxs-lookup"><span data-stu-id="25087-209">Select all text, right-click, and then click **Text Properties**.</span></span>

6.  <span data-ttu-id="25087-210">Haga clic en la pestaña **Fuente** .</span><span class="sxs-lookup"><span data-stu-id="25087-210">Click the **Font** tab.</span></span>

7.  <span data-ttu-id="25087-211">En la lista **Fuente** , seleccione **Times New Roman**; en **Tamaño** seleccione **20 pto**, en **Color** seleccione **Rojo**.</span><span class="sxs-lookup"><span data-stu-id="25087-211">In the **Font** list, select **Times New Roman**; in **Size** select **20 pt**, in **Color** select **Red**.</span></span>

     <span data-ttu-id="25087-212">![Propiedades de texto](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Propiedades de texto")</span><span class="sxs-lookup"><span data-stu-id="25087-212">![Text Properties](../../2014/tutorials/media/tutorial-textpropertieswithnumbers.png "Text Properties")</span></span>

8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]

9. <span data-ttu-id="25087-213">Coloque el cursor debajo del texto que escribió en el paso 3 y escriba: **Hola** .</span><span class="sxs-lookup"><span data-stu-id="25087-213">Place the cursor below the text you typed in step 3 and type: **Hello** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25087-214">Asegúrese de incluir el espacio adicional después de la palabra "Hola".</span><span class="sxs-lookup"><span data-stu-id="25087-214">Be sure to include the extra space after the word "Hello".</span></span> <span data-ttu-id="25087-215">El espacio separa el texto y el campo que agregará en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="25087-215">The space separates the text and the field that you will add in the next step.</span></span>

10. <span data-ttu-id="25087-216">Arrastre el campo FullName hasta el cuadro de texto y colóquelo después del el texto que escribió en el paso 9 y, a continuación, escribe una coma (,).</span><span class="sxs-lookup"><span data-stu-id="25087-216">Drag the FullName field to the text box and place it after the text you typed in step 9, and then type a comma (,).</span></span>

     <span data-ttu-id="25087-217">![Añadir campo de nombre completo](../../2014/tutorials/media/tutorial-addfullnamefield.png "Añadir campo de nombre completo")</span><span class="sxs-lookup"><span data-stu-id="25087-217">![Add Full Name field](../../2014/tutorials/media/tutorial-addfullnamefield.png "Add Full Name field")</span></span>

11. <span data-ttu-id="25087-218">Seleccionar el texto que agregó en los pasos 9 y 10, haga clic con el botón secundario y, a continuación, haga clic en **Propiedades de texto**</span><span class="sxs-lookup"><span data-stu-id="25087-218">Select the text you added in steps 9 and 10, right-click, and then click **Text Properties**.</span></span>

12. <span data-ttu-id="25087-219">Haga clic en la pestaña **Fuente** .</span><span class="sxs-lookup"><span data-stu-id="25087-219">Click the **Font** tab.</span></span>

13. <span data-ttu-id="25087-220">En la lista **Fuente** , seleccione **Times New Roman**; en **Tamaño** seleccione **16 pto**, en **Color** seleccione **Negro** .</span><span class="sxs-lookup"><span data-stu-id="25087-220">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Black** color.</span></span>

14. [!INCLUDE[clickOK](../includes/clickok-md.md)]

15. <span data-ttu-id="25087-221">Coloque el cursor debajo del texto que agregó en los pasos 9 a 13, y, a continuación, copie y pegue el siguiente texto de "lorem ipsum":</span><span class="sxs-lookup"><span data-stu-id="25087-221">Place the cursor below the text you added in steps 9 through 13, and then copy and paste the following "greeked" text:</span></span>

    ```
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin sed dolor in ipsum pulvinar egestas. Sed sed lacus at leo ornare ultricies. Vivamus velit risus, euismod nec sodales gravida, gravida in dui. Etiam ullamcorper elit vitae justo fermentum ut ullamcorper augue sodales. Ut placerat, nisl quis feugiat adipiscing, nibh est aliquet est, mollis faucibus mauris lectus quis arcu. In mollis tincidunt lacinia. In vitae erat ut lorem tincidunt luctus. Curabitur et magna nunc, sit amet adipiscing nisi. Nulla rhoncus elementum orci nec tincidunt. Aliquam imperdiet cursus erat vel tincidunt. Donec et neque ac urna rutrum sodales. In id purus et nisl dignissim dapibus. Sed rhoncus metus at felis feugiat eu tempor dolor vehicula. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam faucibus consectetur diam eu pellentesque. 
    Nulla facilisi. Proin ligula enim, porta ut tincidunt id, adipiscing sit amet eros. Ut purus sem, bibendum et vulputate sit amet, facilisis eget magna. Sed aliquam erat non erat eleifend hendrerit. Ut a ligula est, sit amet eleifend enim. Ut et nisl enim, sit amet adipiscing augue. Vivamus eu arcu ac libero posuere elementum. Integer condimentum bibendum venenatis. Integer odio tellus, feugiat in pellentesque semper, interdum nec sem. Sed cursus euismod sem, ut elementum sapien placerat vel. 
    ```

16. <span data-ttu-id="25087-222">Seleccionar el texto que agregó en el paso 15, haga clic con el botón secundario y, a continuación, haga clic en **Propiedades de texto**</span><span class="sxs-lookup"><span data-stu-id="25087-222">Select the text you added in steps 15, right-click, and then click **Text Properties**.</span></span>

17. <span data-ttu-id="25087-223">Haga clic en la pestaña **Fuente** .</span><span class="sxs-lookup"><span data-stu-id="25087-223">Click the **Font** tab.</span></span>

18. <span data-ttu-id="25087-224">En la lista **Fuente** , seleccione **Arial**; en **Tamaño** seleccione **10 pto**, en **Color** seleccione **Negro**.</span><span class="sxs-lookup"><span data-stu-id="25087-224">In the **Font** list, select **Arial**; in **Size** select **10 pt**, in **Color** select **Black**.</span></span>

19. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="25087-225">![Añadir texto al boletín](../../2014/tutorials/media/tutorial-newslettertext.png "Añadir texto al boletín")</span><span class="sxs-lookup"><span data-stu-id="25087-225">![Add newsletter text](../../2014/tutorials/media/tutorial-newslettertext.png "Add newsletter text")</span></span>

20. <span data-ttu-id="25087-226">Coloque el cursor debajo del texto que pegó en el paso 15, y, a continuación, escriba: **Felicidades por sus ventas totales de** .</span><span class="sxs-lookup"><span data-stu-id="25087-226">Place the cursor below the text you pasted in step 15, and then type: **Congratulations on your total sales of** .</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25087-227">Asegúrese de incluir el espacio adicional después de la palabra "de".</span><span class="sxs-lookup"><span data-stu-id="25087-227">Be sure to include the extra space after the word "of".</span></span> <span data-ttu-id="25087-228">El espacio separa el texto y el campo que agregará en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="25087-228">The space separates the text and the field that you will add in the next step.</span></span>

21. <span data-ttu-id="25087-229">Arrastre el campo Sales hasta el cuadro de texto, colóquelo después del texto que escribió en el paso 20 y, a continuación, escriba un signo de admiración (!).</span><span class="sxs-lookup"><span data-stu-id="25087-229">Drag the Sales field to the text box, place it after the text you typed in step 20, and then type an exclamation mark (!).</span></span>

22. <span data-ttu-id="25087-230">Resalte el campo ventas, haga clic con el botón secundario en el campo y, a continuación, haga clic en **expresión**.</span><span class="sxs-lookup"><span data-stu-id="25087-230">Highlight the Sales field, right-click the field, and then click **Expression**.</span></span>

23. <span data-ttu-id="25087-231">En el cuadro de expresión, cambie la expresión para incluir la función Sum como sigue:</span><span class="sxs-lookup"><span data-stu-id="25087-231">In the expression box, change the expression to include the Sum function as follows:</span></span>

    ```
    =Sum(Fields!Sales.value)
    ```

24. [!INCLUDE[clickOK](../includes/clickok-md.md)]

     <span data-ttu-id="25087-232">![Añadir una expresión al campo de ventas](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Añadir una expresión al campo de ventas")</span><span class="sxs-lookup"><span data-stu-id="25087-232">![Add an expression to sales field](../../2014/tutorials/media/tutorial-addexpressiontosalesfield.png "Add an expression to sales field")</span></span>

25. <span data-ttu-id="25087-233">Seleccionar el texto que agregó en los pasos 20 a 23, haga clic con el botón secundario y, a continuación, haga clic en **Propiedades de texto**</span><span class="sxs-lookup"><span data-stu-id="25087-233">Select the text you added in steps 20 through 23, right-click, and then click **Text Properties**.</span></span>

26. <span data-ttu-id="25087-234">Haga clic en la pestaña **Fuente** .</span><span class="sxs-lookup"><span data-stu-id="25087-234">Click the **Font** tab.</span></span>

27. <span data-ttu-id="25087-235">En la lista **Fuente** , seleccione **Times New Roman**; en **Tamaño** seleccione **16 pto**, en **Color** seleccione **Rojo**.</span><span class="sxs-lookup"><span data-stu-id="25087-235">In the **Font** list, select **Times New Roman**; in **Size** select **16 pt**, in **Color** select **Red**.</span></span>

28. [!INCLUDE[clickOK](../includes/clickok-md.md)]

29. <span data-ttu-id="25087-236">Seleccione `[Sum(Sales)]` y en la pestaña **Inicio** , en el grupo **Número** , haga clic en el botón **Moneda** .</span><span class="sxs-lookup"><span data-stu-id="25087-236">Select `[Sum(Sales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="25087-237">![Añadir símbolo de moneda](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Añadir símbolo de moneda")</span><span class="sxs-lookup"><span data-stu-id="25087-237">![Add currency symbol](../../2014/tutorials/media/tutorial-addcurrencysymbol.png "Add currency symbol")</span></span>

30. <span data-ttu-id="25087-238">Haga clic con el botón derecho en el cuadro de texto con el texto "Haga clic para agregar un título" y, después, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="25087-238">Right-click the text box with the "Click to add title" text, and then click **Delete**.</span></span>

31. <span data-ttu-id="25087-239">Seleccione el cuadro de lista y utilizando las teclas de dirección, muévalo a la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="25087-239">Select the list box and using the arrow keys, move it to the top of the page.</span></span>

32. <span data-ttu-id="25087-240">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="25087-240">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="25087-241">El informe muestra el texto estático y cada página del informe incluye datos que pertenecen a un territorio.</span><span class="sxs-lookup"><span data-stu-id="25087-241">The report displays static text and each report page includes data that pertains to a territory.</span></span> <span data-ttu-id="25087-242">Se da formato a las ventas como moneda.</span><span class="sxs-lookup"><span data-stu-id="25087-242">Sales are formatted as currency.</span></span>

 <span data-ttu-id="25087-243">![Vista previa de boletín](../../2014/tutorials/media/tutorial-newsletters.png "Vista previa de boletín")</span><span class="sxs-lookup"><span data-stu-id="25087-243">![Preview of Newsletter](../../2014/tutorials/media/tutorial-newsletters.png "Preview of Newsletter")</span></span>

##  <a name="5-add-a-table-to-show-sales-details"></a><a name="Table"></a><span data-ttu-id="25087-244">5. agregar una tabla para mostrar los detalles de ventas</span><span class="sxs-lookup"><span data-stu-id="25087-244">5. Add a Table to Show Sales Details</span></span>
 <span data-ttu-id="25087-245">Utilice el nuevo Asistente para tablas y matrices para agregar una tabla al informe de la forma libre.</span><span class="sxs-lookup"><span data-stu-id="25087-245">Use the New Table and Matrix Wizard to add a table to the free form report.</span></span> <span data-ttu-id="25087-246">Después de completar el asistente, agregará manualmente una fila para los totales.</span><span class="sxs-lookup"><span data-stu-id="25087-246">After you complete the wizard, you will manually add a row for totals.</span></span>

#### <a name="to-add-a-table"></a><span data-ttu-id="25087-247">Para agregar una tabla</span><span class="sxs-lookup"><span data-stu-id="25087-247">To add a table</span></span>

1.  <span data-ttu-id="25087-248">En la pestaña **Insertar** de la cinta de opciones, en el área **Regiones de datos** , haga clic en **Tabla**y, a continuación, haga clic en **Asistente para tablas**.</span><span class="sxs-lookup"><span data-stu-id="25087-248">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **Table**, and then click **Table Wizard**.</span></span>

2.  <span data-ttu-id="25087-249">En la página Elegir un conjunto de datos, haga clic en **ListDataset**.</span><span class="sxs-lookup"><span data-stu-id="25087-249">On the Choose a dataset page, click **ListDataset**.</span></span>

3.  <span data-ttu-id="25087-250">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="25087-250">Click **Next**.</span></span>

4.  <span data-ttu-id="25087-251">En la página **Organizar campos** , arrastre el campo Product desde **Campos disponibles** hasta **Valores**.</span><span class="sxs-lookup"><span data-stu-id="25087-251">On the **Arrange fields** page, drag the Product field from **Available fields** to **Values.**</span></span>

5.  <span data-ttu-id="25087-252">Repita el paso 4 para SalesDate, Quantity y Sales.</span><span class="sxs-lookup"><span data-stu-id="25087-252">Repeat step 4, for SalesDate, Quantity, and Sales.</span></span> <span data-ttu-id="25087-253">Coloque SalesDate bajo Product, Quantity bajo SalesDate y Sales bajo SalesDate.</span><span class="sxs-lookup"><span data-stu-id="25087-253">Place SalesDate below Product, Quantity below SalesDate, and Sales below SalesDate.</span></span>

6.  <span data-ttu-id="25087-254">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="25087-254">Click **Next**.</span></span>

7.  <span data-ttu-id="25087-255">En la página **Elegir el diseño** , vea el diseño de la tabla.</span><span class="sxs-lookup"><span data-stu-id="25087-255">On the **Choose the layout** page, view the layout of the table.</span></span>

     <span data-ttu-id="25087-256">La tabla es muy simple.</span><span class="sxs-lookup"><span data-stu-id="25087-256">The table is very simple.</span></span> <span data-ttu-id="25087-257">Se compone de cinco columnas y no tiene ningún grupo de filas o columnas.</span><span class="sxs-lookup"><span data-stu-id="25087-257">It consists of five columns and has no row or column groups.</span></span> <span data-ttu-id="25087-258">Dado que no tiene ningún grupo, las opciones de diseño relacionadas con los grupos no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="25087-258">Because it has no groups, the layout options related to groups, are not available.</span></span> <span data-ttu-id="25087-259">Actualizará manualmente la tabla para incluir un total en una fase posterior del tutorial.</span><span class="sxs-lookup"><span data-stu-id="25087-259">You will manually update the table to include a total later in the tutorial.</span></span>

8.  <span data-ttu-id="25087-260">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="25087-260">Click **Next**.</span></span>

9. <span data-ttu-id="25087-261">En la página **Elegir un estilo** , en el panel **Estilos** , seleccione **Pizarra**.</span><span class="sxs-lookup"><span data-stu-id="25087-261">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

10. <span data-ttu-id="25087-262">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="25087-262">Click **Finish**.</span></span>

11. <span data-ttu-id="25087-263">Arrastre la tabla bajo el cuadro de texto que agregó en la lección 4.</span><span class="sxs-lookup"><span data-stu-id="25087-263">Drag the table to below the text box that you added in lesson 4.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25087-264">Asegúrese de que la tabla está dentro de la lista.</span><span class="sxs-lookup"><span data-stu-id="25087-264">Make sure the table is inside the list.</span></span>

12. <span data-ttu-id="25087-265">Confirme que la tabla está seleccionada y, en el panel Grupo de filas, haga clic con el botón secundario en Detalles, seleccione **Agregar total**y, luego, haga clic en **Después**.</span><span class="sxs-lookup"><span data-stu-id="25087-265">Confirmed that the table is selected, then in the Row Group pane right-click Details, point to **Add Total**, and then click **After**.</span></span>

     <span data-ttu-id="25087-266">![Añadir total del informe](../../2014/tutorials/media/tutorial-addtotal.png "Añadir total del informe")</span><span class="sxs-lookup"><span data-stu-id="25087-266">![Add report total](../../2014/tutorials/media/tutorial-addtotal.png "Add report total")</span></span>

13. <span data-ttu-id="25087-267">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="25087-267">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="25087-268">El informe muestra una tabla con detalles y totales de ventas.</span><span class="sxs-lookup"><span data-stu-id="25087-268">The report displays a table with sales details and totals.</span></span>

 <span data-ttu-id="25087-269">![Totales de ventas en el informe](../../2014/tutorials/media/tutorial-reportsalestotals.png "Totales de ventas en el informe")</span><span class="sxs-lookup"><span data-stu-id="25087-269">![Sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals.png "Sales totals in report")</span></span>

##  <a name="6-format-data"></a><a name="Format"></a><span data-ttu-id="25087-270">6. dar formato a los datos</span><span class="sxs-lookup"><span data-stu-id="25087-270">6. Format Data</span></span>
 <span data-ttu-id="25087-271">Dar formato a datos numéricos como moneda y a fechas como día y hora solamente.</span><span class="sxs-lookup"><span data-stu-id="25087-271">Format numeric data as currency and dates as day and time only.</span></span>

#### <a name="to-format-fields-table"></a><span data-ttu-id="25087-272">Para dar formato a la tabla de campos</span><span class="sxs-lookup"><span data-stu-id="25087-272">To format fields table</span></span>

1.  <span data-ttu-id="25087-273">Haga clic en **Diseño** para cambiar a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="25087-273">Click **Design** to switch to design view.</span></span>

2.  <span data-ttu-id="25087-274">Haga clic en las celdas de la tabla que contienen `[Sum(SalesSales)]` y en la pestaña **Inicio** del grupo **Número** haga clic en el botón **Moneda** .</span><span class="sxs-lookup"><span data-stu-id="25087-274">Click the table cells that contain `[Sum(SalesSales)]` and on the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>

     <span data-ttu-id="25087-275">![Añadir símbolo de moneda a la suma de las ventas](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Añadir símbolo de moneda a la suma de las ventas")</span><span class="sxs-lookup"><span data-stu-id="25087-275">![Add currency symbol to sum sales](../../2014/tutorials/media/tutorial-sumsales-currencysymbol.png "Add currency symbol to sum sales")</span></span>

3.  <span data-ttu-id="25087-276">Haga clic en la celda que contiene `[SalesDate]` y en el grupo **Número** , en la lista desplegable, seleccione **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="25087-276">Click the cell that contains `[SalesDate]` and in the **Number** group, from the drop-down list, select **Date**.</span></span>

4.  <span data-ttu-id="25087-277">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="25087-277">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="25087-278">El informe muestra ahora datos dados con formato y es más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="25087-278">The report now displays formatted data and is easier to read.</span></span>

 <span data-ttu-id="25087-279">![Formatear totales de ventas en el informe](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Formatear totales de ventas en el informe")</span><span class="sxs-lookup"><span data-stu-id="25087-279">![Format sales totals in report](../../2014/tutorials/media/tutorial-reportsalestotals-formatted.png "Format sales totals in report")</span></span>

##  <a name="7-save-the-report"></a><a name="Save"></a><span data-ttu-id="25087-280">7. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="25087-280">7. Save the Report</span></span>
 <span data-ttu-id="25087-281">Puede guardar los informes en un servidor de informes, en una biblioteca de SharePoint o en su equipo.</span><span class="sxs-lookup"><span data-stu-id="25087-281">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="25087-282">También puede exportar el informe en diversos formatos, como Word y PDF: para ello, ejecute el informe y seleccione el formato en el menú **Exportar** .</span><span class="sxs-lookup"><span data-stu-id="25087-282">You can also export the report to a variety of formats such as Word and PDF, by running the report and selecting the format from the **Export** menu.</span></span>

 <span data-ttu-id="25087-283">En este tutorial, guarde el informe en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="25087-283">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="25087-284">Si no tiene acceso a un servidor de informes, guarde el informe en su equipo.</span><span class="sxs-lookup"><span data-stu-id="25087-284">If you do not have access to a report server, save the report to your computer.</span></span>

#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="25087-285">Para guardar el informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="25087-285">To save the report on a report server</span></span>

1.  <span data-ttu-id="25087-286">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="25087-286">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="25087-287">Haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="25087-287">Click **Recent Sites and Servers**.</span></span>

3.  <span data-ttu-id="25087-288">Seleccione o escriba el nombre del servidor de informes donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="25087-288">Select or type the name of the report server where you have permission to save reports.</span></span>

     <span data-ttu-id="25087-289">Aparecerá el mensaje "Conectando con el servidor de informes".</span><span class="sxs-lookup"><span data-stu-id="25087-289">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="25087-290">Una vez completada la conexión, se mostrará el contenido de la carpeta de informes que el administrador del servidor de informes especificó como ubicación predeterminada para los informes.</span><span class="sxs-lookup"><span data-stu-id="25087-290">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>

4.  <span data-ttu-id="25087-291">En `Name` , reemplace el nombre predeterminado por **SalesInformationByTerritory**.</span><span class="sxs-lookup"><span data-stu-id="25087-291">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

5.  <span data-ttu-id="25087-292">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="25087-292">Click **Save**.</span></span>

 <span data-ttu-id="25087-293">El informe se guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="25087-293">The report is saved to the report server.</span></span> <span data-ttu-id="25087-294">El nombre del servidor de informes al que está conectado aparecerá en la barra de estado en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="25087-294">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>

#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="25087-295">Para guardar el informe en el equipo</span><span class="sxs-lookup"><span data-stu-id="25087-295">To save the report on your computer</span></span>

1.  <span data-ttu-id="25087-296">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="25087-296">From the **Report Builder** button, click **Save As**.</span></span>

2.  <span data-ttu-id="25087-297">Haga clic en **Escritorio**, **Mis documentos**o **Mi PC**y vaya a la carpeta donde desea guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="25087-297">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>

3.  <span data-ttu-id="25087-298">En `Name` , reemplace el nombre predeterminado por **SalesInformationByTerritory**.</span><span class="sxs-lookup"><span data-stu-id="25087-298">In `Name`, replace the default name with **SalesInformationByTerritory**.</span></span>

4.  <span data-ttu-id="25087-299">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="25087-299">Click **Save**.</span></span>

##  <a name="8-optional-add-a-line-to-separate-areas-of-the-report"></a><a name="Line"></a><span data-ttu-id="25087-300">8. (opcional) agregar una línea para separar áreas del informe</span><span class="sxs-lookup"><span data-stu-id="25087-300">8. (Optional) Add a Line to Separate Areas of the Report</span></span>
 <span data-ttu-id="25087-301">Agregue una línea para separar las áreas de editorial y detalles del informe.</span><span class="sxs-lookup"><span data-stu-id="25087-301">Add a line to separate the editorial and details areas of the report.</span></span>

#### <a name="to-add-a-line"></a><span data-ttu-id="25087-302">Para agregar una línea</span><span class="sxs-lookup"><span data-stu-id="25087-302">To add a line</span></span>

1.  <span data-ttu-id="25087-303">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="25087-303">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="25087-304">En la pestaña **Insertar** de la cinta de opciones, en el área **Elementos de informe** , haga clic en **Línea.**</span><span class="sxs-lookup"><span data-stu-id="25087-304">On the **Insert** tab of the ribbon, in the **Report Items** area, click **Line.**</span></span>

3.  <span data-ttu-id="25087-305">Dibuje una línea debajo del cuadro de texto de forma libre que agregó en la lección 4.</span><span class="sxs-lookup"><span data-stu-id="25087-305">Draw a line below the free form text box you added in lesson 4.</span></span>

4.  <span data-ttu-id="25087-306">Haga clic en la línea.</span><span class="sxs-lookup"><span data-stu-id="25087-306">Click the line.</span></span>

5.  <span data-ttu-id="25087-307">Haga clic en la pestaña **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="25087-307">Click the **Home** tab.</span></span>

6.  <span data-ttu-id="25087-308">En el área **Borde** , para el ancho seleccione **4 1/2** pto y para el color seleccione **Rojo**.</span><span class="sxs-lookup"><span data-stu-id="25087-308">In the **Border** area, for width select **4 1/2** pt and for color, for color select **Red**.</span></span>

     <span data-ttu-id="25087-309">![Añadir línea al informe](../../2014/tutorials/media/tutorial-reportwithline.png "Añadir línea al informe")</span><span class="sxs-lookup"><span data-stu-id="25087-309">![Add line to report](../../2014/tutorials/media/tutorial-reportwithline.png "Add line to report")</span></span>

##  <a name="9-optional-add-summary-data-visualization"></a><a name="Visualization"></a><span data-ttu-id="25087-310">9. (opcional) agregar visualización de datos resumidos</span><span class="sxs-lookup"><span data-stu-id="25087-310">9. (Optional) Add Summary Data Visualization</span></span>
 <span data-ttu-id="25087-311">Los rectángulos le ayudan a controlar cómo se representa el informe.</span><span class="sxs-lookup"><span data-stu-id="25087-311">Rectangles help you control how the report renders.</span></span> <span data-ttu-id="25087-312">Coloque un grafo circular y de columnas dentro de un rectángulo para asegurarse de que el informe se representa del modo que desea.</span><span class="sxs-lookup"><span data-stu-id="25087-312">Place a pie and column chart inside a rectangle to ensure that the report renders the way you want.</span></span>

#### <a name="to-add-a-rectangle"></a><span data-ttu-id="25087-313">Para agregar un rectángulo</span><span class="sxs-lookup"><span data-stu-id="25087-313">To add a rectangle</span></span>

1.  <span data-ttu-id="25087-314">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="25087-314">Click **Design** to return to design view.</span></span>

2.  <span data-ttu-id="25087-315">En la pestaña **Insertar** de la cinta de opciones, en el área **Elementos de informe** haga clic en **Rectángulo**y, a continuación, arrastre el rectángulo dentro de la lista, a la derecha de la tabla.</span><span class="sxs-lookup"><span data-stu-id="25087-315">On the **Insert** tab of the ribbon, in the **Report Items** area click **Rectangle**, and then drag the rectangle inside the list, to the right of the table.</span></span> <span data-ttu-id="25087-316">Haga el rectángulo de 2 pulgadas de alto y 4 de ancho.</span><span class="sxs-lookup"><span data-stu-id="25087-316">Make the rectangle 2 inches wide and 4 inches tall.</span></span>

3.  <span data-ttu-id="25087-317">Alinee las partes superiores del rectángulo y la tabla.</span><span class="sxs-lookup"><span data-stu-id="25087-317">Align the tops of the rectangle and the table.</span></span>

#### <a name="to-add-a-pie-chart"></a><span data-ttu-id="25087-318">Para agregar un gráfico circular</span><span class="sxs-lookup"><span data-stu-id="25087-318">To add a pie chart</span></span>

1.  <span data-ttu-id="25087-319">En la pestaña **Insertar** de la cinta de opciones, en el área **Visualizaciones de datos** , haga clic en **Gráfico** y después haga clic en **Asistente para gráficos**.</span><span class="sxs-lookup"><span data-stu-id="25087-319">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="25087-320">En la página Elegir un conjunto de datos , haga clic en **ListDataset**y, después, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="25087-320">On the Choose a dataset page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="25087-321">Haga clic en **Circular**y, a continuación, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="25087-321">Click **Pie**, and then click **Next**.</span></span>

4.  <span data-ttu-id="25087-322">En la página Organizar campos del gráfico, arrastre Product hasta **Categorías**.</span><span class="sxs-lookup"><span data-stu-id="25087-322">On the arrange chart fields page, drag Product to **Categories**.</span></span>

5.  <span data-ttu-id="25087-323">Arrastre quantity hasta **valores**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="25087-323">Drag Quantity to **Values**, and then click **Next**.</span></span>

6.  <span data-ttu-id="25087-324">En la página **Elegir un estilo** , en el panel **Estilos** , seleccione **Pizarra**.</span><span class="sxs-lookup"><span data-stu-id="25087-324">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="25087-325">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="25087-325">Click **Finish**.</span></span>

8.  <span data-ttu-id="25087-326">Cambie el tamaño del gráfico que aparece en la esquina superior izquierda del informe, para que tenga 1 1/2 pulgadas de alto y 2 de ancho.</span><span class="sxs-lookup"><span data-stu-id="25087-326">Resize the chart that appears in the upper left corner of the report, to be 1 1/2 inches tall and 2 inches wide.</span></span>

9. <span data-ttu-id="25087-327">Arrastre el gráfico dentro del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="25087-327">Drag the chart inside the rectangle.</span></span>

     <span data-ttu-id="25087-328">![Añadir gráfico circular](../../2014/tutorials/media/tutorial-addpiechart.png "Añadir gráfico circular")</span><span class="sxs-lookup"><span data-stu-id="25087-328">![Add pie chart](../../2014/tutorials/media/tutorial-addpiechart.png "Add pie chart")</span></span>

10. <span data-ttu-id="25087-329">Haga clic con el botón secundario en el título del gráfico y luego haga clic en **Propiedades del título**.</span><span class="sxs-lookup"><span data-stu-id="25087-329">Right-click the chart title, and then click **Title Properties**.</span></span>

11. <span data-ttu-id="25087-330">En el cuadro de diálogo **Propiedades del título del gráfico** , en texto de título, escriba: **Cantidades de producto vendidas**.</span><span class="sxs-lookup"><span data-stu-id="25087-330">In the **Chart Title Properties** dialog box, in Title text, type: **Product Quantities Sold**.</span></span>

12. <span data-ttu-id="25087-331">Haga clic en la pestaña **Fuente** y en la lista **Tamaño** haga clic en **10 pto**.</span><span class="sxs-lookup"><span data-stu-id="25087-331">Click the **Font** tab, and in the **Size** list, click **10pt**.</span></span>

13. [!INCLUDE[clickOK](../includes/clickok-md.md)]

#### <a name="to-add-a-column-chart"></a><span data-ttu-id="25087-332">Para agregar un gráfico de columnas</span><span class="sxs-lookup"><span data-stu-id="25087-332">To add a column chart</span></span>

1.  <span data-ttu-id="25087-333">En la pestaña **Insertar** de la cinta de opciones, en el área **Visualizaciones de datos** , haga clic en **Gráfico** y después haga clic en **Asistente para gráficos**.</span><span class="sxs-lookup"><span data-stu-id="25087-333">On the **Insert** tab of the ribbon, in the **Data Visualizations** area, click **Chart,** and then click **Chart Wizard**.</span></span>

2.  <span data-ttu-id="25087-334">En la página **Elegir un conjunto de datos** , haga clic en **ListDataset**y, después, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="25087-334">On the **Choose a dataset** page, click **ListDataset**, and then click **Next**.</span></span>

3.  <span data-ttu-id="25087-335">Haga clic en **Columna**y, a continuación, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="25087-335">Click **Column**, and then click **Next**.</span></span>

4.  <span data-ttu-id="25087-336">En la página organizar campos del gráfico, arrastre el campo Product hasta **categorías**.</span><span class="sxs-lookup"><span data-stu-id="25087-336">On the arrange chart fields page, drag the Product field to **Categories**.</span></span>

5.  <span data-ttu-id="25087-337">Arrastre Sales hasta **Valores** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="25087-337">Drag Sales to **Values,** and then click **Next**.</span></span>

     <span data-ttu-id="25087-338">Valores se muestra en el eje vertical.</span><span class="sxs-lookup"><span data-stu-id="25087-338">Values display on the vertical axis.</span></span>

6.  <span data-ttu-id="25087-339">En la página **Elegir un estilo** , en el panel **Estilos** , seleccione **Pizarra**.</span><span class="sxs-lookup"><span data-stu-id="25087-339">On the **Choose a Style** page, in the **Styles** pane, select **Slate**.</span></span>

7.  <span data-ttu-id="25087-340">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="25087-340">Click **Finish**.</span></span>

     <span data-ttu-id="25087-341">Un gráfico de columnas se agrega a la esquina superior izquierda del informe.</span><span class="sxs-lookup"><span data-stu-id="25087-341">A column chart is added to the upper left corner of the report.</span></span>

8.  <span data-ttu-id="25087-342">Cambie el tamaño del gráfico para que tenga 2 pulgadas de ancho y 2 de alto.</span><span class="sxs-lookup"><span data-stu-id="25087-342">Resize the chart to be 2 inches wide and 2 inches tall.</span></span>

9. <span data-ttu-id="25087-343">Arrastre el gráfico al interior del rectángulo, debajo del gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="25087-343">Drag the chart inside the rectangle, below the pie chart.</span></span>

     <span data-ttu-id="25087-344">![Agregar gráfico de columnas](../../2014/tutorials/media/tutorial-addcolumnchart.png "Agregar gráfico de columnas")</span><span class="sxs-lookup"><span data-stu-id="25087-344">![Add column chart](../../2014/tutorials/media/tutorial-addcolumnchart.png "Add column chart")</span></span>

10. <span data-ttu-id="25087-345">Haga clic con el botón secundario en el título del gráfico y después haga clic en **propiedades del título**.</span><span class="sxs-lookup"><span data-stu-id="25087-345">Right-click the chart title and then click **Title Properties**.</span></span>

11. <span data-ttu-id="25087-346">En el cuadro de diálogo **Propiedades del título del gráfico** , en texto de título, escriba: **Ventas de producto**.</span><span class="sxs-lookup"><span data-stu-id="25087-346">In the **Chart Title Properties** dialog box, in Title text, type: **Product Sales**.</span></span>

12. <span data-ttu-id="25087-347">Haga clic en la pestaña **Fuente** y, en la lista **Tamaño** , haga clic en **10 pto**y luego en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="25087-347">Click the **Font** tab, and in the **Size** list click **10pt**, and then click **OK**.</span></span>

13. <span data-ttu-id="25087-348">En el gráfico de columnas, haga clic con el botón secundario en el eje vertical y después anule la selección de **Mostrar título del eje**.</span><span class="sxs-lookup"><span data-stu-id="25087-348">In the column chart, right click the vertical axis, and then deselect **Show Axis Title**.</span></span>

14. <span data-ttu-id="25087-349">Repita el paso 13 para el eje horizontal.</span><span class="sxs-lookup"><span data-stu-id="25087-349">Repeat step 13 for the horizontal axis.</span></span>

15. <span data-ttu-id="25087-350">Haga clic con el botón secundario en la leyenda y, a continuación, haga clic en **Eliminar leyenda**.</span><span class="sxs-lookup"><span data-stu-id="25087-350">Right click the legend, and then click **Delete Legend**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25087-351">Quitar los títulos y la leyenda de un eje vuelve el gráfico más legible cuando es un tamaño pequeño.</span><span class="sxs-lookup"><span data-stu-id="25087-351">Removing axis titles and the legend makes the chart more readable when it is a small size.</span></span>

 <span data-ttu-id="25087-352">![Cambiar los títulos del gráfico y eliminar el título del eje](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Cambiar los títulos del gráfico y eliminar el título del eje")</span><span class="sxs-lookup"><span data-stu-id="25087-352">![Change chart titles and remove axis title](../../2014/tutorials/media/tutorial-columnchart-newtitle-noaxistitle.png "Change chart titles and remove axis title")</span></span>

#### <a name="to-verify-the-charts-are-inside-the-rectangle"></a><span data-ttu-id="25087-353">Para comprobar que los gráficos están dentro del rectángulo</span><span class="sxs-lookup"><span data-stu-id="25087-353">To verify the charts are inside the rectangle</span></span>

1.  <span data-ttu-id="25087-354">Haga clic en el rectángulo que agregó anteriormente en esta lección.</span><span class="sxs-lookup"><span data-stu-id="25087-354">Click the rectangle you added earlier in this lesson.</span></span>

     <span data-ttu-id="25087-355">En el panel Propiedades, la propiedad `Name` muestra el nombre del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="25087-355">In the Properties pane, the `Name` property displays the name of the rectangle.</span></span>

     <span data-ttu-id="25087-356">![Nombre del rectángulo](../../2014/tutorials/media/tutorial-rectanglename.png "Nombre del rectángulo")</span><span class="sxs-lookup"><span data-stu-id="25087-356">![Name of rectangle](../../2014/tutorials/media/tutorial-rectanglename.png "Name of rectangle")</span></span>

2.  <span data-ttu-id="25087-357">Haga clic en el gráfico circular.</span><span class="sxs-lookup"><span data-stu-id="25087-357">Click the pie chart.</span></span>

3.  <span data-ttu-id="25087-358">En el panel **propiedades** , compruebe que la `Parent` propiedad contiene el nombre del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="25087-358">In the **Properties** pane, verify that the `Parent` property contains the name of the rectangle.</span></span>

     <span data-ttu-id="25087-359">![Propiedad primaria del gráfico circular](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Propiedad primaria del gráfico circular")</span><span class="sxs-lookup"><span data-stu-id="25087-359">![Parent property for pie chart](../../2014/tutorials/media/tutorial-piechart-parentproperty.png "Parent property for pie chart")</span></span>

4.  <span data-ttu-id="25087-360">Haga clic en el gráfico de columnas y repita los pasos 2 y 3.</span><span class="sxs-lookup"><span data-stu-id="25087-360">Click the column chart and repeat steps 2 and 3.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25087-361">Si los gráficos no están dentro del rectángulo, el informe representado no muestra los gráficos juntos.</span><span class="sxs-lookup"><span data-stu-id="25087-361">If the charts are not inside the rectangle, the rendered report does not display the charts together.</span></span>

#### <a name="to-make-the-charts-the-same-size"></a><span data-ttu-id="25087-362">Para que los gráficos sean del mismo tamaño</span><span class="sxs-lookup"><span data-stu-id="25087-362">To make the charts the same size</span></span>

1.  <span data-ttu-id="25087-363">Haga clic en el gráfico circular, presione la tecla CTRL y, a continuación, haga clic en el gráfico de columnas.</span><span class="sxs-lookup"><span data-stu-id="25087-363">Click the pie chart, press the Ctrl key, and then click the column chart.</span></span>

2.  <span data-ttu-id="25087-364">Con ambos gráficos seleccionados, haga clic con el botón secundario para seleccionar **Diseño**y, a continuación, haga clic en **Igualar ancho**.</span><span class="sxs-lookup"><span data-stu-id="25087-364">With both charts selected, right-click, point to **Layout**, and then click **Make Same Width**.</span></span>

     <span data-ttu-id="25087-365">![Igualar los anchos de los gráficos](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Igualar los anchos de los gráficos")</span><span class="sxs-lookup"><span data-stu-id="25087-365">![Make chart widths the same](../../2014/tutorials/media/tutorial-makechartssamewidth.png "Make chart widths the same")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="25087-366">El elemento en el que hace clic primero determina el ancho de todos los elementos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="25087-366">The item you click first determines the width of all the selected items.</span></span>

3.  <span data-ttu-id="25087-367">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="25087-367">Click **Run** to preview the report.</span></span>

 <span data-ttu-id="25087-368">El informe muestra ahora los datos de ventas resumidos en gráficos circulares y de columnas.</span><span class="sxs-lookup"><span data-stu-id="25087-368">The report now displays summary sales data in pie and column charts.</span></span>

 <span data-ttu-id="25087-369">![Tutorial de SSRS, informe con formato libre](../../2014/tutorials/media/tutorial-reportfinal.png "Tutorial de SSRS, informe con formato libre")</span><span class="sxs-lookup"><span data-stu-id="25087-369">![SSRS tutorial, free form report](../../2014/tutorials/media/tutorial-reportfinal.png "SSRS tutorial, free form report")</span></span>

## <a name="more-information"></a><span data-ttu-id="25087-370">Más información</span><span class="sxs-lookup"><span data-stu-id="25087-370">More Information</span></span>
 <span data-ttu-id="25087-371">Para obtener más información acerca de las listas, consulte [tablas, matrices y listas &#40;generador de informes y ssrs&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [enumera &#40;Generador de informes y SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), áreas de la [región de datos Tablix &#40;generador de informes y SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)y [celdas, filas y columnas de la región de datos Tablix &#40;generador de informes&#41; y SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="25087-371">For more information about lists, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/tables-matrices-and-lists-report-builder-and-ssrs.md), [Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md).</span></span>

 <span data-ttu-id="25087-372">Para más información sobre los diseñadores de consultas, vea [Diseñadores de consultas &#40;Generador de informes&#41;](../../2014/reporting-services/query-designers-report-builder.md) e [Interfaz de usuario del Diseñador de consultas basado en texto &#40;Generador de informes&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="25087-372">For more information about query designers, see [Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) and [Text-based Query Designer User Interface &#40;Report Builder&#41;](report-data/text-based-query-designer-user-interface-report-builder.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="25087-373">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25087-373">See Also</span></span>
 <span data-ttu-id="25087-374">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) [Generador de informes en SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="25087-374">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) [Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md)</span></span>


