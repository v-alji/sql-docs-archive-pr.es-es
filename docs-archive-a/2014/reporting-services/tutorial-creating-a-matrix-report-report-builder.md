---
title: 'Tutorial: Crear un informe de matriz (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9ee19c2e-2a8c-4bb0-9274-04a5812c2e96
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3df32098d9e6400931ba2a88b2ffd22d6e015a62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748603"
---
# <a name="tutorial-creating-a-matrix-report-report-builder"></a><span data-ttu-id="486da-102">Tutorial: Crear un informe de matriz (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="486da-102">Tutorial: Creating a Matrix Report (Report Builder)</span></span>
  <span data-ttu-id="486da-103">Este tutorial enseña a crear un informe de matriz básico de acuerdo con los datos de ventas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="486da-103">This tutorial teaches you how to create a basic matrix report based on sample sales data.</span></span> <span data-ttu-id="486da-104">La matriz ha anidado en grupos de filas y de columnas, así como en un grupos de columnas adyacente.</span><span class="sxs-lookup"><span data-stu-id="486da-104">The matrix has nested row and column groups and an adjacent column group.</span></span> <span data-ttu-id="486da-105">También aprenderá a dar formato a las columnas y a girar el texto.</span><span class="sxs-lookup"><span data-stu-id="486da-105">You will also learn how to format columns and rotate text.</span></span> <span data-ttu-id="486da-106">En la siguiente ilustración se muestra un informe similar al que creará.</span><span class="sxs-lookup"><span data-stu-id="486da-106">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="486da-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span><span class="sxs-lookup"><span data-stu-id="486da-107">![rs_CreateMatixReportTutorial](../../2014/tutorials/media/rs-creatematixreporttutorial.gif "rs_CreateMatixReportTutorial")</span></span>  
  
 <span data-ttu-id="486da-108">Una versión mejorada del informe que creará en este tutorial está disponible como ejemplo en el informe del Generador de informes de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="486da-108">An enhanced version of the report you will create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="486da-109">Para obtener más información acerca de cómo descargar este informe de ejemplo y otros, vea [generador de informes informes de ejemplo](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="486da-109">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="486da-110">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="486da-110">What You Will Learn</span></span>  
 <span data-ttu-id="486da-111">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="486da-111">In this tutorial, you will learn how to:</span></span>  
  
1.  [<span data-ttu-id="486da-112">Crear un informe de matriz y un conjunto de datos desde el nuevo Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="486da-112">Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>](#CreateMatrix)  
  
2.  [<span data-ttu-id="486da-113">Organizar datos y elegir el diseño y el estilo desde el nuevo Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="486da-113">Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>](#Groups)  
  
3.  [<span data-ttu-id="486da-114">Dar formato a datos</span><span class="sxs-lookup"><span data-stu-id="486da-114">Format Data</span></span>](#FormatData)  
  
4.  [<span data-ttu-id="486da-115">Agregar grupo de columnas adyacente</span><span class="sxs-lookup"><span data-stu-id="486da-115">Add Adjacent Column Group</span></span>](#AdjacentGroup)  
  
5.  [<span data-ttu-id="486da-116">Cambiar el ancho de columna</span><span class="sxs-lookup"><span data-stu-id="486da-116">Change Column Widths</span></span>](#Width)  
  
6.  [<span data-ttu-id="486da-117">Combinar las celdas de la matriz</span><span class="sxs-lookup"><span data-stu-id="486da-117">Merge Matrix Cells</span></span>](#MergeCells)  
  
7.  [<span data-ttu-id="486da-118">Agregar un encabezado y un título del informe</span><span class="sxs-lookup"><span data-stu-id="486da-118">Add a Report Header and Report Title</span></span>](#HeaderTitle)  
  
8.  [<span data-ttu-id="486da-119">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="486da-119">Save the Report</span></span>](#Save)  
  
### <a name="other-optional-step"></a><span data-ttu-id="486da-120">Otro paso opcional</span><span class="sxs-lookup"><span data-stu-id="486da-120">Other Optional Step</span></span>  
  
1.  [<span data-ttu-id="486da-121">Girar 270 grados el cuadro de texto</span><span class="sxs-lookup"><span data-stu-id="486da-121">Rotate Text Box 270 Degrees</span></span>](#RotateTextBox)  
  
 <span data-ttu-id="486da-122">Tiempo estimado para completar este tutorial: 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="486da-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="486da-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="486da-123">Requirements</span></span>  
 <span data-ttu-id="486da-124">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="486da-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-matrix-report-and-dataset-from-the-new-table-or-matrix-wizard"></a><a name="CreateMatrix"></a><span data-ttu-id="486da-125">1. crear un informe de matriz y un conjunto de DataSet desde el Asistente para nueva tabla o matriz</span><span class="sxs-lookup"><span data-stu-id="486da-125">1. Create a Matrix Report and Dataset from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="486da-126">En el cuadro de diálogo **Introducción** en generador de informes, elija un origen de datos compartido, cree un conjunto de datos incrustado y, a continuación, muestre los datos en una matriz.</span><span class="sxs-lookup"><span data-stu-id="486da-126">From the **Getting Started** dialog box in Report Builder, choose a shared data source, create an embedded dataset, and then display the data in a matrix.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="486da-127">En este tutorial, la consulta contiene ya los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="486da-127">In this tutorial, the query already contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="486da-128">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="486da-128">This makes the query quite long.</span></span> <span data-ttu-id="486da-129">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="486da-129">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="486da-130">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="486da-130">This is for learning purposes only.</span></span>  
  
#### <a name="to-create-a-new-matrix"></a><span data-ttu-id="486da-131">Para crear una nueva matriz</span><span class="sxs-lookup"><span data-stu-id="486da-131">To create a new matrix</span></span>  
  
1.  <span data-ttu-id="486da-132">Haga clic en **Inicio**, seleccione **Programas**, **Generador de informes de Microsoft SQL Server 2012**y, a continuación, haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="486da-132">Click **Start**, point to **Programs**, point to **Microsoft SQL Server 2012 Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="486da-133">Debería aparecer el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="486da-133">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="486da-134">Si no es así, en el botón Generador de informes, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="486da-134">If it doesn't, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="486da-135">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="486da-135">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="486da-136">En el panel de la derecha, haga clic en **Asistente para tabla o matriz**.</span><span class="sxs-lookup"><span data-stu-id="486da-136">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="486da-137">En la página **Elegir un conjunto de datos** , haga clic en **Crear un conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="486da-137">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="486da-138">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="486da-138">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="486da-139">En la página **elegir una conexión a un origen de datos** , seleccione un origen de datos existente o vaya al servidor de informes y, a continuación, seleccione un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="486da-139">On the **Choose a connection to a data source** page, select an existing data source or browse to the report server, and then select a data source.</span></span> <span data-ttu-id="486da-140">Si no hay disponible ningún origen de datos o no tiene acceso a un servidor de informes, puede utilizar un origen de datos incrustados en su lugar.</span><span class="sxs-lookup"><span data-stu-id="486da-140">If no data source is available or you do not have access to a report server, you can use an embedded data source instead.</span></span> <span data-ttu-id="486da-141">Para obtener más información acerca de la creación de un origen de datos incrustado, vea [Tutorial: crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="486da-141">For more information about creating an embedded data source, see [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
7.  <span data-ttu-id="486da-142">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="486da-142">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="486da-143">En la página **Diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="486da-143">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="486da-144">Copie y pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="486da-144">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity  
    ```  
  
10. <span data-ttu-id="486da-145">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="486da-145">Click **Next**.</span></span>  
  
##  <a name="2-organize-data-and-choose-layout-and-style-from-the-new-table-or-matrix-wizard"></a><a name="Groups"></a><span data-ttu-id="486da-146">2. organizar datos y elegir el diseño y el estilo desde el Asistente para nueva tabla o matriz</span><span class="sxs-lookup"><span data-stu-id="486da-146">2. Organize Data and Choose Layout and Style from the New Table or Matrix Wizard</span></span>  
 <span data-ttu-id="486da-147">Utilice el asistente para proporcionar un diseño inicial en el que mostrar los datos.</span><span class="sxs-lookup"><span data-stu-id="486da-147">Use the wizard to provide a starting design on which to display data.</span></span> <span data-ttu-id="486da-148">El panel de vista previa del asistente le ayudará a visualizar el resultado de las agrupaciones de datos antes de completar el diseño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="486da-148">The preview pane in the wizard helps you to visualize the result of grouping data before you complete the matrix design.</span></span>  
  
#### <a name="to-organize-data-into-groups-and-choose-a-layout-and-style"></a><span data-ttu-id="486da-149">Para organizar los datos en grupos y elegir un diseño y un estilo</span><span class="sxs-lookup"><span data-stu-id="486da-149">To organize data into groups and choose a layout and style</span></span>  
  
1.  <span data-ttu-id="486da-150">En la página **Organizar campos** , arrastre Territory desde **Campos disponibles** a **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="486da-150">On the **Arrange fields** page, drag Territory from **Available fields** to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="486da-151">Arrastre SalesDate hasta **Grupos de filas** y colóquelo debajo de Territory.</span><span class="sxs-lookup"><span data-stu-id="486da-151">Drag SalesDate to **Row groups** and place it below Territory.</span></span>  
  
     <span data-ttu-id="486da-152">El orden en el que se enumeran los campos en **Grupos de filas** define la jerarquía de grupos.</span><span class="sxs-lookup"><span data-stu-id="486da-152">The order in which fields are listed in **Row groups** defines the group hierarchy.</span></span> <span data-ttu-id="486da-153">Los pasos 1 y 2 organizan los valores de los campos primero por territorio y, después, por la fecha de las ventas.</span><span class="sxs-lookup"><span data-stu-id="486da-153">Steps 1 and 2 organize the values of the fields first by territory, and then by sales date.</span></span>  
  
3.  <span data-ttu-id="486da-154">Arrastre Subcategory a **Grupos de columnas**.</span><span class="sxs-lookup"><span data-stu-id="486da-154">Drag Subcategory to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="486da-155">Arrastre Product hasta **grupos de columnas** y, a continuación, colóquelo debajo de subcategory.</span><span class="sxs-lookup"><span data-stu-id="486da-155">Drag Product to **Column groups,** and then place below Subcategory.</span></span>  
  
     <span data-ttu-id="486da-156">El orden en que se enumeran los campos en **grupos de columnas** define la jerarquía de grupos.</span><span class="sxs-lookup"><span data-stu-id="486da-156">The order in which fields are listed in **Column groups** defines the group hierarchy.</span></span>  
  
     <span data-ttu-id="486da-157">Los pasos 3 y 4 organizan los valores de los campos primero por subcategoría y, después, por producto.</span><span class="sxs-lookup"><span data-stu-id="486da-157">Steps 3 and 4 organize the values for the fields first by subcategory, and then by product.</span></span>  
  
5.  <span data-ttu-id="486da-158">Arrastre Sales a **Valores**.</span><span class="sxs-lookup"><span data-stu-id="486da-158">Drag Sales to **Values**.</span></span>  
  
     <span data-ttu-id="486da-159">El campo Sales se resume con la función Sum, que es la función predeterminada para resumir campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="486da-159">Sales is summarized with the Sum function, the default function to summarize numeric fields.</span></span>  
  
6.  <span data-ttu-id="486da-160">Arrastre Quantity a **Valores**.</span><span class="sxs-lookup"><span data-stu-id="486da-160">Drag Quantity to **Values**.</span></span>  
  
     <span data-ttu-id="486da-161">El campo Quantity se resume con la función Sum.</span><span class="sxs-lookup"><span data-stu-id="486da-161">Quantity is summarized with the Sum function.</span></span>  
  
     <span data-ttu-id="486da-162">Los pasos 5 y 6 especifican los datos que deben mostrarse en las celdas de datos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="486da-162">Steps 5 and 6 specify the data to display in the matrix data cells.</span></span>  
  
7.  <span data-ttu-id="486da-163">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="486da-163">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="486da-164">En la página elegir el diseño, en **Opciones**, compruebe que esté seleccionada la opción **Mostrar subtotales y totales generales** .</span><span class="sxs-lookup"><span data-stu-id="486da-164">On the Choose the Layout page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
9. <span data-ttu-id="486da-165">Compruebe que esté seleccionada la opción **Bloqueado, subtotal abajo** .</span><span class="sxs-lookup"><span data-stu-id="486da-165">Verify that **Blocked, subtotal below** is selected.</span></span>  
  
10. <span data-ttu-id="486da-166">Compruebe que la opción **Expandir o contraer grupos** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="486da-166">Verify the option **Expand/collapse groups** is selected.</span></span>  
  
11. <span data-ttu-id="486da-167">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="486da-167">Click **Next**.</span></span>  
  
12. <span data-ttu-id="486da-168">En la página Elegir un estilo , en el panel Estilos , seleccione **Pizarra**.</span><span class="sxs-lookup"><span data-stu-id="486da-168">On the Choose a Style page, in the Styles pane, select **Slate**.</span></span>  
  
13. <span data-ttu-id="486da-169">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="486da-169">Click **Finish**.</span></span>  
  
     <span data-ttu-id="486da-170">La matriz se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="486da-170">The matrix is added to the design surface.</span></span> <span data-ttu-id="486da-171">El panel Grupos de filas muestra dos grupos de filas: Territory y SalesDate.</span><span class="sxs-lookup"><span data-stu-id="486da-171">The Row Groups pane shows two row groups: Territory and SalesDate.</span></span> <span data-ttu-id="486da-172">El panel Grupos de columnas muestra dos grupos de columnas: Subcategory y Product.</span><span class="sxs-lookup"><span data-stu-id="486da-172">The Column Groups pane shows two column groups: Subcategory and Product.</span></span> <span data-ttu-id="486da-173">Los datos detallados son todos los datos recuperados por la consulta del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="486da-173">Detail data is all the data that is retrieved by the dataset query.</span></span>  
  
14. <span data-ttu-id="486da-174">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-174">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="486da-175">Para cada producto que se vende en una fecha concreta, la matriz muestra la subcategoría a la que pertenece el producto y el territorio de las ventas.</span><span class="sxs-lookup"><span data-stu-id="486da-175">For each product that is sold on a specific date, the matrix shows the subcategory to which the product belongs and the territory of the sales.</span></span>  
  
##  <a name="3-format-data"></a><a name="FormatData"></a><span data-ttu-id="486da-176">3. dar formato a los datos</span><span class="sxs-lookup"><span data-stu-id="486da-176">3. Format Data</span></span>  
 <span data-ttu-id="486da-177">De forma predeterminada, los datos de resumen para el campo Sales muestran un número general y el campo SalesDate muestra información de fecha y de hora.</span><span class="sxs-lookup"><span data-stu-id="486da-177">By default, the summary data for the Sales field displays a general number and the SalesDate field displays both date and time information.</span></span> <span data-ttu-id="486da-178">Dé formato al campo Sales para mostrar el número como moneda y el campo SalesDate para mostrar solo la fecha.</span><span class="sxs-lookup"><span data-stu-id="486da-178">Format the Sales field to display the number as currency and the SalesDate field to display only the date.</span></span> <span data-ttu-id="486da-179">Alterne **Estilos de marcador de posición** para mostrar los cuadros de texto con formato y el texto de marcador de posición como valores de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="486da-179">Toggle **Placeholder Styles** to display formatted text boxes and placeholder text as sample values.</span></span>  
  
#### <a name="to-format-fields"></a><span data-ttu-id="486da-180">Para dar formato a los campos</span><span class="sxs-lookup"><span data-stu-id="486da-180">To format fields</span></span>  
  
1.  <span data-ttu-id="486da-181">Haga clic en **Diseño** para cambiar a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="486da-181">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="486da-182">Presione la tecla CTRL y, a continuación, seleccione las nueve celdas que contienen `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="486da-182">Press the Ctrl key, and then select the nine cells that contain `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="486da-183">En la pestaña **Inicio** , en el grupo **Número** , haga clic en el botón **Moneda**.</span><span class="sxs-lookup"><span data-stu-id="486da-183">On the **Home** tab, in the **Number** group, click **Currency**.</span></span> <span data-ttu-id="486da-184">Las celdas cambian para mostrar la moneda con formato.</span><span class="sxs-lookup"><span data-stu-id="486da-184">The cells changeto show the formatted currency.</span></span>  
  
     <span data-ttu-id="486da-185">Si la configuración regional es Inglés (Estados Unidos), el texto de ejemplo predeterminado es [**$12,345.00**].</span><span class="sxs-lookup"><span data-stu-id="486da-185">If your regional setting is English (United States), the default sample text is [**$12,345.00**].</span></span> <span data-ttu-id="486da-186">Si no ve un valor de moneda de ejemplo, haga clic en **estilos de marcador de posición** en el grupo **números** y, a continuación, haga clic en **valores de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="486da-186">If you do not see an example currency value, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
4.  <span data-ttu-id="486da-187">Haga clic en la celda que contiene `[SalesDate]`.</span><span class="sxs-lookup"><span data-stu-id="486da-187">Click the cell that contains `[SalesDate]`.</span></span>  
  
5.  <span data-ttu-id="486da-188">En el grupo **número** , en la lista desplegable, seleccione **fecha**.</span><span class="sxs-lookup"><span data-stu-id="486da-188">In the **Number** group, from the drop-down list, select **Date**.</span></span>  
  
     <span data-ttu-id="486da-189">La celda muestra la fecha de ejemplo **[1/31/2000]**.</span><span class="sxs-lookup"><span data-stu-id="486da-189">The cell displays the example date **[1/31/2000]**.</span></span> <span data-ttu-id="486da-190">Si no ve un valor de fecha de ejemplo, haga clic en **Estilos de marcador de posición** en el grupo **Números** y, después, haga clic en **Valores de ejemplo**.</span><span class="sxs-lookup"><span data-stu-id="486da-190">If you do not see an example date, click **Placeholder Styles** in the **Numbers** group, and then click **Sample Values**.</span></span>  
  
6.  <span data-ttu-id="486da-191">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-191">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="486da-192">Los valores de fecha solo muestran fechas y los valores de ventas se muestran como moneda.</span><span class="sxs-lookup"><span data-stu-id="486da-192">The date values display only dates and the sales values display as currency.</span></span>  
  
##  <a name="4-add-adjacent-column-group"></a><a name="AdjacentGroup"></a><span data-ttu-id="486da-193">4. Agregar grupo de columnas adyacente</span><span class="sxs-lookup"><span data-stu-id="486da-193">4. Add Adjacent Column Group</span></span>  
 <span data-ttu-id="486da-194">Puede anidar grupos de filas y de columnas en relaciones de elemento primarias o adyacentes en relaciones del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="486da-194">You can nest row and column groups in parent child relationships or adjacent in sibling relationships.</span></span>  
  
 <span data-ttu-id="486da-195">Agregue un grupo de columnas que es adyacente al grupo de columnas de Subcategory, copie las celdas para rellenar el nuevo grupo de columnas y, a continuación, utilice una expresión para crear el valor del encabezado de grupo de columnas.</span><span class="sxs-lookup"><span data-stu-id="486da-195">Add a column group that is adjacent to the Subcategory column group, copy cells to populate the new column group, and then use an expression to create the value of the column group header.</span></span>  
  
#### <a name="to-add-an-adjacent-column-group"></a><span data-ttu-id="486da-196">Para agregar un grupo de columnas adyacente</span><span class="sxs-lookup"><span data-stu-id="486da-196">To add an adjacent column group</span></span>  
  
1.  <span data-ttu-id="486da-197">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="486da-197">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="486da-198">Haga clic con el botón derecho en la celda que contiene `[Subcategory]`, señale **Agregar grupo**y luego haga clic en **Adyacente a la derecha**.</span><span class="sxs-lookup"><span data-stu-id="486da-198">Right-click the cell that contains `[Subcategory]`, point to **Add Group**, and then click **Adjacent Right**.</span></span>  
  
     <span data-ttu-id="486da-199">Se abre el cuadro de diálogo **Grupo de Tablix** .</span><span class="sxs-lookup"><span data-stu-id="486da-199">The **Tablix Group** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="486da-200">En la lista **Agrupar por** , seleccione SalesDate y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="486da-200">In the **Group By** list, select SalesDate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="486da-201">Un nuevo grupo de columnas se agrega a la izquierda del grupo de columnas de Subcategory.</span><span class="sxs-lookup"><span data-stu-id="486da-201">A new column group is added to the left of the Subcategory column group.</span></span>  
  
4.  <span data-ttu-id="486da-202">Haga clic con el botón derecho en la celda del nuevo grupo de columnas que contiene `[SalesDate],` y luego haga clic en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="486da-202">Right-click the cell in the new column group that contains `[SalesDate],` and then click **Expression**.</span></span>  
  
5.  <span data-ttu-id="486da-203">Copie la siguiente expresión en el cuadro de diálogo de expresión.</span><span class="sxs-lookup"><span data-stu-id="486da-203">Copy the following expression to expression box.</span></span>  
  
    ```  
    =WeekdayName(DatePart("w",Fields!SalesDate.Value))  
    ```  
  
     <span data-ttu-id="486da-204">Esta expresión extrae el nombre del día de la semana de la fecha de ventas.</span><span class="sxs-lookup"><span data-stu-id="486da-204">This expression extracts the weekday name from the sales date.</span></span> <span data-ttu-id="486da-205">Para más información, vea [Expresiones &#40;Generador de informes y SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="486da-205">For more information, see [Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md).</span></span>  
  
6.  <span data-ttu-id="486da-206">Haga clic con el botón derecho en la celda del grupo de columnas de Subcategory que contiene Total y luego haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="486da-206">Right-click the cell in the Subcategory column group that contains Total, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="486da-207">Haga clic con el botón derecho en la celda situada inmediatamente debajo de la celda que contiene la expresión que ha creado en el paso 5 y haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="486da-207">Right-click the cell immediately below the cell that contains the expression you created in step 5 and click **Paste**.</span></span>  
  
8.  <span data-ttu-id="486da-208">Presione la tecla CTRL.</span><span class="sxs-lookup"><span data-stu-id="486da-208">Press the Ctrl key.</span></span>  
  
9. <span data-ttu-id="486da-209">En el grupo Subcategory, haga clic en el encabezado de columna Sales y las tres celdas debajo de él, haga clic con el botón derecho y, después, haga clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="486da-209">In the Subcategory group, click the Sales column header and the three cells below it, right-click, and then click **Copy**.</span></span>  
  
10. <span data-ttu-id="486da-210">Pegue las cuatro celdas en las cuatro celdas vacías en el nuevo grupo de columnas.</span><span class="sxs-lookup"><span data-stu-id="486da-210">Paste the four cells into the four empty cells in the new column group.</span></span>  
  
11. <span data-ttu-id="486da-211">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-211">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="486da-212">El informe incluye columnas denominadas Monday y Tuesday.</span><span class="sxs-lookup"><span data-stu-id="486da-212">The report includes columns named Monday and Tuesday.</span></span> <span data-ttu-id="486da-213">El conjunto de datos solo contiene los datos de estos dos días.</span><span class="sxs-lookup"><span data-stu-id="486da-213">The dataset contains only data for these two days.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="486da-214">Si los datos incluyeran otros días, el informe también incluiría las columnas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="486da-214">If the data included other days, the report would include columns for them as well.</span></span> <span data-ttu-id="486da-215">Cada columna tiene el encabezado de columna, `Sales` y los totales de ventas por territorio.</span><span class="sxs-lookup"><span data-stu-id="486da-215">Each column has the column header, `Sales`, and sales totals by territory.</span></span>  
  
##  <a name="5-change-column-widths"></a><a name="Width"></a><span data-ttu-id="486da-216">5. cambiar el ancho de las columnas</span><span class="sxs-lookup"><span data-stu-id="486da-216">5. Change Column Widths</span></span>  
 <span data-ttu-id="486da-217">Un informe que incluye una matriz normalmente se expande horizontalmente así como verticalmente cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="486da-217">A report that includes a matrix typically expands horizontally as well as vertically when it runs.</span></span> <span data-ttu-id="486da-218">Controlar la expansión horizontal es particularmente importante si piensa exportar el informe a los formatos como Microsoft Word o Adobe PDF, que se utilizan para los informes impresos.</span><span class="sxs-lookup"><span data-stu-id="486da-218">Controlling horizontal expansion is particularly important if you plan to export the report to formats such as Microsoft Word or Adobe PDF that are used for printed reports.</span></span> <span data-ttu-id="486da-219">Si el informe se expande horizontalmente por varias páginas, el informe impreso es difícil de entender.</span><span class="sxs-lookup"><span data-stu-id="486da-219">If the report expands horizontally across multiple pages, the printed report is difficult to understand.</span></span> <span data-ttu-id="486da-220">Para minimizar la expansión horizontal, puede cambiar el tamaño de las columnas para que tengan solo el ancho necesario para mostrar los datos sin ajustar.</span><span class="sxs-lookup"><span data-stu-id="486da-220">To minimize horizontal expansion, you can resize columns to be only the width necessary to display the data without wrapping.</span></span> <span data-ttu-id="486da-221">También puede cambiar el nombre de las columnas para que sus títulos con el ancho necesario para mostrar los datos.</span><span class="sxs-lookup"><span data-stu-id="486da-221">You can also rename columns so that their titles fit the width needed to display the data.</span></span>  
  
#### <a name="to-rename-and-resize-the-columns"></a><span data-ttu-id="486da-222">Cambiar el nombre y el tamaño de las columnas</span><span class="sxs-lookup"><span data-stu-id="486da-222">To rename and resize the columns</span></span>  
  
1.  <span data-ttu-id="486da-223">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="486da-223">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="486da-224">Seleccione el texto de la columna Quantity situada más a la izquierda y, después, escriba **QTY**.</span><span class="sxs-lookup"><span data-stu-id="486da-224">Select the text in the furthest Quantity column to the left, and then type **QTY**.</span></span>  
  
     <span data-ttu-id="486da-225">El título de la columna es ahora QTY.</span><span class="sxs-lookup"><span data-stu-id="486da-225">The column title is now QTY.</span></span>  
  
3.  <span data-ttu-id="486da-226">Repita el paso 2 en las otras columnas denominadas Quantity.</span><span class="sxs-lookup"><span data-stu-id="486da-226">Repeat step 2 for the other columns named Quantity.</span></span> <span data-ttu-id="486da-227">Hay dos de ellas.</span><span class="sxs-lookup"><span data-stu-id="486da-227">There are two of them.</span></span>  
  
4.  <span data-ttu-id="486da-228">Haga clic en la matriz para que los identificadores de columna y de fila aparezcan encima y al lado de la matriz.</span><span class="sxs-lookup"><span data-stu-id="486da-228">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
     <span data-ttu-id="486da-229">Las barras grises situadas en la parte superior y en el lado de la tabla son los identificadores de fila y de columna.</span><span class="sxs-lookup"><span data-stu-id="486da-229">The gray bars along the top and side of the table are the column and row handles.</span></span>  
  
5.  <span data-ttu-id="486da-230">Para cambiar el tamaño de la columna QTY situada más a la izquierda, seleccione la línea entre los identificadores de columna para que el cursor cambie a una flecha doble.</span><span class="sxs-lookup"><span data-stu-id="486da-230">To resize the furthest QTY column to the left, point to the line between column handles so that the cursor changes into a double arrow.</span></span> <span data-ttu-id="486da-231">Arrastre la columna hacia la izquierda hasta que el ancho sea de 1/2 pulgada.</span><span class="sxs-lookup"><span data-stu-id="486da-231">Drag the column towards the left until it is 1/2 inch wide.</span></span>  
  
     <span data-ttu-id="486da-232">Un ancho de columna de 1/2 pulgada es adecuado para mostrar la cantidad.</span><span class="sxs-lookup"><span data-stu-id="486da-232">A column width of 1/2 inch is adequate to display the quantity.</span></span>  
  
6.  <span data-ttu-id="486da-233">Repita el paso 5 en las otras columnas denominadas QTY.</span><span class="sxs-lookup"><span data-stu-id="486da-233">Repeat step 5 for the other columns named QTY.</span></span>  
  
7.  <span data-ttu-id="486da-234">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-234">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="486da-235">Las columnas del informe que contiene las cantidades se denominan ahora QTY y son más estrechas.</span><span class="sxs-lookup"><span data-stu-id="486da-235">The columns in the report that contains quantities are now named QTY and the columns are narrower.</span></span>  
  
##  <a name="6-merge-matrix-cells"></a><a name="MergeCells"></a><span data-ttu-id="486da-236">6. combinar las celdas de la matriz</span><span class="sxs-lookup"><span data-stu-id="486da-236">6. Merge Matrix Cells</span></span>  
 <span data-ttu-id="486da-237">El área de la esquina está en la esquina superior izquierda de la matriz</span><span class="sxs-lookup"><span data-stu-id="486da-237">The corner area is in the upper left corner of the matrix.</span></span> <span data-ttu-id="486da-238">Dependiendo del número de grupos de filas y columnas de la matriz, el número de celdas en el área de la esquina varía.</span><span class="sxs-lookup"><span data-stu-id="486da-238">Depending on the number of row and column groups in the matrix, the number of cells in the corner area varies.</span></span> <span data-ttu-id="486da-239">La matriz generada en este tutorial tiene cuatro celdas en su área de esquina.</span><span class="sxs-lookup"><span data-stu-id="486da-239">The matrix, built in this tutorial, has four cells in its corner area.</span></span> <span data-ttu-id="486da-240">Las celdas se disponen en dos filas y dos columnas, reflejando la profundidad de las jerarquías de grupos de filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="486da-240">The cells are arranged in two rows and two columns, reflecting the depth of row and column group hierarchies.</span></span> <span data-ttu-id="486da-241">Las cuatro celdas no se utilizan en este informe y los combinará en una.</span><span class="sxs-lookup"><span data-stu-id="486da-241">The four cells are not used in this report and you will merge them into one.</span></span>  
  
#### <a name="to-merge-matrix-cells"></a><span data-ttu-id="486da-242">Para combinar las celdas de la matriz</span><span class="sxs-lookup"><span data-stu-id="486da-242">To merge matrix cells</span></span>  
  
1.  <span data-ttu-id="486da-243">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="486da-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="486da-244">Haga clic en la matriz para que los identificadores de columna y de fila aparezcan encima y al lado de la matriz.</span><span class="sxs-lookup"><span data-stu-id="486da-244">Click the matrix so that column and row handles appear above and next to the matrix.</span></span>  
  
3.  <span data-ttu-id="486da-245">Presione la tecla CTRL y, a continuación, seleccione las cuatro celdas de la esquina.</span><span class="sxs-lookup"><span data-stu-id="486da-245">Press the Ctrl key, and then select the four corner cells.</span></span>  
  
4.  <span data-ttu-id="486da-246">Haga clic con el botón secundario en las celdas y haga clic en **combinar celdas**.</span><span class="sxs-lookup"><span data-stu-id="486da-246">Right-click the cells and then click **Merge Cells**.</span></span>  
  
5.  <span data-ttu-id="486da-247">Haga clic con el botón secundario en la celda de la esquina y después haga clic en **propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="486da-247">Right-click the corner cell, and then click **Text Box Properties**.</span></span>  
  
6.  <span data-ttu-id="486da-248">Haga clic en la pestaña **Rellenar** .</span><span class="sxs-lookup"><span data-stu-id="486da-248">Click the **Fill** tab.</span></span>  
  
7.  <span data-ttu-id="486da-249">Haga clic en el botón (***FX***) para el **color de relleno**.</span><span class="sxs-lookup"><span data-stu-id="486da-249">Click the (***fx***) button for **Fill color**.</span></span>  
  
8.  <span data-ttu-id="486da-250">Copie y pegue la expresión siguiente en el cuadro de diálogo de expresión.</span><span class="sxs-lookup"><span data-stu-id="486da-250">Copy and paste the following expression in the expression box.</span></span>  
  
    ```  
    #96a4b2  
    ```  
  
     <span data-ttu-id="486da-251">Es el valor hexadecimal de RGB para un color del azul deshabilitado utilizado en el estilo Pizarra.</span><span class="sxs-lookup"><span data-stu-id="486da-251">This is the RGB hex value for a gray blue color used in the Slate style.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="486da-252">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-252">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="486da-253">La matriz de la esquina superior es una celda única y tiene el mismo color que las celdas del grupo de filas y columnas.</span><span class="sxs-lookup"><span data-stu-id="486da-253">The upper corner matrix is a single cell and has the same color as the row group and column group cells.</span></span>  
  
##  <a name="7-add-a-report-header-and-report-title"></a><a name="HeaderTitle"></a><span data-ttu-id="486da-254">7. agregar un encabezado de informe y un título de informe</span><span class="sxs-lookup"><span data-stu-id="486da-254">7. Add a Report Header and Report Title</span></span>  
 <span data-ttu-id="486da-255">Los títulos de informe aparecen en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="486da-255">A report title appears at the top of the report.</span></span> <span data-ttu-id="486da-256">Puede situar el título del informe en un encabezado de informe o, si el informe no lo utiliza, en un cuadro de texto en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-256">You can place the report title in a report header or if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="486da-257">En este tutorial, quitará el cuadro de texto de la parte superior del informe y agregará un título al encabezado.</span><span class="sxs-lookup"><span data-stu-id="486da-257">In this tutorial, you will remove the text box at the top of the report and add a title to the header.</span></span>  
  
#### <a name="to-add-a-report-header-and-report-title"></a><span data-ttu-id="486da-258">Para agregar un encabezado y un título del informe</span><span class="sxs-lookup"><span data-stu-id="486da-258">To add a report header and report title</span></span>  
  
1.  <span data-ttu-id="486da-259">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="486da-259">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="486da-260">Haga clic en el cuadro de texto de la parte superior del cuerpo del informe que contiene **haga clic para agregar título**y, a continuación, presione la tecla Supr.</span><span class="sxs-lookup"><span data-stu-id="486da-260">Click the text box at the top of the report body that contains **Click to add title**, and then press the Delete key.</span></span>  
  
3.  <span data-ttu-id="486da-261">En la pestaña **Insertar** de la cinta de opciones, haga clic en **encabezado** y, a continuación, haga clic en **Agregar encabezado**.</span><span class="sxs-lookup"><span data-stu-id="486da-261">On the **Insert** tab of the ribbon, click **Header** and then click **Add Header**.</span></span>  
  
     <span data-ttu-id="486da-262">Se agrega un encabezado a la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-262">A header is added to the top of the report body.</span></span>  
  
4.  <span data-ttu-id="486da-263">En la pestaña **Insertar** , haga clic en **Cuadro de texto**y luego arrastre un cuadro de texto al encabezado del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-263">On the **Insert** tab, click **Text Box**, and then drag a text box inside the report header.</span></span> <span data-ttu-id="486da-264">Haga un cuadro de texto de aproximadamente 6 pulgadas de largo y 3/4 de pulgada de alto, y colóquelo en el lado izquierdo del encabezado del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-264">Make the text box about 6 inches long and 3/4 inch tall and place it on the left side of the report header.</span></span>  
  
5.  <span data-ttu-id="486da-265">En el cuadro de texto, escriba **Ventas por territorio, Subcategoría y Día**.</span><span class="sxs-lookup"><span data-stu-id="486da-265">In the text box, type **Sales by Territory, Subcategory, and Day**.</span></span>  
  
6.  <span data-ttu-id="486da-266">Seleccione el texto que escribió, haga clic con el botón secundario y, a continuación, haga clic en **propiedades de texto**.</span><span class="sxs-lookup"><span data-stu-id="486da-266">Select the text you typed, right-click, and then click **Text Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="486da-267">Para dar formato al mismo tiempo a los caracteres, deben ser contiguos.</span><span class="sxs-lookup"><span data-stu-id="486da-267">To format characters at the same time, they must be contiguous.</span></span>  
  
7.  <span data-ttu-id="486da-268">En el cuadro de diálogo **propiedades de texto** , haga clic en **fuente**.</span><span class="sxs-lookup"><span data-stu-id="486da-268">In the **Text Properties** dialog box, click **Font**.</span></span>  
  
8.  <span data-ttu-id="486da-269">En la lista **fuente** , seleccione **Times New Roman**; en **tamaño** , **Seleccione 24 PT**, en **color** seleccione **granate**y en **estilo** seleccione **cursiva**.</span><span class="sxs-lookup"><span data-stu-id="486da-269">In the **Font** list, select **Times New Roman**; in **Size** select **24 pt**, in **Color** select **Maroon**, and in **Style** select **Italic**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="486da-270">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-270">Click **Run** to preview the report.</span></span>  
  
 <span data-ttu-id="486da-271">El informe incluye un título de informe en el encabezado del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-271">The report includes a report title in the report header.</span></span>  
  
##  <a name="8-save-the-report"></a><a name="Save"></a><span data-ttu-id="486da-272">8. guardar el informe</span><span class="sxs-lookup"><span data-stu-id="486da-272">8. Save the Report</span></span>  
 <span data-ttu-id="486da-273">Puede guardar los informes en un servidor de informes, en una biblioteca de SharePoint o en su equipo.</span><span class="sxs-lookup"><span data-stu-id="486da-273">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="486da-274">En este tutorial, guarde el informe en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="486da-274">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="486da-275">Si no tiene acceso a un servidor de informes, guarde el informe en su equipo.</span><span class="sxs-lookup"><span data-stu-id="486da-275">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="486da-276">Para guardar el informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="486da-276">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="486da-277">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="486da-277">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="486da-278">Haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="486da-278">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="486da-279">Seleccione o escriba el nombre del servidor de informes donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="486da-279">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="486da-280">Aparecerá el mensaje "Conectando con el servidor de informes".</span><span class="sxs-lookup"><span data-stu-id="486da-280">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="486da-281">Una vez completada la conexión, verá el contenido de la carpeta de informes que el administrador del servidor de informes especificó como ubicación predeterminada para los informes.</span><span class="sxs-lookup"><span data-stu-id="486da-281">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="486da-282">En **Nombre**, reemplace el nombre predeterminado por **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="486da-282">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
5.  <span data-ttu-id="486da-283">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="486da-283">Click **Save**.</span></span>  
  
 <span data-ttu-id="486da-284">El informe se guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="486da-284">The report is saved to the report server.</span></span> <span data-ttu-id="486da-285">El nombre del servidor de informes al que está conectado aparecerá en la barra de estado en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="486da-285">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="486da-286">Para guardar el informe en el equipo</span><span class="sxs-lookup"><span data-stu-id="486da-286">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="486da-287">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="486da-287">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="486da-288">Haga clic en **Escritorio**, **Mis documentos**o **Mi PC**y vaya a la carpeta donde desea guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="486da-288">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="486da-289">En **Nombre**, reemplace el nombre predeterminado por **SalesByTerritorySubcategory**.</span><span class="sxs-lookup"><span data-stu-id="486da-289">In **Name**, replace the default name with **SalesByTerritorySubcategory**.</span></span>  
  
4.  <span data-ttu-id="486da-290">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="486da-290">Click **Save**.</span></span>  
  
##  <a name="9-optional-rotate-text-box-270-degrees"></a><a name="RotateTextBox"></a><span data-ttu-id="486da-291">9. (opcional) girar el cuadro de texto 270 grados</span><span class="sxs-lookup"><span data-stu-id="486da-291">9. (Optional) Rotate Text Box 270 Degrees</span></span>  
 <span data-ttu-id="486da-292">Un informe con matrices se puede expandir horizontal y verticalmente cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="486da-292">A report with matrices can expand horizontally and vertically when it runs.</span></span> <span data-ttu-id="486da-293">Girando los cuadros de texto verticalmente o 270 grados, puede ahorrar espacio horizontal.</span><span class="sxs-lookup"><span data-stu-id="486da-293">By rotating text boxes vertically, or 270 degrees, you can save horizontal space.</span></span> <span data-ttu-id="486da-294">El informe representado se hace más estrecho y, si se exporta a un formato como Microsoft Word, tendrá más posibilidades de ajustar en una página impresa.</span><span class="sxs-lookup"><span data-stu-id="486da-294">The rendered report is then narrower and if exported to a format such as Microsoft Word, will be more likely to fit on a printed page.</span></span>  
  
 <span data-ttu-id="486da-295">Un cuadro de texto también puede mostrar el texto como horizontal o como, vertical (de arriba abajo).</span><span class="sxs-lookup"><span data-stu-id="486da-295">A text box can also display text as horizontal, vertical (top to bottom).</span></span> <span data-ttu-id="486da-296">Para más información, vea [Cuadros de texto &#40;Generador de informes y SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="486da-296">For more information, see [Text Boxes &#40;Report Builder and SSRS&#41;](report-design/text-boxes-report-builder-and-ssrs.md).</span></span>  
  
#### <a name="to-rotate-text-box-270-degrees"></a><span data-ttu-id="486da-297">Para girar el cuadro de texto 270 grados</span><span class="sxs-lookup"><span data-stu-id="486da-297">To rotate text box 270 degrees</span></span>  
  
1.  <span data-ttu-id="486da-298">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="486da-298">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="486da-299">Haga clic en la celda que contiene `[Territory].`.</span><span class="sxs-lookup"><span data-stu-id="486da-299">Click the cell that contains `[Territory].`</span></span>  
  
3.  <span data-ttu-id="486da-300">En el panel Propiedades, busque la propiedad WritingMode y, en la lista desplegable, seleccione **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="486da-300">In the Properties pane, locate the WritingMode property and in its drop-down list, select **Rotate270**.</span></span>  
  
     <span data-ttu-id="486da-301">Si el panel Propiedades no está abierto, haga clic en la pestaña **Ver** de la cinta de opciones y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="486da-301">If the Properties pane is not open, click the **View** tab of the ribbon, and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="486da-302">Compruebe que la propiedad CanGrow está establecida en `True` .</span><span class="sxs-lookup"><span data-stu-id="486da-302">Verify that the CanGrow property is set to `True`.</span></span>  
  
5.  <span data-ttu-id="486da-303">Cambie el tamaño de la columna Territory para que tenga un ancho de 1/2 pulgada y elimine el título de columna.</span><span class="sxs-lookup"><span data-stu-id="486da-303">Resize the Territory column to be 1/2 inch wide and delete the column title.</span></span>  
  
6.  <span data-ttu-id="486da-304">Haga clic en **Ejecutar** para obtener una vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="486da-304">Click **Run** to preview your report.</span></span>  
  
 <span data-ttu-id="486da-305">El nombre del territorio se escribe verticalmente, de arriba abajo.</span><span class="sxs-lookup"><span data-stu-id="486da-305">The territory name is written vertically, bottom to top.</span></span> <span data-ttu-id="486da-306">El alto del grupo de fila de Territory varía por la longitud del nombre del territorio.</span><span class="sxs-lookup"><span data-stu-id="486da-306">The height of the Territory row group varies by the length of the territory name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="486da-307">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="486da-307">Next Steps</span></span>  
 <span data-ttu-id="486da-308">Concluye así el tutorial para sobre el modo de crear un informe de matriz.</span><span class="sxs-lookup"><span data-stu-id="486da-308">This concludes the tutorial for how to create a matrix report.</span></span> <span data-ttu-id="486da-309">Para más información sobre las matrices, consulte [tablas, matrices y listas &#40;generador de informes y ssrs&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [matrices &#40;Generador de informes y SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [áreas de la región de datos Tablix &#40;generador de informes y SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md)y [celdas, filas y columnas de la región de datos Tablix &#40;generador de informes&#41; y SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="486da-309">For more information about matrices, see [Tables, Matrices, and Lists &#40;Report Builder and SSRS&#41;](report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md), [Matrices &#40;Report Builder and SSRS&#41;](report-design/create-a-matrix-report-builder-and-ssrs.md), [Tablix Data Region Areas &#40;Report Builder and SSRS&#41;](report-design/tablix-data-region-areas-report-builder-and-ssrs.md), and [Tablix Data Region Cells, Rows, and Columns &#40;Report Builder&#41; and SSRS](report-design/tablix-data-region-cells-rows-and-columns-report-builder-and-ssrs.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486da-310">Consulte también</span><span class="sxs-lookup"><span data-stu-id="486da-310">See Also</span></span>  
 <span data-ttu-id="486da-311">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="486da-311">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 [<span data-ttu-id="486da-312">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="486da-312">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
