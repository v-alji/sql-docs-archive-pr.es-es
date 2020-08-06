---
title: 'Tutorial: Dar formato a texto (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 67d8513e-8a70-464b-b87f-e91d010cfd82
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c96b500f8aa30b77c78f75ccd1342398fd44eb2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748598"
---
# <a name="tutorial-format-text-report-builder"></a><span data-ttu-id="bb2f1-102">Tutorial: Dar formato a texto (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="bb2f1-102">Tutorial: Format Text (Report Builder)</span></span>
  <span data-ttu-id="bb2f1-103">En este tutorial, puede practicar el proceso de dar formato al texto de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-103">In this tutorial, you can practice formatting text in various ways.</span></span> <span data-ttu-id="bb2f1-104">Después de configurar el informe en blanco con el origen de datos y el conjunto de datos, puede escoger y elegir los pasos que desea explorar.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-104">After you set up the blank report with the data source and dataset, you can pick and choose the steps that you want to explore.</span></span>  
  
 <span data-ttu-id="bb2f1-105">En la siguiente ilustración se muestra un informe similar al que creará.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-105">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="bb2f1-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span><span class="sxs-lookup"><span data-stu-id="bb2f1-106">![rs_FormatTextFinal](../../2014/tutorials/media/rs-formattextfinal.gif "rs_FormatTextFinal")</span></span>  
  
 <span data-ttu-id="bb2f1-107">En un paso puede cometer un error voluntario para ver por qué es un error.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-107">In one step, you make a mistake on purpose so you can see why it is a mistake.</span></span> <span data-ttu-id="bb2f1-108">A continuación, corrija el error para lograr el efecto deseado.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-108">Then you correct the mistake to achieve the desired effect.</span></span>  
  
 <span data-ttu-id="bb2f1-109">Una versión mejorada del informe que creará en este tutorial está disponible como informe de ejemplo del Generador de informes de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb2f1-109">An enhanced version of the report you create in this tutorial is available as a sample [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="bb2f1-110">Para obtener más información acerca de cómo descargar este informe de ejemplo y otros, vea [generador de informes informes de ejemplo](https://go.microsoft.com/fwlink/?LinkId=184851).</span><span class="sxs-lookup"><span data-stu-id="bb2f1-110">For more information about downloading this sample report and others, see [Report Builder sample reports](https://go.microsoft.com/fwlink/?LinkId=184851).</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="bb2f1-111">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="bb2f1-111">What You Will Learn</span></span>  
  
### <a name="set-up-the-report"></a><span data-ttu-id="bb2f1-112">Configurar el informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-112">Set Up the Report</span></span>  
 1. [<span data-ttu-id="bb2f1-113">Crear un informe en blanco con un origen de datos y un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="bb2f1-113">Create a Blank Report with a Data Source and Dataset</span></span>](#CreateReport)  
  
 2. [<span data-ttu-id="bb2f1-114">Agregar un campo a la superficie de diseño del informe(incorrectamente y, luego, correctamente)</span><span class="sxs-lookup"><span data-stu-id="bb2f1-114">Add a Field to the Report Design Surface (Incorrectly, then Correctly)</span></span>](#AddField)  
  
 3. [<span data-ttu-id="bb2f1-115">Agregar una tabla al informe Superficie de diseño</span><span class="sxs-lookup"><span data-stu-id="bb2f1-115">Add a Table to the Report Design Surface</span></span>](#AddTable)  
  
### <a name="pick-and-choose"></a><span data-ttu-id="bb2f1-116">Escoger y elegir</span><span class="sxs-lookup"><span data-stu-id="bb2f1-116">Pick and Choose</span></span>  
 [<span data-ttu-id="bb2f1-117">Agregar un hipervínculo al informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-117">Add a Hyperlink to the Report</span></span>](#AddHyperlink)  
  
 [<span data-ttu-id="bb2f1-118">Girar texto en el informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-118">Rotate Text in the Report</span></span>](#RotateText)  
  
 [<span data-ttu-id="bb2f1-119">Mostrar texto con formato HTML</span><span class="sxs-lookup"><span data-stu-id="bb2f1-119">Displaying Text with HTML Formatting</span></span>](#FormatHTML)  
  
 [<span data-ttu-id="bb2f1-120">Formato de moneda</span><span class="sxs-lookup"><span data-stu-id="bb2f1-120">Format Currency</span></span>](#FormatCurrency)  
  
 [<span data-ttu-id="bb2f1-121">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-121">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="bb2f1-122">Tiempo estimado para completar este tutorial: 20 minutos.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-122">Estimated time to complete this tutorial: 20 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb2f1-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb2f1-123">Requirements</span></span>  
 <span data-ttu-id="bb2f1-124">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="bb2f1-124">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="create-a-blank-report-with-a-data-source-and-dataset"></a><a name="CreateReport"></a><span data-ttu-id="bb2f1-125">Crear un informe en blanco con un origen de datos y un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="bb2f1-125">Create a Blank Report with a Data Source and Dataset</span></span>  
  
#### <a name="to-create-a-blank-report"></a><span data-ttu-id="bb2f1-126">Para crear un informe en blanco</span><span class="sxs-lookup"><span data-stu-id="bb2f1-126">To create a blank report</span></span>  
  
1.  <span data-ttu-id="bb2f1-127">Haga clic en **Inicio**, seleccione **Programas**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Generador de informes**y luego haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-127">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb2f1-128">Debería aparecer el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="bb2f1-128">The **Getting Started** dialog box should appear.</span></span> <span data-ttu-id="bb2f1-129">Si no hace, en el botón Generador de informes haga clic **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-129">If it does not, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="bb2f1-130">En el panel izquierdo del cuadro de diálogo **Introducción** , compruebe que **Nuevo informe** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-130">In the left pane of the **Getting Started** dialog box, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="bb2f1-131">En el panel derecho, haga clic en **Informe en blanco**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-131">In the right pane, click **Blank Report**.</span></span>  
  
#### <a name="to-create-a-data-source"></a><span data-ttu-id="bb2f1-132">Para crear un origen de datos</span><span class="sxs-lookup"><span data-stu-id="bb2f1-132">To create a data source</span></span>  
  
1.  <span data-ttu-id="bb2f1-133">En el panel datos de informe, haga clic en **nuevo**y, a continuación, haga clic en **origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-133">In the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="bb2f1-134">En el cuadro **Nombre** , escriba: **TextDataSource**</span><span class="sxs-lookup"><span data-stu-id="bb2f1-134">In the **Name** box, type: **TextDataSource**</span></span>  
  
3.  <span data-ttu-id="bb2f1-135">Haga clic en **Usar una conexión incrustada en mi informe**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-135">Click **Use a connection embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="bb2f1-136">Compruebe que el tipo de conexión es Microsoft SQL Server y, a continuación, en el cuadro **cadena de conexión** , escriba: \*\*origen de datos = \<servername> \*\*</span><span class="sxs-lookup"><span data-stu-id="bb2f1-136">Verify that the connection type is Microsoft SQL Server, and then in the **Connection string** box type: **Data Source = \<servername>**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb2f1-137">La expresión \<servername>, por ejemplo Report001, especifica un equipo en el que se ha instalado una instancia del motor de SQL Server Database.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-137">The expression \<servername>, for example Report001, specifies a computer on which an instance of the SQL Server Database Engine is installed.</span></span> <span data-ttu-id="bb2f1-138">Este tutorial no necesita datos concretos; solo necesita una conexión a una base de datos de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bb2f1-138">This tutorial does not need specific data; it just needs a connection to a [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] database.</span></span> <span data-ttu-id="bb2f1-139">Si ya tiene una conexión a un origen de datos enumerada bajo **Conexiones de origen de datos**, puede seleccionarla e ir al procedimiento siguiente, "Para crear un conjunto de datos".</span><span class="sxs-lookup"><span data-stu-id="bb2f1-139">If you already have a data source connection listed under **Data Source Connections**, you can select it and go to the next procedure, "To create a dataset."</span></span> <span data-ttu-id="bb2f1-140">Para obtener más información, consulte [Maneras alternativas de obtener una conexión de datos &#40;Generador de informes&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="bb2f1-140">For more information, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-create-a-dataset"></a><span data-ttu-id="bb2f1-141">Para crear un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="bb2f1-141">To create a dataset</span></span>  
  
1.  <span data-ttu-id="bb2f1-142">En el panel Datos de informe, haga clic en **Nuevo**y, a continuación, haga clic en **Conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-142">In the Report Data pane, click **New**, and then click **Dataset**.</span></span>  
  
2.  <span data-ttu-id="bb2f1-143">Compruebe que el origen de datos es **TextDataSource**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-143">Verify that the data source is **TextDataSource**.</span></span>  
  
3.  <span data-ttu-id="bb2f1-144">En el cuadro **Nombre** , escriba: **TextDataset.**</span><span class="sxs-lookup"><span data-stu-id="bb2f1-144">In the **Name** box, type: **TextDataset.**</span></span>  
  
4.  <span data-ttu-id="bb2f1-145">Compruebe que el tipo de consulta **Texto** está seleccionado, y, a continuación, haga clic en **Diseñador de consultas**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-145">Verify that the **Text** query type is selected, and then click **Query Designer**.</span></span>  
  
5.  <span data-ttu-id="bb2f1-146">Haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-146">Click **Edit as Text**.</span></span>  
  
6.  <span data-ttu-id="bb2f1-147">Pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="bb2f1-147">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(16996.60 AS money) AS Sales, 68 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13747.25 AS money) AS Sales, 55 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Carrying Case' as Product, CAST(9248.15 AS money) As Sales, 37 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1350.00 AS money) AS Sales, 18 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1800.00 AS money) AS Sales, 24 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1125.00 AS money) AS Sales, 15 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1147.50 AS money) AS Sales, 17 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,  'Lens Adapter' as Product, CAST(742.50 AS money) AS Sales, 11 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1417.50 AS money) AS Sales, 21 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(13497.30 AS money) AS Sales, 54 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(11997.60 AS money) AS Sales, 48 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory, 'Carrying Case' as Product, CAST(10247.95 AS money) As Sales, 41 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory, 'Tripod' as Product, CAST(1200.00 AS money) AS Sales, 16 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(2025.00 AS money) AS Sales, 27 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Tripod' as Product, CAST(1425.00 AS money) AS Sales, 19 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(887.50 AS money) AS Sales, 13 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Accessories' as Subcategory, 'Lens Adapter' as Product, CAST(607.50 AS money) AS Sales, 9 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Accessories' as Subcategory,'Lens Adapter' as Product, CAST(1215.00 AS money) AS Sales, 18 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(10191.00 AS money) AS Sales, 79 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8772.00 AS money) AS Sales, 68 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(10578.00 AS money) AS Sales, 82 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(7218.10 AS money) AS Sales, 38 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory,'Digital' as Subcategory, 'Slim Digital' as Product, CAST(8357.80 AS money) AS Sales, 44 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-05' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory,'Digital' as Subcategory,'Slim Digital' as Product, CAST(9307.55 AS money) AS Sales, 49 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(3870.00 AS money) AS Sales, 30 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory,'Compact Digital' as Product, CAST(5805.00 AS money) AS Sales, 45 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate,  'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Compact Digital' as Product, CAST(8643.00 AS money) AS Sales, 67 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Lauren Johnson' as FullName,'Central' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(9877.40 AS money) AS Sales, 52 as Quantity, 'Installing Report Builder' as LinkText, 'https://go.microsoft.com/fwlink/?LinkId=154882' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Warren Pal' as FullName,'North' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(12536.70 AS money) AS Sales, 66 as Quantity, 'Getting Started with Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=160556' AS URL  
    UNION SELECT CAST('2009-01-06' AS date) as SalesDate, 'Fernando Ross' as FullName,'South' as Territory, 'Digital' as Subcategory, 'Slim Digital' as Product, CAST(6648.25 AS money) AS Sales, 35 as Quantity, 'What is New in Report Builder' as Link, 'https://go.microsoft.com/fwlink/?LinkId=165064' AS URL  
    ```  
  
7.  <span data-ttu-id="bb2f1-148">Haga clic en Ejecutar (**!**) para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-148">Click Run (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="bb2f1-149">Los resultados de la consulta son los datos disponibles para mostrarse en su informe.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-149">The query results are the data available to display in your report.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="add-a-field-to-the-report-design-surface"></a><a name="AddField"></a><span data-ttu-id="bb2f1-150">Agregar un campo al informe Superficie de diseño</span><span class="sxs-lookup"><span data-stu-id="bb2f1-150">Add a Field to the Report Design Surface</span></span>  
 <span data-ttu-id="bb2f1-151">Si desea que un campo del conjunto de datos aparezca en un informe, su primer impulso puede ser arrastrarlo hasta la superficie de diseño directamente.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-151">If you want a field from your dataset to appear in a report, your first impulse may be to drag it directly to the design surface.</span></span> <span data-ttu-id="bb2f1-152">En este ejercicio se describe por qué eso no funciona y lo que se ha de hacer en su lugar.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-152">This exercise points out why that doesn't work and what to do instead.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-wrong-result"></a><span data-ttu-id="bb2f1-153">Para agregar un campo al informe (y obtener el resultado incorrecto)</span><span class="sxs-lookup"><span data-stu-id="bb2f1-153">To add a field to the report (and get the wrong result)</span></span>  
  
1.  <span data-ttu-id="bb2f1-154">Arrastre el campo **FullName** desde el panel Datos de informe hasta la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-154">Drag the **FullName** field from the Report Data pane to the design surface.</span></span>  
  
     <span data-ttu-id="bb2f1-155">El Generador de informes crea un cuadro de texto con una expresión en él, representada como \<Expr>.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-155">Report Builder creates a text box with an expression in it, represented as \<Expr>.</span></span>  
  
2.  <span data-ttu-id="bb2f1-156">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-156">Click **Run**.</span></span>  
  
     <span data-ttu-id="bb2f1-157">Tenga en cuenta que solo hay un registro, **Fernando Ross**, que es alfabéticamente el primer registro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-157">Note that there is just one record, **Fernando Ross**, which is alphabetically the first record in the query.</span></span> <span data-ttu-id="bb2f1-158">El campo no se repite para mostrar los otros registros de ese campo.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-158">The field does not repeat to show the other records in that field.</span></span>  
  
3.  <span data-ttu-id="bb2f1-159">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-159">Click **Design** to return to design view.</span></span>  
  
4.  <span data-ttu-id="bb2f1-160">Seleccione la expresión \<Expr> en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-160">Select the expression \<Expr> in the text box.</span></span>  
  
5.  <span data-ttu-id="bb2f1-161">En el panel Propiedades, para la propiedad **Value** verá lo siguiente (si no ve el panel Propiedades, en la pestaña **Ver** active **Propiedades**):</span><span class="sxs-lookup"><span data-stu-id="bb2f1-161">In the Properties pane, for the **Value** property, you see the following (if you don't see the Properties pane, on the **View** tab, check **Properties**):</span></span>  
  
    ```  
    =First(Fields!FullName.Value, "TextDataSet")  
    ```  
  
     <span data-ttu-id="bb2f1-162">La función `First` está diseñada para recuperar solo el primer valor de un campo y es lo que ha hecho.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-162">The `First` function is designed to retrieve only the first value in a field, and that is what it has done.</span></span>  
  
     <span data-ttu-id="bb2f1-163">Al arrastrar el campo hacia la superficie de diseño directamente, se creó un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-163">Dragging the field directly to the design surface created a text box.</span></span> <span data-ttu-id="bb2f1-164">Por sí mismos, los cuadros de texto no son regiones de datos, de modo que no muestran datos de un conjunto de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-164">Text boxes by themselves are not data regions, so they do not display data from a report dataset.</span></span> <span data-ttu-id="bb2f1-165">Los cuadros de texto de las regiones de datos, como tablas, matrices y listas, muestran datos.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-165">Text boxes in data regions, such as tables, matrices, and lists, do display data.</span></span>  
  
6.  <span data-ttu-id="bb2f1-166">Seleccione el cuadro de texto (si tiene la expresión seleccionada, presione ESC para seleccionarlo) y presione la tecla SUPRIMIR.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-166">Select the text box (if you have the expression selected, press ESC to select the text box), and press the DELETE key.</span></span>  
  
#### <a name="to-add-a-field-to-the-report-and-get-the-right-result"></a><span data-ttu-id="bb2f1-167">Para agregar un campo al informe (y obtener el resultado correcto)</span><span class="sxs-lookup"><span data-stu-id="bb2f1-167">To add a field to the report (and get the right result)</span></span>  
  
1.  <span data-ttu-id="bb2f1-168">En la pestaña **Insertar** de la cinta de opciones, en el área **Regiones de datos** , haga clic en **Lista**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-168">On the **Insert** tab of the ribbon, in the **Data Regions** area, click **List**.</span></span> <span data-ttu-id="bb2f1-169">Haga clic en la superficie de diseño y, a continuación, arrástrela para crear un cuadro que tenga aproximadamente dos pulgadas de ancho y una de alto.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-169">Click the design surface, and then drag to create a box that about two inches wide and one inch tall.</span></span>  
  
2.  <span data-ttu-id="bb2f1-170">Arrastre el campo **FullName** desde el panel Datos de informe hasta el cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-170">Drag the **FullName** field from the Report Data pane to the list box.</span></span>  
  
     <span data-ttu-id="bb2f1-171">Esta vez el Generador de informes crea un cuadro de texto con la expresión `[FullName]` en él.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-171">This time Report Builder creates a text box with the expression `[FullName]` in it.</span></span>  
  
3.  <span data-ttu-id="bb2f1-172">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-172">Click **Run**.</span></span>  
  
     <span data-ttu-id="bb2f1-173">Tenga en cuenta que esta vez el cuadro se repite para mostrar todos los registros de la consulta.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-173">Note that this time the box repeats to show all the records in the query.</span></span>  
  
4.  <span data-ttu-id="bb2f1-174">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-174">Click **Design** to return to design view.</span></span>  
  
5.  <span data-ttu-id="bb2f1-175">Seleccione la expresión en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-175">Select the expression in the text box.</span></span>  
  
6.  <span data-ttu-id="bb2f1-176">En el panel Propiedades, para la propiedad **Value** , ve lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bb2f1-176">In the Properties pane, for the **Value** property, you see the following:</span></span>  
  
    ```  
    =Fields!FullName.Value  
    ```  
  
     <span data-ttu-id="bb2f1-177">Arrastrando el cuadro de texto hasta la región de datos de la lista, muestra los datos que hay en el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-177">By dragging the text box to the list data region, you display the data that is in the dataset.</span></span>  
  
7.  <span data-ttu-id="bb2f1-178">Seleccione el cuadro de lista y presione la tecla ELIMINAR.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-178">Select the list box and press the DELETE key.</span></span>  
  
##  <a name="add-a-table-to-the-report-design-surface"></a><a name="AddTable"></a><span data-ttu-id="bb2f1-179">Agregar una tabla al informe Superficie de diseño</span><span class="sxs-lookup"><span data-stu-id="bb2f1-179">Add a Table to the Report Design Surface</span></span>  
 <span data-ttu-id="bb2f1-180">Cree esta tabla para tener un lugar donde colocar los hipervínculos y el texto girado.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-180">Create this table so that you'll have a place to put hyperlinks and rotated text.</span></span>  
  
#### <a name="to-add-a-table-to-the-report"></a><span data-ttu-id="bb2f1-181">Para agregar una tabla al informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-181">To add a table to the report</span></span>  
  
1.  <span data-ttu-id="bb2f1-182">En el menú **Insertar** , haga clic en **tabla**y, a continuación, haga clic en **Asistente para tablas**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-182">On the **Insert** menu, click **Table**, and then click **Table Wizard**.</span></span>  
  
2.  <span data-ttu-id="bb2f1-183">En la página **elegir un conjunto** de información del Asistente para nueva tabla o matriz, haga clic en **elegir un conjunto de los conjuntos de los existentes en este informe o en un conjunto de un conjunto**de los recursos, y haga clic en **TextDataset (en este informe)** y, a continuación, en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-183">On the **Choose a dataset** page of the New Table or Matrix wizard, click **Choose an existing dataset in this report or a shared dataset**, and click **TextDataset (in this Report)**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="bb2f1-184">En la página **organizar campos** , arrastre los **campos territorio**, **LinkText**y **Product** a **grupos de filas**, arrastre el campo **sales** hasta **valores**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-184">On the **Arrange fields** page, drag the **Territory**, **LinkText**, and **Product** fields to **Row groups**, drag the **Sales** field to **Values**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="bb2f1-185">En la página **elegir el diseño** , desactive la casilla **expandir o contraer grupos** de modo que pueda ver toda la tabla y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-185">On the **Choose the layout** page, clear the **Expand/collapse groups** check box so you can see the whole table, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="bb2f1-186">En la página **elegir un estilo** , haga clic en **pizarra**y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-186">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="bb2f1-187">Arrastre la tabla para que esté bajo el bloque de títulos.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-187">Drag the table so it is below the title block.</span></span>  
  
7.  <span data-ttu-id="bb2f1-188">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-188">Click **Run**.</span></span>  
  
     <span data-ttu-id="bb2f1-189">La tabla parece correcta, pero tiene dos filas con el título Total.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-189">The table looks OK, but it has two Total rows.</span></span> <span data-ttu-id="bb2f1-190">El campo **LinkText** no necesita una fila total.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-190">The **LinkText** field doesn't need a Total row.</span></span>  
  
8.  <span data-ttu-id="bb2f1-191">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-191">Click **Design** to return to design view.</span></span>  
  
9. <span data-ttu-id="bb2f1-192">Haga clic con el botón secundario en el cuadro de texto que contiene `[LinkText]` y haga clic en **dividir celdas**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-192">Right-click the text box that contains `[LinkText]`, and click **Split Cells**.</span></span>  
  
10. <span data-ttu-id="bb2f1-193">Seleccione la celda vacía situada debajo de la `[LinkText]` celda y, a continuación, mantenga presionada la tecla Mayús y seleccione las dos celdas hacia la derecha: la celda **total** de la columna **Product** y la `[Sum(Sales)]` celda de la columna **sales** .</span><span class="sxs-lookup"><span data-stu-id="bb2f1-193">Select the empty cell below the `[LinkText]` cell, and then hold down the SHIFT key and select the two cells to its right: the **Total** cell in the **Product** column and the `[Sum(Sales)]` cell in the **Sales** column.</span></span>  
  
11. <span data-ttu-id="bb2f1-194">Con las tres celdas seleccionadas, haga clic con el botón secundario en una de esas celdas y haga clic en **Eliminar fila**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-194">With those three cells selected, right-click one of those cells and click **Delete Row**.</span></span>  
  
12. <span data-ttu-id="bb2f1-195">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-195">Click **Run**.</span></span>  
  
##  <a name="add-a-hyperlink-to-the-report"></a><a name="AddHyperlink"></a><span data-ttu-id="bb2f1-196">Agregar un hipervínculo al informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-196">Add a Hyperlink to the Report</span></span>  
 <span data-ttu-id="bb2f1-197">En esta sección, agrega un hipervínculo al texto de la tabla desde la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-197">In this section, you add a hyperlink to text in the table from the previous section.</span></span>  
  
#### <a name="to-add-a-hyperlink-to-the-report"></a><span data-ttu-id="bb2f1-198">Para agregar un hipervínculo al informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-198">To add a hyperlink to the report</span></span>  
  
1.  <span data-ttu-id="bb2f1-199">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-199">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="bb2f1-200">Haga clic con el botón secundario en la celda que contiene `[LinkText]`y haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-200">Right-click in the cell containing `[LinkText]`, and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="bb2f1-201">En el cuadro **propiedades de cuadro de texto** , haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-201">In the **Text Box Properties** box, click **Action**.</span></span>  
  
4.  <span data-ttu-id="bb2f1-202">Haga clic en **ir a dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-202">Click **Go to URL**.</span></span>  
  
5.  <span data-ttu-id="bb2f1-203">En el cuadro **seleccionar dirección URL** , haga clic en **[URL]** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-203">In the **Select URL** box, click **[URL]**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="bb2f1-204">Observe que el texto no parece diferente.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-204">Note that the text does not look any different.</span></span> <span data-ttu-id="bb2f1-205">Necesita que se parezca al texto del vínculo.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-205">You need to make it look like link text.</span></span>  
  
7.  <span data-ttu-id="bb2f1-206">Seleccione `[LinkText]`.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-206">Select `[LinkText]`.</span></span>  
  
8.  <span data-ttu-id="bb2f1-207">En la sección **fuente** de la pestaña **Inicio** , haga clic en el botón **subrayado** y, a continuación, haga clic en la flecha desplegable situada junto al botón **color** y haga clic en **azul**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-207">In the **Font** section of the **Home** tab, click the **Underline** button, and then click the drop-down arrow next to the **Color** button, and click **Blue**.</span></span>  
  
9. <span data-ttu-id="bb2f1-208">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-208">Click **Run**.</span></span>  
  
     <span data-ttu-id="bb2f1-209">Ahora el texto parece un vínculo.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-209">The text now looks like a link.</span></span>  
  
10. <span data-ttu-id="bb2f1-210">Haga clic en un vínculo.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-210">Click a link.</span></span> <span data-ttu-id="bb2f1-211">Si el equipo está conectado a Internet, un explorador abrirá a un tema de la Ayuda del Generador de informes.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-211">If the computer is connected to the Internet, a browser will open to a Report Builder Help topic.</span></span>  
  
##  <a name="rotate-text-in-the-report"></a><a name="RotateText"></a><span data-ttu-id="bb2f1-212">Girar texto en el informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-212">Rotate Text in the Report</span></span>  
 <span data-ttu-id="bb2f1-213">En esta sección, girará parte del texto de la tabla de las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-213">In this section, you rotate some of the text in the table from the previous sections.</span></span>  
  
#### <a name="to-rotate-text"></a><span data-ttu-id="bb2f1-214">Para girar el texto</span><span class="sxs-lookup"><span data-stu-id="bb2f1-214">To rotate text</span></span>  
  
1.  <span data-ttu-id="bb2f1-215">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-215">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="bb2f1-216">Haga clic en la celda que contiene `[Territory].`</span><span class="sxs-lookup"><span data-stu-id="bb2f1-216">Click in the cell containing `[Territory].`</span></span>  
  
3.  <span data-ttu-id="bb2f1-217">En la pestaña **Inicio** , en la sección **Fuente** , haga clic en el botón **Negrita** .</span><span class="sxs-lookup"><span data-stu-id="bb2f1-217">On the **Home** tab in the **Font** section, click the **Bold** button.</span></span>  
  
4.  <span data-ttu-id="bb2f1-218">Si el panel de propiedades no está abierto, en la pestaña **Ver** active la casilla **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="bb2f1-218">If the Properties pane is not open, on the **View** tab, select the **Properties** check box.</span></span>  
  
5.  <span data-ttu-id="bb2f1-219">Busque la propiedad WritingMode en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-219">Locate the WritingMode property in the Properties pane.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bb2f1-220">Cuando las propiedades del panel de propiedades se organizan en categorías, WritingMode está en la categoría **Localización** .</span><span class="sxs-lookup"><span data-stu-id="bb2f1-220">When the properties in the Properties pane are organized into categories, WritingMode is in the **Localization** category.</span></span> <span data-ttu-id="bb2f1-221">Asegúrese de haber seleccionado la celda y no el texto.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-221">Be sure you have selected the cell and not the text.</span></span> <span data-ttu-id="bb2f1-222">WritingMode es una propiedad del cuadro de texto, no del texto.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-222">WritingMode is a property of the text box, not of the text.</span></span>  
  
6.  <span data-ttu-id="bb2f1-223">En el cuadro de lista, haga clic en **Rotate270**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-223">In the list box, click **Rotate270**.</span></span>  
  
7.  <span data-ttu-id="bb2f1-224">En la pestaña **Inicio** de la sección **párrafo** , haga clic en los botones **central** y **central** para buscar el texto en el centro de la celda tanto vertical como horizontalmente.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-224">On the **Home** tab in the **Paragraph** section, click the **Middle** and **Center** buttons to locate the text in the center of the cell both vertically and horizontally.</span></span>  
  
8.  <span data-ttu-id="bb2f1-225">Haga clic en Ejecutar (**!**).</span><span class="sxs-lookup"><span data-stu-id="bb2f1-225">Click Run (**!**).</span></span>  
  
 <span data-ttu-id="bb2f1-226">Ahora el texto de la celda `[Territory]` está situado verticalmente desde la parte inferior a la parte superior de las celdas.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-226">Now the text in the `[Territory]` cell runs vertically from the bottom to the top of the cells.</span></span>  
  
##  <a name="displaying-text-with-html-formatting"></a><a name="FormatHTML"></a><span data-ttu-id="bb2f1-227">Mostrar texto con formato HTML</span><span class="sxs-lookup"><span data-stu-id="bb2f1-227">Displaying Text with HTML Formatting</span></span>  
  
#### <a name="to-display-text-formatted-as-html"></a><span data-ttu-id="bb2f1-228">Para mostrar texto con formato HTML</span><span class="sxs-lookup"><span data-stu-id="bb2f1-228">To display text formatted as HTML</span></span>  
  
1.  <span data-ttu-id="bb2f1-229">Haga clic en **Diseño** para cambiar a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-229">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="bb2f1-230">En la pestaña **Insertar** , haga clic en **Cuadro de texto**y, después, en la superficie de diseño, haga clic y arrastre para crear un cuadro de texto bajo la tabla, aproximadamente de cuatro pulgadas de ancho y tres de alto.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-230">On the **Insert** tab, click **Text Box**, and then on the design surface, click and drag to create a text box under the table, about four inches wide and three inches tall.</span></span>  
  
3.  <span data-ttu-id="bb2f1-231">Copie este texto y péguelo en el cuadro de texto:</span><span class="sxs-lookup"><span data-stu-id="bb2f1-231">Copy this text and paste it into the text box:</span></span>  
  
    ```  
    <h4>Limitations of cascading style sheet attributes</h4>  
          <p>Only a basic set of <b>cascading style sheet (CSS)</b> attributes are defined:</p>  
          <ul><li>  
              text-align, text-indent  
            </li><li>  
              font-family, font-size  
            </li><li>  
              color  
            </li><li>  
              padding, padding-bottom, padding-top, padding-right, padding-left  
            </li><li>  
              font-weight  
            </li></ul>  
    ```  
  
4.  <span data-ttu-id="bb2f1-232">Seleccione todo el texto del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-232">Select all of the text in the text box.</span></span>  
  
     <span data-ttu-id="bb2f1-233">Esta es una propiedad del texto, no del cuadro de texto, por lo que en un cuadro de texto puede tener una mezcla de texto sin formato y texto que usa etiquetas HTML como estilos.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-233">This is a property of the text, not the text box, so in one text box you could have a mixture of plain text and text that uses HTML tags as styles.</span></span>  
  
5.  <span data-ttu-id="bb2f1-234">Haga clic con el botón secundario en todo el texto seleccionado y, después, haga clic en **Propiedades del texto**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-234">Right-click all of the selected text and click **Text Properties**.</span></span>  
  
6.  <span data-ttu-id="bb2f1-235">En la página **General** , en **tipo de marcado**, haga clic en **HTML-interpretar etiquetas HTML como estilos**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-235">On the **General** page, under **Markup type**, click **HTML - Interpret HTML tags as styles**.</span></span>  
  
7.  <span data-ttu-id="bb2f1-236">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-236">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="bb2f1-237">Haga clic en Ejecutar (**!**) para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-237">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="bb2f1-238">El texto del cuadro de texto se muestra como un encabezado, párrafo y lista con viñetas.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-238">The text in the text box is displayed as a heading, paragraph, and bulleted list.</span></span>  
  
##  <a name="format-currency"></a><a name="FormatCurrency"></a><span data-ttu-id="bb2f1-239">Formato de moneda</span><span class="sxs-lookup"><span data-stu-id="bb2f1-239">Format Currency</span></span>  
  
#### <a name="to-format-numbers-as-currency"></a><span data-ttu-id="bb2f1-240">Para dar formato a los números como moneda</span><span class="sxs-lookup"><span data-stu-id="bb2f1-240">To format numbers as currency</span></span>  
  
1.  <span data-ttu-id="bb2f1-241">Haga clic en **Diseño** para cambiar a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-241">Click **Design** to switch to design view.</span></span>  
  
2.  <span data-ttu-id="bb2f1-242">Haga clic en la celda de la tabla superior que contiene `[Sum(Sales)]`, mantenga presionada la tecla MAYÚS y haga clic en la celda de la tabla inferior que contiene `[Sum(Sales)]`.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-242">Click the top table cell that contains `[Sum(Sales)]`, hold down the SHIFT key, and click the bottom table cell that contains `[Sum(Sales)]`.</span></span>  
  
3.  <span data-ttu-id="bb2f1-243">En la pestaña **Inicio** , en el grupo **Número** , haga clic en el botón **Moneda** .</span><span class="sxs-lookup"><span data-stu-id="bb2f1-243">On the **Home** tab, in the **Number** group, click the **Currency** button.</span></span>  
  
4.  <span data-ttu-id="bb2f1-244">Opta En la pestaña **Inicio** , en el grupo **número** , haga clic en el botón estilos de marcador de **posición** y, a continuación, haga clic en valores de **ejemplo** para ver cómo se dará formato a los números.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-244">(Optional) On the **Home** tab, in the **Number** group, click the **Placeholder Styles** button and click **Sample Values** to see how the numbers will be formatted.</span></span>  
  
5.  <span data-ttu-id="bb2f1-245">(Opcional) En la pestaña **Inicio** , en el grupo **Número** , haga clic dos veces en el botón **Disminuir decimales** para mostrar las cifras en dólares sin centavos.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-245">(Optional) On the **Home** tab, in the **Number** group, click the **Decrease Decimals** button twice to display dollar figures with no cents.</span></span>  
  
6.  <span data-ttu-id="bb2f1-246">Haga clic en Ejecutar (**!**) para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-246">Click Run (**!**) to preview the report.</span></span>  
  
 <span data-ttu-id="bb2f1-247">El informe muestra ahora datos dados con formato y es más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-247">The report now displays formatted data and is easier to read.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="bb2f1-248">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="bb2f1-248">Save the Report</span></span>  
 <span data-ttu-id="bb2f1-249">Puede guardar los informes en un servidor de informes, en una biblioteca de SharePoint o en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-249">You can save reports to a report server, SharePoint library, or your computer.</span></span>  
  
 <span data-ttu-id="bb2f1-250">En este tutorial, guarde el informe en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-250">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="bb2f1-251">Si no tiene acceso a un servidor de informes, guarde el informe en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-251">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-on-a-report-server"></a><span data-ttu-id="bb2f1-252">Para guardar el informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="bb2f1-252">To save the report on a report server</span></span>  
  
1.  <span data-ttu-id="bb2f1-253">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-253">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="bb2f1-254">Haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-254">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="bb2f1-255">Seleccione o escriba el nombre del servidor de informes donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-255">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="bb2f1-256">Aparecerá el mensaje "Conectando con el servidor de informes".</span><span class="sxs-lookup"><span data-stu-id="bb2f1-256">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="bb2f1-257">Una vez completada la conexión, se mostrará el contenido de la carpeta de informes que el administrador del servidor de informes especificó como ubicación predeterminada para los informes.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-257">When the connection is complete, you see the contents of the report folder that the report server administrator specified as the default location for reports.</span></span>  
  
4.  <span data-ttu-id="bb2f1-258">En **Nombre**, reemplace el nombre predeterminado por un nombre de su elección.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-258">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
5.  <span data-ttu-id="bb2f1-259">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="bb2f1-259">Click **Save**.</span></span>  
  
 <span data-ttu-id="bb2f1-260">El informe se guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-260">The report is saved to the report server.</span></span> <span data-ttu-id="bb2f1-261">El nombre del servidor de informes al que está conectado aparecerá en la barra de estado en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-261">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-on-your-computer"></a><span data-ttu-id="bb2f1-262">Para guardar el informe en el equipo</span><span class="sxs-lookup"><span data-stu-id="bb2f1-262">To save the report on your computer</span></span>  
  
1.  <span data-ttu-id="bb2f1-263">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-263">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="bb2f1-264">Haga clic en **Escritorio**, **Mis documentos**o **Mi PC**y vaya a la carpeta donde desea guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-264">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="bb2f1-265">En **Nombre**, reemplace el nombre predeterminado por un nombre de su elección.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-265">In **Name**, replace the default name with a name of your choosing.</span></span>  
  
4.  <span data-ttu-id="bb2f1-266">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="bb2f1-266">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bb2f1-267">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bb2f1-267">Next Steps</span></span>  
 <span data-ttu-id="bb2f1-268">Hay muchas maneras de dar formato al texto en Generador de informes [Tutorial: crear un informe de forma libre &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contiene más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bb2f1-268">There are many ways to format text in Report Builder [Tutorial: Creating a Free Form Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-free-form-report-report-builder.md) contains more examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2f1-269">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb2f1-269">See Also</span></span>  
 <span data-ttu-id="bb2f1-270">[Tutoriales &#40;Generador de informes&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="bb2f1-270">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="bb2f1-271">[Aplicar formato a los elementos de informe &#40;Generador de informes y SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="bb2f1-271">[Formatting Report Items &#40;Report Builder and SSRS&#41;](report-design/formatting-report-items-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="bb2f1-272">Generador de informes en SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="bb2f1-272">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
