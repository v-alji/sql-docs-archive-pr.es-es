---
title: 'Tutorial: Introducción a las expresiones | Microsoft Docs'
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2d05ef4c-5f91-48b2-8795-f0a201a0b3cc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62a815800dba0730052eb812124d4561d031d0e3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748595"
---
# <a name="tutorial-introducing-expressions"></a><span data-ttu-id="c64de-102">Tutorial: Introducción a las expresiones</span><span class="sxs-lookup"><span data-stu-id="c64de-102">Tutorial: Introducing Expressions</span></span>
  <span data-ttu-id="c64de-103">Las expresiones ayudan a crear informes eficaces y flexibles.</span><span class="sxs-lookup"><span data-stu-id="c64de-103">Expressions help you create powerful and flexible reports.</span></span> <span data-ttu-id="c64de-104">Este tutorial enseña a crear e implementar expresiones que usen operadores y funciones comunes.</span><span class="sxs-lookup"><span data-stu-id="c64de-104">This tutorial teaches you to create and implement expressions that use common functions and operators.</span></span> <span data-ttu-id="c64de-105">Usará el cuadro de diálogo **expresión** para escribir expresiones que concatenan valores de nombres, buscan valores en un conjunto de un conjunto de distintos, muestran imágenes diferentes en función de los valores de campo, etc.</span><span class="sxs-lookup"><span data-stu-id="c64de-105">You will use the **Expression** dialog box to write expressions that concatenate name values, look up values in a separate dataset, display different pictures based on field values, and so on.</span></span>  
  
 <span data-ttu-id="c64de-106">Se trata de un informe con barras y colores de filas que alternan entre el blanco y un color.</span><span class="sxs-lookup"><span data-stu-id="c64de-106">The report is a barred report with alternating row colors in white and a color.</span></span> <span data-ttu-id="c64de-107">El informe incluye un parámetro para seleccionar el color de las filas que no son blancas.</span><span class="sxs-lookup"><span data-stu-id="c64de-107">The report includes a parameter for selecting the color of the non-white rows.</span></span>  
  
 <span data-ttu-id="c64de-108">En la siguiente ilustración se muestra un informe similar al que creará.</span><span class="sxs-lookup"><span data-stu-id="c64de-108">The following illustration shows a report similar to the one you will create.</span></span>  
  
 <span data-ttu-id="c64de-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span><span class="sxs-lookup"><span data-stu-id="c64de-109">![rs_ExpressionsTutorial](../../2014/tutorials/media/rs-expressionstutorial.gif "rs_ExpressionsTutorial")</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="c64de-110">Qué aprenderá</span><span class="sxs-lookup"><span data-stu-id="c64de-110">What You Will Learn</span></span>  
 <span data-ttu-id="c64de-111">En este tutorial, aprenderá a realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="c64de-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="c64de-112">Crear un informe de tabla y un conjunto de datos con el asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="c64de-112">Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>](#Setup)  
  
2.  [<span data-ttu-id="c64de-113">Actualizar nombres predeterminados del origen de datos y el conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="c64de-113">Update Default Names of the Data Source and Dataset</span></span>](#UpdateNames)  
  
3.  [<span data-ttu-id="c64de-114">Mostrar First Name, Initial y Last Name</span><span class="sxs-lookup"><span data-stu-id="c64de-114">Display First Name, Initial, and Last Name</span></span>](#Concatenate)  
  
4.  [<span data-ttu-id="c64de-115">Usar imágenes para mostrar el sexo</span><span class="sxs-lookup"><span data-stu-id="c64de-115">Use Images to Display Gender</span></span>](#Gender)  
  
5.  [<span data-ttu-id="c64de-116">Buscar el nombre CountryRegion</span><span class="sxs-lookup"><span data-stu-id="c64de-116">Look Up CountryRegion Name</span></span>](#Lookup)  
  
6.  [<span data-ttu-id="c64de-117">Recuento de días desde la última compra</span><span class="sxs-lookup"><span data-stu-id="c64de-117">Count Days Since Last Purchase</span></span>](#Count)  
  
7.  [<span data-ttu-id="c64de-118">Usar un indicador para mostrar la comparación de ventas</span><span class="sxs-lookup"><span data-stu-id="c64de-118">Use an Indicator to Show Sales Comparison</span></span>](#Indicator)  
  
8.  [<span data-ttu-id="c64de-119">Hacer que el informe sea un "barra verde"</span><span class="sxs-lookup"><span data-stu-id="c64de-119">Make the Report a "Green Bar" Report</span></span>](#GreenBar)  
  
### <a name="other-optional-steps"></a><span data-ttu-id="c64de-120">Otros pasos opcionales</span><span class="sxs-lookup"><span data-stu-id="c64de-120">Other Optional Steps</span></span>  
  
-   [<span data-ttu-id="c64de-121">Dar formato a la columna de fecha</span><span class="sxs-lookup"><span data-stu-id="c64de-121">Format Date Column</span></span>](#DateFormat)  
  
-   [<span data-ttu-id="c64de-122">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="c64de-122">Add a Report Title</span></span>](#Title)  
  
-   [<span data-ttu-id="c64de-123">Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="c64de-123">Save the Report</span></span>](#Save)  
  
 <span data-ttu-id="c64de-124">Tiempo estimado para completar este tutorial: 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="c64de-124">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c64de-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c64de-125">Requirements</span></span>  
 <span data-ttu-id="c64de-126">Para obtener información sobre los requisitos, vea [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="c64de-126">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-table-report-and-dataset-from-the-table-or-matrix-wizard"></a><a name="Setup"></a><span data-ttu-id="c64de-127">1. crear un informe de tabla y un conjunto de informes desde el Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="c64de-127">1. Create a Table Report and Dataset from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="c64de-128">Cree un informe de tabla, un origen de datos y un conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="c64de-128">Create a table report, a data source, and a dataset.</span></span> <span data-ttu-id="c64de-129">Cuando distribuya la tabla, incluirá solo unos cuantos campos.</span><span class="sxs-lookup"><span data-stu-id="c64de-129">When you lay out the table, you will include only a few fields.</span></span> <span data-ttu-id="c64de-130">Después de completar el asistente, agregará manualmente las columnas.</span><span class="sxs-lookup"><span data-stu-id="c64de-130">After you complete the wizard you will manually add columns.</span></span> <span data-ttu-id="c64de-131">El asistente facilita la distribución de la tabla y la aplicación de un estilo.</span><span class="sxs-lookup"><span data-stu-id="c64de-131">The wizard makes it easy for you to lay out the table and apply a style.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c64de-132">En este tutorial, la consulta contiene los valores de datos, de forma que no necesita un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="c64de-132">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="c64de-133">Esto hace que la consulta requiera bastante tiempo.</span><span class="sxs-lookup"><span data-stu-id="c64de-133">This makes the query quite long.</span></span> <span data-ttu-id="c64de-134">En un entorno empresarial, la consulta no contendría los datos.</span><span class="sxs-lookup"><span data-stu-id="c64de-134">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="c64de-135">Esto es solo con fines de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="c64de-135">This is for learning purposes only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c64de-136">En este tutorial, los pasos del asistente se encuentran reunidos en un único procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c64de-136">In this tutorial, the steps for the wizard are consolidated into one procedure.</span></span> <span data-ttu-id="c64de-137">Para obtener instrucciones paso a paso sobre cómo ir hasta un servidor de informes, elegir un origen de datos y crear un conjunto de datos, consulte el primer tutorial de esta serie: [Tutorial: Crear un informe de tabla básico &#40;Generador de informes&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c64de-137">For step-by-step instructions about how to browse to a report server, choose a data source, and create a dataset, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
#### <a name="to-create-a-new-table-report"></a><span data-ttu-id="c64de-138">Para crear un nuevo informe de tabla</span><span class="sxs-lookup"><span data-stu-id="c64de-138">To create a new table report</span></span>  
  
1.  <span data-ttu-id="c64de-139">Haga clic en **Inicio**, elija **programas**, haga clic en [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **generador de informes**y, a continuación, haga clic en **generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="c64de-139">Click **Start**, point to **Programs**, click [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="c64de-140">Aparece el cuadro de diálogo **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="c64de-140">The **Getting Started** dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64de-141">Si el cuadro de diálogo **Introducción** no aparece, en el botón **generador de informes** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c64de-141">If the **Getting Started** dialog box does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64de-142">Si prefiere usar la versión ClickOnce de Generador de informes, abra Administrador de informes y haga clic en **generador de informes**o vaya a un sitio de SharePoint en el que Reporting Services tipos de contenido como informes estén habilitados y haga clic en **generador de informes Informe** en el menú **nuevo documento** de la pestaña **documentos** de una biblioteca de documentos compartida.</span><span class="sxs-lookup"><span data-stu-id="c64de-142">If you prefer using the ClickOnce version of Report Builder, open Report Manager and click **Report Builder**, or go to a SharePoint site on which Reporting Services content types such as reports are enabled and click **Report Builder Report** on the **New Document** menu on the **Documents** tab of a shared documents library.</span></span>  
  
2.  <span data-ttu-id="c64de-143">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="c64de-143">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="c64de-144">En el panel de la derecha, haga clic en **Asistente para tabla o matriz**.</span><span class="sxs-lookup"><span data-stu-id="c64de-144">In the right pane, click **Table or Matrix Wizard**.</span></span>  
  
4.  <span data-ttu-id="c64de-145">En la página **Elegir un conjunto de datos** , haga clic en **Crear un conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="c64de-145">On the **Choose a dataset** page, click **Create a dataset**.</span></span>  
  
5.  <span data-ttu-id="c64de-146">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="c64de-146">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="c64de-147">En la página **Elegir una conexión a un origen de datos** , seleccione un origen de datos del tipo **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c64de-147">On the **Choose a connection to a data source** page, select a data source that is type **SQL Server**.</span></span> <span data-ttu-id="c64de-148">Seleccione un origen de datos en la lista o vaya al servidor de informes para seleccionar uno.</span><span class="sxs-lookup"><span data-stu-id="c64de-148">Select a data source from the list or browse to the report server to select one.</span></span>  
  
7.  <span data-ttu-id="c64de-149">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="c64de-149">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="c64de-150">En la página **Diseñar una consulta** , haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="c64de-150">On the **Design a query** page, click **Edit as Text**.</span></span>  
  
9. <span data-ttu-id="c64de-151">Pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="c64de-151">Paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 'Lauren' AS FirstName,'Johnson' AS LastName, 'American Samoa' AS StateProvince, 1 AS CountryRegionID,'Unknown' AS Gender, CAST(9996.60 AS money) AS YTDPurchase, CAST('2010-6-10' AS date) AS LastPurchase  
    UNION SELECT'Warren' AS FirstName, 'Pal' AS LastName, 'New South Wales' AS StateProvince, 2 AS CountryRegionID, 'Male' AS Gender, CAST(5747.25 AS money) AS YTDPurchase, CAST('2010-7-3' AS date) AS LastPurchase  
    UNION SELECT 'Fernando' AS FirstName, 'Ross' AS LastName, 'Alberta' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(9248.15 AS money) AS YTDPurchase, CAST('2010-10-17' AS date) AS LastPurchase  
    UNION SELECT 'Rob' AS FirstName, 'Caron' AS LastName, 'Northwest Territories' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(742.50 AS money) AS YTDPurchase, CAST('2010-4-29' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Bailey' AS LastName, 'British Columbia' AS StateProvince, 3 AS CountryRegionID, 'Male' AS Gender, CAST(1147.50 AS money) AS YTDPurchase, CAST('2010-6-15' AS date) AS LastPurchase  
    UNION SELECT  'Bridget' AS FirstName, 'She' AS LastName, 'Hamburg' AS StateProvince, 4 AS CountryRegionID, 'Female' AS Gender, CAST(7497.30 AS money) AS YTDPurchase, CAST('2010-5-10' AS date) AS LastPurchase  
    UNION SELECT 'Alexander' AS FirstName, 'Martin' AS LastName, 'Saxony' AS StateProvince, 4 AS CountryRegionID, 'Male' AS Gender, CAST(2997.60 AS money) AS YTDPurchase, CAST('2010-11-19' AS date) AS LastPurchase  
    UNION SELECT 'Yolanda' AS FirstName, 'Sharma' AS LastName ,'Micronesia' AS StateProvince, 5 AS CountryRegionID, 'Female' AS Gender, CAST(3247.95 AS money) AS YTDPurchase, CAST('2010-8-23' AS date) AS LastPurchase  
    UNION SELECT 'Marc' AS FirstName, 'Zimmerman' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1200.00 AS money) AS YTDPurchase, CAST('2010-11-16' AS date) AS LastPurchase  
    UNION SELECT 'Katherine' AS FirstName, 'Abel' AS LastName, 'Moselle' AS StateProvince, 6 AS CountryRegionID, 'Female' AS Gender, CAST(2025.00 AS money) AS YTDPurchase, CAST('2010-12-1' AS date) AS LastPurchase  
    UNION SELECT 'Nicolas' as FirstName, 'Anand' AS LastName, 'Seine (Paris)' AS StateProvince, 6 AS CountryRegionID, 'Male' AS Gender, CAST(1425.00 AS money) AS YTDPurchase, CAST('2010-12-11' AS date) AS LastPurchase  
    UNION SELECT 'James' AS FirstName, 'Peters' AS LastName, 'England' AS StateProvince, 12 AS CountryRegionID, 'Male' AS Gender, CAST(887.50 AS money) AS YTDPurchase, CAST('2010-8-15' AS date) AS LastPurchase  
    UNION SELECT 'Alison' AS FirstName, 'Nath' AS LastName, 'Alaska' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(607.50 AS money) AS YTDPurchase, CAST('2010-10-13' AS date) AS LastPurchase  
    UNION SELECT 'Grace' AS FirstName, 'Patterson' AS LastName, 'Kansas' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(1215.00 AS money) AS YTDPurchase, CAST('2010-10-18' AS date) AS LastPurchase  
    UNION SELECT 'Bobby' AS FirstName, 'Sanchez' AS LastName, 'North Dakota' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(6191.00 AS money) AS YTDPurchase, CAST('2010-9-17' AS date) AS LastPurchase  
    UNION SELECT 'Charles' AS FirstName, 'Reed' AS LastName, 'Nebraska' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8772.00 AS money) AS YTDPurchase, CAST('2010-8-27' AS date) AS LastPurchase  
    UNION SELECT 'Orlando' AS FirstName, 'Romeo' AS LastName, 'Texas' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(8578.00 AS money) AS YTDPurchase, CAST('2010-7-29' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    UNION SELECT 'Cynthia' AS FirstName, 'Randall' AS LastName, 'Utah' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(7218.10 AS money) AS YTDPurchase, CAST('2010-1-11' AS date) AS LastPurchase  
    UNION SELECT 'Rebecca' AS FirstName, 'Roberts' AS LastName, 'Washington' AS StateProvince, 7 AS CountryRegionID, 'Female' AS Gender, CAST(8357.80 AS money) AS YTDPurchase, CAST('2010-10-28' AS date) AS LastPurchase  
    UNION SELECT 'Cristian' AS FirstName, 'Petulescu' AS LastName, 'Wisconsin' AS StateProvince, 7 AS CountryRegionID, 'Male' AS Gender, CAST(3470.00 AS money) AS YTDPurchase, CAST('2010-11-30' AS date) AS LastPurchase  
    ```  
  
     <span data-ttu-id="c64de-152">La consulta especifica los nombres de columna que incluyen una fecha de nacimiento, un nombre, un apellido, el estado o provincia, el identificador de país o región, el sexo y compras anuales.</span><span class="sxs-lookup"><span data-stu-id="c64de-152">The query specifies column names that include a birth date, first name, last name, state or province, country/region identifier, gender, and year-to-date purchases.</span></span>  
  
10. <span data-ttu-id="c64de-153">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar** (**!**).</span><span class="sxs-lookup"><span data-stu-id="c64de-153">On the query designer toolbar, click **Run** (**!**).</span></span> <span data-ttu-id="c64de-154">El conjunto de resultados muestra 20 filas de datos e incluye las siguientes columnas: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase y LastPurchase.</span><span class="sxs-lookup"><span data-stu-id="c64de-154">The result set displays 20 rows of data and includes the following columns: FirstName, LastName, StateProvince, CountryRegionID, Gender, YTDPurchase, and LastPurchase.</span></span>  
  
11. <span data-ttu-id="c64de-155">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="c64de-155">Click **Next**.</span></span>  
  
12. <span data-ttu-id="c64de-156">En la página **Organizar campos** , arrastre los campos siguientes, en el orden especificado, desde la lista **Campos disponibles** a la lista **Valores** .</span><span class="sxs-lookup"><span data-stu-id="c64de-156">On the **Arrange fields** page, drag the following fields, in the specified order, from the **Available Fields** list to the **Values** list.</span></span>  
  
    -   <span data-ttu-id="c64de-157">StateProvince</span><span class="sxs-lookup"><span data-stu-id="c64de-157">StateProvince</span></span>  
  
    -   <span data-ttu-id="c64de-158">CountryRegionID</span><span class="sxs-lookup"><span data-stu-id="c64de-158">CountryRegionID</span></span>  
  
    -   <span data-ttu-id="c64de-159">LastPurchase</span><span class="sxs-lookup"><span data-stu-id="c64de-159">LastPurchase</span></span>  
  
    -   <span data-ttu-id="c64de-160">YTDPurchase</span><span class="sxs-lookup"><span data-stu-id="c64de-160">YTDPurchase</span></span>  
  
     <span data-ttu-id="c64de-161">Dado que CountryRegionID e YTDPurchase contienen datos numéricos, el agregado SUM se aplica a ellos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c64de-161">Because the CountryRegionID and YTDPurchase contain numeric data, the SUM aggregate is applied to them by default.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64de-162">Los campos FirstName y LastName no están incluidos.</span><span class="sxs-lookup"><span data-stu-id="c64de-162">The FirstName and LastName fields are not included.</span></span> <span data-ttu-id="c64de-163">Los agregará en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="c64de-163">You will add them in a later step.</span></span>  
  
13. <span data-ttu-id="c64de-164">En la lista **valores** , haga clic con el botón secundario `CountryRegionID` y haga clic en la opción **suma** .</span><span class="sxs-lookup"><span data-stu-id="c64de-164">In the **Values** list, right-click `CountryRegionID` and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="c64de-165">La suma ya no se aplica a CountryRegionID.</span><span class="sxs-lookup"><span data-stu-id="c64de-165">Sum is no longer applied to CountryRegionID.</span></span>  
  
14. <span data-ttu-id="c64de-166">En la lista **Valores** , haga clic con el botón derecho en **YTDPurchase** y en la opción **Sumar** .</span><span class="sxs-lookup"><span data-stu-id="c64de-166">In the **Values** list, right-click **YTDPurchase** and click the **Sum** option.</span></span>  
  
     <span data-ttu-id="c64de-167">La suma ya no se aplica a YTDPurchase.</span><span class="sxs-lookup"><span data-stu-id="c64de-167">Sum is no longer applied to YTDPurchase.</span></span>  
  
15. <span data-ttu-id="c64de-168">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="c64de-168">Click **Next**.</span></span>  
  
16. <span data-ttu-id="c64de-169">En la página **Elegir el diseño**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c64de-169">On the **Choose the layout** page, click **Next**.</span></span>  
  
17. <span data-ttu-id="c64de-170">En la página **elegir un estilo** , haga clic en **pizarra**y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-170">On the **Choose a style** page, click **Slate**, and then click **Finish**.</span></span>  
  
##  <a name="2-update-default-names-of-the-data-source-and-dataset"></a><a name="UpdateNames"></a><span data-ttu-id="c64de-171">2. actualizar los nombres predeterminados del origen de datos y el conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="c64de-171">2. Update Default Names of the Data Source and Dataset</span></span>  
  
#### <a name="to-update-the-default-name-of-the-data-source"></a><span data-ttu-id="c64de-172">Para actualizar el nombre predeterminado del origen de datos</span><span class="sxs-lookup"><span data-stu-id="c64de-172">To update the default name of the data source</span></span>  
  
1.  <span data-ttu-id="c64de-173">En el panel Datos de informe, expanda **Orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="c64de-173">In the Report Data pane, expand **Data Sources**.</span></span>  
  
2.  <span data-ttu-id="c64de-174">Haga clic con el botón derecho en **OrigenDeDatos1** y, después, haga clic en **Propiedades del origen de datos.**</span><span class="sxs-lookup"><span data-stu-id="c64de-174">Right-click **DataSource1** and click **Data Source Properties.**</span></span>  
  
3.  <span data-ttu-id="c64de-175">En el cuadro **Nombre** , escriba **ExpressionsDataSource**</span><span class="sxs-lookup"><span data-stu-id="c64de-175">In the **Name** box, type **ExpressionsDataSource**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-update-the-default-name-of-the-dataset"></a><span data-ttu-id="c64de-176">Para actualizar el nombre predeterminado del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="c64de-176">To update the default name of the dataset</span></span>  
  
1.  <span data-ttu-id="c64de-177">En el panel Datos de informe, expanda **Conjuntos de datos**.</span><span class="sxs-lookup"><span data-stu-id="c64de-177">In the Report Data pane, expand **Datasets**.</span></span>  
  
2.  <span data-ttu-id="c64de-178">Haga clic con el botón derecho en **ConjuntoDeDatos1** y haga clic en **Propiedades del conjunto de datos.**</span><span class="sxs-lookup"><span data-stu-id="c64de-178">Right-click **DataSet1** and click **Dataset Properties.**</span></span>  
  
3.  <span data-ttu-id="c64de-179">En el cuadro **Nombre** , escriba **Expresiones**</span><span class="sxs-lookup"><span data-stu-id="c64de-179">In the **Name** box, type **Expressions**</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="3-display-first-name-initial-and-last-name"></a><a name="Concatenate"></a><span data-ttu-id="c64de-180">3. Mostrar el nombre, el inicial y el apellido</span><span class="sxs-lookup"><span data-stu-id="c64de-180">3. Display First Name, Initial, and Last Name</span></span>  
 <span data-ttu-id="c64de-181">Use la función **Izquierda** y el operador **Concatenar** (**&**) en una expresión que da como resultado un nombre que incluye una inicial y un apellido.</span><span class="sxs-lookup"><span data-stu-id="c64de-181">Use the **Left** function and the **Concatenate** (**&**) operator in an expression that evaluates to a name that includes an initial and a last name.</span></span> <span data-ttu-id="c64de-182">Puede compilar la expresión paso a paso o avanzar en el procedimiento y copiar y pegar la expresión desde el tutorial al cuadro de diálogo **Expresión** .</span><span class="sxs-lookup"><span data-stu-id="c64de-182">You can build the expression step by step or skip ahead in the procedure and copy/paste the expression from the tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the-name-column"></a><span data-ttu-id="c64de-183">Para agregar la columna Nombre</span><span class="sxs-lookup"><span data-stu-id="c64de-183">To add the Name column</span></span>  
  
1.  <span data-ttu-id="c64de-184">Haga clic con el botón derecho en la columna **StateProvince** , seleccione **Insertar columna**y haga clic en **Izquierda**.</span><span class="sxs-lookup"><span data-stu-id="c64de-184">Right-click the **StateProvince** column, point to **Insert Column**, and then click **Left**.</span></span>  
  
     <span data-ttu-id="c64de-185">Se agrega una columna nueva a la izquierda de la columna **StateProvince** .</span><span class="sxs-lookup"><span data-stu-id="c64de-185">A new column is added to the left of the **StateProvince** column.</span></span>  
  
2.  <span data-ttu-id="c64de-186">Haga clic en el título de la nueva columna y escriba **Nombre**</span><span class="sxs-lookup"><span data-stu-id="c64de-186">Click the title of the new column and type **Name**</span></span>  
  
3.  <span data-ttu-id="c64de-187">Haga clic con el botón derecho en la celda de datos de la columna **Nombre** y haga clic en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="c64de-187">Right-click the data cell for the **Name** column and click **Expression**.</span></span>  
  
4.  <span data-ttu-id="c64de-188">En el cuadro de diálogo **Expresión** , expanda **Funciones comunes**y haga clic en **Texto**.</span><span class="sxs-lookup"><span data-stu-id="c64de-188">In the **Expression** dialog box, expand **Common Functions**, and then click **Text**.</span></span>  
  
5.  <span data-ttu-id="c64de-189">En la lista **Elemento** , haga doble clic en **Izquierda**.</span><span class="sxs-lookup"><span data-stu-id="c64de-189">In the **Item** list, double-click **Left**.</span></span>  
  
     <span data-ttu-id="c64de-190">La función **Izquierda** se agrega a la expresión.</span><span class="sxs-lookup"><span data-stu-id="c64de-190">The **Left** function is added to the expression.</span></span>  
  
6.  <span data-ttu-id="c64de-191">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-191">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="c64de-192">En la lista **Valores** , haga doble clic en **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="c64de-192">In the **Values** list, double-click **FirstName**.</span></span>  
  
8.  <span data-ttu-id="c64de-193">Escriba **, 1)**</span><span class="sxs-lookup"><span data-stu-id="c64de-193">Type **, 1)**</span></span>  
  
     <span data-ttu-id="c64de-194">Esta expresión extrae un carácter del valor **FirstName** , contando desde la izquierda.</span><span class="sxs-lookup"><span data-stu-id="c64de-194">This expression extracts one character from the **FirstName** value, counting from the left.</span></span>  
  
9. <span data-ttu-id="c64de-195">Escriba **&" "&**</span><span class="sxs-lookup"><span data-stu-id="c64de-195">Type **&" "&**</span></span>  
  
10. <span data-ttu-id="c64de-196">En la lista **Valores** , haga doble clic en **LastName**.</span><span class="sxs-lookup"><span data-stu-id="c64de-196">In the **Values** list, double-click **LastName**.</span></span>  
  
     <span data-ttu-id="c64de-197">La expresión completa es la siguiente: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span><span class="sxs-lookup"><span data-stu-id="c64de-197">The completed expression: `=Left(Fields!FirstName.Value, 1) &" "& Fields!LastName.Value`</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="c64de-198">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="c64de-198">Click **Run** to preview the report.</span></span>  
  
##  <a name="4-use-images-to-display-gender"></a><a name="Gender"></a><span data-ttu-id="c64de-199">4. usar imágenes para mostrar el sexo</span><span class="sxs-lookup"><span data-stu-id="c64de-199">4. Use Images to Display Gender</span></span>  
 <span data-ttu-id="c64de-200">Use imágenes para mostrar el sexo de una persona e identifique el sexo desconocido usando una tercera imagen.</span><span class="sxs-lookup"><span data-stu-id="c64de-200">Use images to show the gender of a person, and identify unknown gender values by using a third image.</span></span> <span data-ttu-id="c64de-201">Agregará al informe tres imágenes ocultas y una nueva columna para mostrar las imágenes y después determinará la imagen que aparece en la columna según el valor del campo Gender.</span><span class="sxs-lookup"><span data-stu-id="c64de-201">You will add to the report three hidden images and a new column to display the images, and then determine the image that appears in the column based on the value of the Gender field.</span></span>  
  
 <span data-ttu-id="c64de-202">Para aplicar un color a la celda de la tabla que contiene la imagen, cuando convierta el informe en un informe con barras, agregará un rectángulo y después agregará la imagen al mismo.</span><span class="sxs-lookup"><span data-stu-id="c64de-202">To apply a color to the table cell that contains the image when you make the report a barred report, you will add a rectangle and then add the image to the rectangle.</span></span> <span data-ttu-id="c64de-203">Tiene que usar un rectángulo porque puede aplicar un color de fondo a un rectángulo, pero no a una imagen.</span><span class="sxs-lookup"><span data-stu-id="c64de-203">You need to use a rectangle because you can apply a background color to a rectangle, but not to an image.</span></span>  
  
 <span data-ttu-id="c64de-204">El tutorial usa las imágenes que se instalan con Windows, pero puede usar cualquier imagen de que disponga.</span><span class="sxs-lookup"><span data-stu-id="c64de-204">The tutorial uses images that are installed with Windows, but you can use any images available to you.</span></span> <span data-ttu-id="c64de-205">Usará imágenes incrustadas y no es necesario que estén instaladas en el equipo local ni en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c64de-205">You will use embedded images, and they do not need to be installed on your local computer or the report server.</span></span>  
  
#### <a name="to-add-images-to-the-report-body"></a><span data-ttu-id="c64de-206">Para agregar imágenes al cuerpo del informe</span><span class="sxs-lookup"><span data-stu-id="c64de-206">To add images to the report body</span></span>  
  
1.  <span data-ttu-id="c64de-207">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="c64de-207">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c64de-208">En la pestaña **Insertar** de la cinta de opciones, haga clic en **Imagen** y, después, haga clic en el cuerpo del informe, debajo de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c64de-208">On the **Insert** tab of the ribbon, click **Image** and then click in the report body, below the table.</span></span>  
  
     <span data-ttu-id="c64de-209">Se abrirá el cuadro de diálogo **Propiedades de la imagen**.</span><span class="sxs-lookup"><span data-stu-id="c64de-209">The **Image Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c64de-210">Haga clic en **Importar** y navegue hasta C:\Users\Public\Public Pictures\Sample Pictures.</span><span class="sxs-lookup"><span data-stu-id="c64de-210">Click **Import** and navigate to C:\Users\Public\Public Pictures\Sample Pictures.</span></span>  
  
4.  <span data-ttu-id="c64de-211">Haga clic en Penguins.JPG y en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c64de-211">Click Penguins.JPG and click **Open**.</span></span>  
  
     <span data-ttu-id="c64de-212">En el cuadro de diálogo **Propiedades de la imagen** haga clic en **Visibilidad** y, después, en la opción **Ocultar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-212">In the **Image Properties** dialog box, click **Visibility** and then click the **Hide** option.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="c64de-213">Repita los pasos 2 a 5, pero elija ahora Koala.JPG.</span><span class="sxs-lookup"><span data-stu-id="c64de-213">Repeat steps 2 through 5, but choose Koala.JPG.</span></span>  
  
7.  <span data-ttu-id="c64de-214">Repita los pasos 2 a 5, pero elija ahora Tulips.JPG.</span><span class="sxs-lookup"><span data-stu-id="c64de-214">Repeat steps 2 through 5, but choose Tulips.JPG.</span></span>  
  
#### <a name="to-add-the-gender-column"></a><span data-ttu-id="c64de-215">Para agregar la columna Gender</span><span class="sxs-lookup"><span data-stu-id="c64de-215">To add the Gender column</span></span>  
  
1.  <span data-ttu-id="c64de-216">Haga clic con el botón derecho en la columna **Nombre**, seleccione **Insertar columna** y haga clic en **Derecha**.</span><span class="sxs-lookup"><span data-stu-id="c64de-216">Right-click the **Name** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="c64de-217">Se agrega una columna nueva a la derecha de la columna **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="c64de-217">A new column is added to the right of the **Name** column.</span></span>  
  
2.  <span data-ttu-id="c64de-218">Haga clic en el título de la nueva columna y escriba **Gender**</span><span class="sxs-lookup"><span data-stu-id="c64de-218">Click the title of the new column and type **Gender**</span></span>  
  
#### <a name="to-add-a-rectangle"></a><span data-ttu-id="c64de-219">Para agregar un rectángulo</span><span class="sxs-lookup"><span data-stu-id="c64de-219">To add a rectangle</span></span>  
  
-   <span data-ttu-id="c64de-220">En la pestaña **Insertar** de la cinta de opciones, haga clic en **Rectángulo** y, después, haga clic en la celda de datos de la columna **Gender**.</span><span class="sxs-lookup"><span data-stu-id="c64de-220">On the **Insert** tab of the ribbon, click **Rectangle** and then click in the data cell of the **Gender** column.</span></span>  
  
     <span data-ttu-id="c64de-221">Se agregará un rectángulo a la celda.</span><span class="sxs-lookup"><span data-stu-id="c64de-221">A rectangle is added to the cell.</span></span>  
  
#### <a name="to-add-an-image-to-the-rectangle"></a><span data-ttu-id="c64de-222">Para agregar una imagen al rectángulo</span><span class="sxs-lookup"><span data-stu-id="c64de-222">To add an image to the rectangle</span></span>  
  
1.  <span data-ttu-id="c64de-223">Haga clic con el botón derecho en el rectángulo, seleccione **Insertar** y haga clic en **Imagen**.</span><span class="sxs-lookup"><span data-stu-id="c64de-223">Right-click in the rectangle, point to **Insert**, and then click **Image**.</span></span>  
  
2.  <span data-ttu-id="c64de-224">En el cuadro de diálogo **Propiedades de la imagen**, haga clic en la flecha abajo junto a **Usar esta imagen** y seleccione una de las imágenes que agregó, por ejemplo, Penguins.JPG.</span><span class="sxs-lookup"><span data-stu-id="c64de-224">In the **Image Properties** dialog box, click the down arrow beside **Use this image**, and select one of the images you added, for example, Penguins.JPG.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-use-images-to-show-gender"></a><span data-ttu-id="c64de-225">Para usar imágenes para mostrar el sexo</span><span class="sxs-lookup"><span data-stu-id="c64de-225">To use images to show gender</span></span>  
  
1.  <span data-ttu-id="c64de-226">Haga clic con el botón derecho en la imagen en la celda de datos de la columna **Gender** y haga clic en **Propiedades de la imagen**.</span><span class="sxs-lookup"><span data-stu-id="c64de-226">Right-click the image in the data cell in the **Gender** column and click **Image Properties**.</span></span>  
  
2.  <span data-ttu-id="c64de-227">En el cuadro de diálogo **Propiedades de la imagen** haga clic en el botón **fx** de la expresión junto al cuadro de texto **Usar esta imagen**.</span><span class="sxs-lookup"><span data-stu-id="c64de-227">In the **Image Properties** dialog box, click the expression **fx** button next to the **Use this image** text box.</span></span>  
  
3.  <span data-ttu-id="c64de-228">En el cuadro de diálogo **Expresión** , expanda **Funciones comunes** y, después, haga clic en **Flujo de programa**.</span><span class="sxs-lookup"><span data-stu-id="c64de-228">In the **Expression** dialog box, expand **Common Functions** and click **Program Flow**.</span></span>  
  
4.  <span data-ttu-id="c64de-229">En la lista **Elemento** , haga doble clic en **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-229">In the **Item** list, double-click **Switch**.</span></span>  
  
5.  <span data-ttu-id="c64de-230">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-230">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="c64de-231">En la lista **Valores** , haga doble clic en **Gender**.</span><span class="sxs-lookup"><span data-stu-id="c64de-231">In the **Values** list, double-click **Gender**.</span></span>  
  
7.  <span data-ttu-id="c64de-232">Escriba **="Male", "Koala",**</span><span class="sxs-lookup"><span data-stu-id="c64de-232">Type **="Male", "Koala",**</span></span>  
  
8.  <span data-ttu-id="c64de-233">En la lista **Valores** , haga doble clic en **Gender**.</span><span class="sxs-lookup"><span data-stu-id="c64de-233">In the **Values** list, double-click **Gender**.</span></span>  
  
9. <span data-ttu-id="c64de-234">Escriba **="Female", "Penguins",**</span><span class="sxs-lookup"><span data-stu-id="c64de-234">Type **="Female", "Penguins",**</span></span>  
  
10. <span data-ttu-id="c64de-235">En la lista **Valores** , haga doble clic en **Gender**.</span><span class="sxs-lookup"><span data-stu-id="c64de-235">In the **Values** list, double-click **Gender**.</span></span>  
  
11. <span data-ttu-id="c64de-236">Escriba **="Unknown", "Tulips")**</span><span class="sxs-lookup"><span data-stu-id="c64de-236">Type **="Unknown", "Tulips")**</span></span>  
  
     <span data-ttu-id="c64de-237">La expresión completa es la siguiente: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span><span class="sxs-lookup"><span data-stu-id="c64de-237">The completed expression: `=Switch(Fields!Gender.Value ="Male", "Koala",Fields!Gender.Value ="Female","Penguins",Fields!Gender.Value ="Unknown","Tulips")`</span></span>  
  
12. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
13. <span data-ttu-id="c64de-238">Haga clic en **Aceptar** de nuevo para cerrar el cuadro de diálogo **Propiedades de la imagen**.</span><span class="sxs-lookup"><span data-stu-id="c64de-238">Click **OK** again to close the **Image Properties** dialog box.</span></span>  
  
14. <span data-ttu-id="c64de-239">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="c64de-239">Click **Run** to preview the report.</span></span>  
  
##  <a name="5-look-up-countryregion-name"></a><a name="Lookup"></a><span data-ttu-id="c64de-240">5. Buscar nombre PaísRegión</span><span class="sxs-lookup"><span data-stu-id="c64de-240">5. Look Up CountryRegion Name</span></span>  
 <span data-ttu-id="c64de-241">Cree el conjunto de datos CountryRegion y use la función **Búsqueda** para mostrar el nombre de un país o región en lugar del identificador del mismo.</span><span class="sxs-lookup"><span data-stu-id="c64de-241">Create the CountryRegion dataset and use the **Lookup** function to display the name of a country/region instead of the identifier of the country/region.</span></span>  
  
#### <a name="to-create-the-countryregion-dataset"></a><span data-ttu-id="c64de-242">Para crear el conjunto de datos CountryRegion</span><span class="sxs-lookup"><span data-stu-id="c64de-242">To create the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="c64de-243">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="c64de-243">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c64de-244">En el panel datos de informe, haga clic en **nuevo** y, a continuación, en **conjunto**de datos.</span><span class="sxs-lookup"><span data-stu-id="c64de-244">In the Report Data pane, click **New** and then click **Dataset**.</span></span>  
  
3.  <span data-ttu-id="c64de-245">Haga clic en **Usar un conjunto de datos insertado en el informe**.</span><span class="sxs-lookup"><span data-stu-id="c64de-245">Click **Use a dataset embedded in my report**.</span></span>  
  
4.  <span data-ttu-id="c64de-246">En la lista **Origen de datos** , seleccione ExpressionsDataSource.</span><span class="sxs-lookup"><span data-stu-id="c64de-246">In the **Data source** list, select ExpressionsDataSource.</span></span>  
  
5.  <span data-ttu-id="c64de-247">En el cuadro **Nombre** , escriba **CountryRegion**</span><span class="sxs-lookup"><span data-stu-id="c64de-247">In the **Name** box, type **CountryRegion**</span></span>  
  
6.  <span data-ttu-id="c64de-248">Compruebe que el tipo de consulta **Texto** está seleccionado y haga clic en **Diseñador de consultas**.</span><span class="sxs-lookup"><span data-stu-id="c64de-248">Verify that the **Text** query type is selected and click **Query Designer**.</span></span>  
  
7.  <span data-ttu-id="c64de-249">Haga clic en **Editar como texto**.</span><span class="sxs-lookup"><span data-stu-id="c64de-249">Click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="c64de-250">Copie y pegue la siguiente consulta en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="c64de-250">Copy and paste the following query into the query pane:</span></span>  
  
    ```  
    SELECT 1 AS ID, 'American Samoa' AS CountryRegion  
    UNION SELECT 2 AS CountryRegionID, 'Australia' AS CountryRegion  
    UNION SELECT 3 AS ID, 'Canada' AS CountryRegion  
    UNION SELECT 4 AS ID, 'Germany' AS CountryRegion  
    UNION SELECT 5 AS ID, 'Micronesia' AS CountryRegion  
    UNION SELECT 6 AS ID, 'France' AS CountryRegion  
    UNION SELECT 7 AS ID, 'United States' AS CountryRegion  
    UNION SELECT 8 AS ID, 'Brazil' AS CountryRegion  
    UNION SELECT 9 AS ID, 'Mexico' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Japan' AS CountryRegion  
    UNION SELECT 10 AS ID, 'Australia' AS CountryRegion  
    UNION SELECT 12 AS ID, 'United Kingdom' AS CountryRegion  
    ```  
  
9. <span data-ttu-id="c64de-251">Haga clic en **Ejecutar** (**!**) para ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="c64de-251">Click **Run** (**!**) to run the query.</span></span>  
  
     <span data-ttu-id="c64de-252">Los resultados de la consulta son los identificadores del país o región y los nombres.</span><span class="sxs-lookup"><span data-stu-id="c64de-252">The query results are the country/region identifiers and names.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="c64de-253">Haga clic en **Aceptar** de nuevo para cerrar el cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="c64de-253">Click **OK** again to close the **Dataset Properties** dialog box.</span></span>  
  
#### <a name="to-look-up-values-in-the-countryregion-dataset"></a><span data-ttu-id="c64de-254">Para buscar valores en el conjunto de datos CountryRegion</span><span class="sxs-lookup"><span data-stu-id="c64de-254">To look up values in the CountryRegion dataset</span></span>  
  
1.  <span data-ttu-id="c64de-255">Haga clic en el título de columna **Country Region ID** y elimine el texto: ID.</span><span class="sxs-lookup"><span data-stu-id="c64de-255">Click the **Country Region ID** column title and delete the text: ID.</span></span>  
  
2.  <span data-ttu-id="c64de-256">Haga clic con el botón derecho en la celda de datos de la columna **Country Region** y haga clic en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="c64de-256">Right-click the data cell for the **Country Region** column and click **Expression**.</span></span>  
  
3.  <span data-ttu-id="c64de-257">Elimine la expresión excepto el signo igual (=) inicial.</span><span class="sxs-lookup"><span data-stu-id="c64de-257">Delete the expression except the initial equal (=) sign.</span></span>  
  
     <span data-ttu-id="c64de-258">El resto de la expresión es: `=`</span><span class="sxs-lookup"><span data-stu-id="c64de-258">The remaining expression is: `=`</span></span>  
  
4.  <span data-ttu-id="c64de-259">En el cuadro de diálogo **Expresión**, expanda **Funciones comunes** y, después, haga clic en **Varios**.</span><span class="sxs-lookup"><span data-stu-id="c64de-259">In the **Expression** dialog box, expand **Common Functions** and click **Miscellaneous**.</span></span>  
  
5.  <span data-ttu-id="c64de-260">En la lista **Elemento**, haga doble clic en **Búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="c64de-260">In the **Item** list, double-click **Lookup**.</span></span>  
  
6.  <span data-ttu-id="c64de-261">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-261">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
7.  <span data-ttu-id="c64de-262">En la lista **valores** , haga doble clic en `CountryRegionID` .</span><span class="sxs-lookup"><span data-stu-id="c64de-262">In the **Values** list, double-click `CountryRegionID`.</span></span>  
  
8.  <span data-ttu-id="c64de-263">Si el cursor no está ya inmediatamente después de `CountryRegionID.Value`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-263">If the cursor is not already immediately after `CountryRegionID.Value`, place it there.</span></span>  
  
9. <span data-ttu-id="c64de-264">Elimine el paréntesis de cierre y escriba **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span><span class="sxs-lookup"><span data-stu-id="c64de-264">Delete the right parenthesis and then type **,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")**</span></span>  
  
     <span data-ttu-id="c64de-265">La expresión completa es la siguiente: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span><span class="sxs-lookup"><span data-stu-id="c64de-265">The completed expression: `=Lookup(Fields!CountryRegionID.Value,Fields!ID.value, Fields!CountryRegion.value, "CountryRegion")`</span></span>  
  
     <span data-ttu-id="c64de-266">La sintaxis de la función **Búsqueda** especifica una búsqueda entre CountryRegionID e ID en el conjunto de datos CountryRegion que devuelve el valor CountryRegion, que también está en el conjunto de datos CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="c64de-266">The syntax of the **Lookup** function specifies a lookup between CountryRegionID and ID in the CountryRegion dataset that returns the CountryRegion value, which is also in the CountryRegion dataset.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="c64de-267">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="c64de-267">Click **Run** to preview the report.</span></span>  
  
##  <a name="6-count-days-since-last-purchase"></a><a name="Count"></a><span data-ttu-id="c64de-268">6. recuento de días desde la última compra</span><span class="sxs-lookup"><span data-stu-id="c64de-268">6. Count Days Since Last Purchase</span></span>  
 <span data-ttu-id="c64de-269">Agregue una columna y, a continuación, utilice la función **Now** o la `ExecutionTime` variable global integrada para calcular el número de días a partir de hoy desde la fecha en que la última compra una persona.</span><span class="sxs-lookup"><span data-stu-id="c64de-269">Add a column and then use the **Now** function or the `ExecutionTime` built-in global variable to calculate the number of days from today since a person's last purchases.</span></span>  
  
#### <a name="to-add-the-days-ago-column"></a><span data-ttu-id="c64de-270">Para agregar la columna Días transcurridos</span><span class="sxs-lookup"><span data-stu-id="c64de-270">To add the Days Ago column</span></span>  
  
1.  <span data-ttu-id="c64de-271">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="c64de-271">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c64de-272">Haga clic con el botón derecho en la columna **Last Purchase** , seleccione **Insertar columna**y haga clic en **Derecha**.</span><span class="sxs-lookup"><span data-stu-id="c64de-272">Right-click the **Last Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="c64de-273">Se agrega una columna nueva a la derecha de la columna **Last Purchase** .</span><span class="sxs-lookup"><span data-stu-id="c64de-273">A new column is added to the right of the **Last Purchase** column.</span></span>  
  
3.  <span data-ttu-id="c64de-274">En el encabezado de columna, escriba **Días transcurridos**</span><span class="sxs-lookup"><span data-stu-id="c64de-274">In the column header, type **Days Ago**</span></span>  
  
4.  <span data-ttu-id="c64de-275">Haga clic con el botón derecho en la celda de datos de la columna **Días transcurridos** y haga clic en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="c64de-275">Right-click the data cell for the **Days Ago** column and click **Expression**.</span></span>  
  
5.  <span data-ttu-id="c64de-276">En el cuadro de diálogo **Expresión**, expanda **Funciones comunes** y haga clic en **Fecha y hora**.</span><span class="sxs-lookup"><span data-stu-id="c64de-276">In the **Expression** dialog box, expand **Common Functions**, and then click **Date & Time**.</span></span>  
  
6.  <span data-ttu-id="c64de-277">En la lista **Elemento** , haga doble clic en **DateDiff**.</span><span class="sxs-lookup"><span data-stu-id="c64de-277">In the **Item** list, double-click **DateDiff**.</span></span>  
  
7.  <span data-ttu-id="c64de-278">Si el cursor no está ya inmediatamente después de `DateDiff(`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-278">If the cursor is not already immediately after `DateDiff(`, place it there.</span></span>  
  
8.  <span data-ttu-id="c64de-279">Escriba **"d",**</span><span class="sxs-lookup"><span data-stu-id="c64de-279">Type **"d",**</span></span>  
  
9. <span data-ttu-id="c64de-280">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-280">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
10. <span data-ttu-id="c64de-281">En la lista **Valores**, haga doble clic en **LastPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c64de-281">In the **Values** list, double-click **LastPurchase**.</span></span>  
  
11. <span data-ttu-id="c64de-282">Si el cursor no está ya inmediatamente después de `Fields!LastPurchase.Value`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-282">If the cursor is not already immediately after `Fields!LastPurchase.Value`, place it there.</span></span>  
  
12. <span data-ttu-id="c64de-283">Escriba **,**</span><span class="sxs-lookup"><span data-stu-id="c64de-283">Type **,**</span></span>  
  
13. <span data-ttu-id="c64de-284">En la lista de **Categoría**, haga clic de nuevo en **Fecha y hora**.</span><span class="sxs-lookup"><span data-stu-id="c64de-284">In the **Category** list, click **Date & Time** again.</span></span>  
  
14. <span data-ttu-id="c64de-285">En la lista **Elemento**, haga doble clic en **Ahora**.</span><span class="sxs-lookup"><span data-stu-id="c64de-285">In the **Item** list, double-click **Now**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="c64de-286">En los informes de producción no debe usar la función **Ahora** en las expresiones que se evalúan varias veces como representadores de informes (por ejemplo, en las filas de detalle de un informe).</span><span class="sxs-lookup"><span data-stu-id="c64de-286">In production reports you should not use the **Now** function in expressions that are evaluated multiple times as the report renders (for example, in the detail rows of a report).</span></span> <span data-ttu-id="c64de-287">El valor de **Ahora** cambia de una fila a otra y los diferentes valores afectan a los resultados de evaluación de las expresiones, lo que conduce a resultados ligeramente incoherentes.</span><span class="sxs-lookup"><span data-stu-id="c64de-287">The value of **Now** changes from row to row and the different values affect the evaluation results of expressions, which leads to results that are subtly inconsistent.</span></span> <span data-ttu-id="c64de-288">En su lugar, debe usar la variable global `ExecutionTime` que proporciona [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c64de-288">Instead, you should use the `ExecutionTime` global variable that [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] provides.</span></span>  
  
15. <span data-ttu-id="c64de-289">Si el cursor no está ya inmediatamente después de `Now(`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-289">If the cursor is not already immediately after `Now(`, place it there.</span></span>  
  
16. <span data-ttu-id="c64de-290">Elimine el paréntesis de apertura y escriba **)**</span><span class="sxs-lookup"><span data-stu-id="c64de-290">Delete the left parenthesis and then type **)**</span></span>  
  
     <span data-ttu-id="c64de-291">La expresión completa es la siguiente: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span><span class="sxs-lookup"><span data-stu-id="c64de-291">The completed expression: `=DateDiff("d", Fields!LastPurchase.Value, Now)`</span></span>  
  
17. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="7-use-an-indicator-to-show-sales-comparison"></a><a name="Indicator"></a><span data-ttu-id="c64de-292">7. usar un indicador para mostrar la comparación de ventas</span><span class="sxs-lookup"><span data-stu-id="c64de-292">7. Use an Indicator to Show Sales Comparison</span></span>  
 <span data-ttu-id="c64de-293">Agregue una nueva columna y use un indicador para mostrar si las compras anuales hasta la fecha (año) de una persona están por encima o por debajo del promedio de compras de año.</span><span class="sxs-lookup"><span data-stu-id="c64de-293">Add a new column and use an indicator to show whether a person's year-to-date (YTD) purchases are above or below the average YTD purchases.</span></span> <span data-ttu-id="c64de-294">La función **Redondear** quita los decimales de los valores.</span><span class="sxs-lookup"><span data-stu-id="c64de-294">The **Round** function removes decimals from values.</span></span>  
  
 <span data-ttu-id="c64de-295">La configuración del indicador y sus estados requiere muchos pasos.</span><span class="sxs-lookup"><span data-stu-id="c64de-295">The configuration of the indicator and its states requires many steps.</span></span> <span data-ttu-id="c64de-296">Si lo desea, en el procedimiento "para configurar el indicador", puede avanzar y copiar o pegar las expresiones completadas de este tutorial en el cuadro de diálogo **expresión** .</span><span class="sxs-lookup"><span data-stu-id="c64de-296">If you want to, in the "To configure the indicator" procedure, you can skip ahead and copy/paste the completed expressions from this tutorial into the **Expression** dialog box.</span></span>  
  
#### <a name="to-add-the--or---avg-sales-column"></a><span data-ttu-id="c64de-297">Para agregar la columna Promedio + o -</span><span class="sxs-lookup"><span data-stu-id="c64de-297">To add the + or - AVG Sales column</span></span>  
  
1.  <span data-ttu-id="c64de-298">Haga clic con el botón derecho en la columna **YTD Purchase** , seleccione **Insertar columna**y haga clic en **Derecha**.</span><span class="sxs-lookup"><span data-stu-id="c64de-298">Right-click the **YTD Purchase** column, point to **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="c64de-299">Se agrega una columna nueva a la derecha de la columna **YTD Purchase** .</span><span class="sxs-lookup"><span data-stu-id="c64de-299">A new column is added to the right of the **YTD Purchase** column.</span></span>  
  
2.  <span data-ttu-id="c64de-300">Haga clic en el título de la columna y escriba **Ventas promedio + o -**</span><span class="sxs-lookup"><span data-stu-id="c64de-300">Click the title of the column and type **+ or - AVG Sales**</span></span>  
  
#### <a name="to-add-an-indicator"></a><span data-ttu-id="c64de-301">Para agregar un indicador</span><span class="sxs-lookup"><span data-stu-id="c64de-301">To add an indicator</span></span>  
  
1.  <span data-ttu-id="c64de-302">En la pestaña **Insertar** de la cinta de opciones, haga clic en **Indicador** y, después, haga clic en la celda de datos de la columna **Ventas promedio + o -**.</span><span class="sxs-lookup"><span data-stu-id="c64de-302">On the **Insert** tab of the ribbon, click **Indicator**, and then click the data cell for the **+ or - AVG Sales** column.</span></span>  
  
     <span data-ttu-id="c64de-303">Se abrirá el cuadro de diálogo **Seleccionar tipo de indicador** .</span><span class="sxs-lookup"><span data-stu-id="c64de-303">The **Select Indicator Type** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="c64de-304">En el grupo **Direccional** de los conjuntos de iconos, haga clic en el conjunto de tres flechas grises.</span><span class="sxs-lookup"><span data-stu-id="c64de-304">In the **Directional** group of icon sets, click the set of three gray arrows.</span></span>  
  
3.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-configure-the-indicator"></a><span data-ttu-id="c64de-305">Para configurar el indicador</span><span class="sxs-lookup"><span data-stu-id="c64de-305">To configure the indicator</span></span>  
  
1.  <span data-ttu-id="c64de-306">Haga clic con el botón derecho en el indicador, haga clic en **Propiedades de indicador**y, después, en **Valor y estados**.</span><span class="sxs-lookup"><span data-stu-id="c64de-306">Right-click the indicator, click **Indicator Properties**, and then click **Value and States**.</span></span>  
  
2.  <span data-ttu-id="c64de-307">Haga clic en el botón de expresión **fx** situado junto al cuadro de texto **Valor** .</span><span class="sxs-lookup"><span data-stu-id="c64de-307">Click the expression **fx** button next to the **Value** text box.</span></span>  
  
3.  <span data-ttu-id="c64de-308">En el cuadro de diálogo **Expresión** , expanda **Funciones comunes**y haga clic en **Matemáticas**.</span><span class="sxs-lookup"><span data-stu-id="c64de-308">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
4.  <span data-ttu-id="c64de-309">En la lista **Elemento** , haga doble clic en **Redondear**.</span><span class="sxs-lookup"><span data-stu-id="c64de-309">In the **Item** list, double-click **Round**.</span></span>  
  
5.  <span data-ttu-id="c64de-310">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-310">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
6.  <span data-ttu-id="c64de-311">En la lista **Valores**, haga doble clic en **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c64de-311">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
7.  <span data-ttu-id="c64de-312">Si el cursor no está ya inmediatamente después de `Fields!YTDPurchase.Value`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-312">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
8.  <span data-ttu-id="c64de-313">Automáticamente**-**</span><span class="sxs-lookup"><span data-stu-id="c64de-313">Type  **-**</span></span>  
  
9. <span data-ttu-id="c64de-314">Expanda **Funciones comunes** de nuevo y haga clic en **Agregado**.</span><span class="sxs-lookup"><span data-stu-id="c64de-314">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
10. <span data-ttu-id="c64de-315">En la lista **Elemento**, haga doble clic en **Promedio**.</span><span class="sxs-lookup"><span data-stu-id="c64de-315">In the **Item** list, double-click **Avg**.</span></span>  
  
11. <span data-ttu-id="c64de-316">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-316">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
12. <span data-ttu-id="c64de-317">En la lista **Valores**, haga doble clic en **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c64de-317">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
13. <span data-ttu-id="c64de-318">Si el cursor no está ya inmediatamente después de `Fields!YTDPurchase.Value`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-318">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
14. <span data-ttu-id="c64de-319">Escriba **, "Expressions"))**</span><span class="sxs-lookup"><span data-stu-id="c64de-319">Type **, "Expressions"))**</span></span>  
  
     <span data-ttu-id="c64de-320">La expresión completa es la siguiente: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span><span class="sxs-lookup"><span data-stu-id="c64de-320">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions"))`</span></span>  
  
15. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
16. <span data-ttu-id="c64de-321">En el cuadro **Unidad de medida de estados** , seleccione **Numérico**.</span><span class="sxs-lookup"><span data-stu-id="c64de-321">In the **States Measurement Unit** box, select **Numeric**.</span></span>  
  
17. <span data-ttu-id="c64de-322">En la fila con la flecha hacia abajo, haga clic en el botón **fx** a la derecha del cuadro de texto del valor **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="c64de-322">In the row with the down-pointing arrow, click the **fx** button to the right of the text box for the **Start** value.</span></span>  
  
18. <span data-ttu-id="c64de-323">En el cuadro de diálogo **Expresión** , expanda **Funciones comunes**y haga clic en **Matemáticas**.</span><span class="sxs-lookup"><span data-stu-id="c64de-323">In the **Expression** dialog box, expand **Common Functions**, and then click **Math**.</span></span>  
  
19. <span data-ttu-id="c64de-324">En la lista **Elemento** , haga doble clic en **Redondear**.</span><span class="sxs-lookup"><span data-stu-id="c64de-324">In the **Item** list, double-click **Round**.</span></span>  
  
20. <span data-ttu-id="c64de-325">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-325">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
21. <span data-ttu-id="c64de-326">En la lista **Valores**, haga doble clic en **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c64de-326">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
22. <span data-ttu-id="c64de-327">Si el cursor no está ya inmediatamente después de `Fields!YTDPurchase.Value`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-327">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="c64de-328">Automáticamente**-**</span><span class="sxs-lookup"><span data-stu-id="c64de-328">Type  **-**</span></span>  
  
24. <span data-ttu-id="c64de-329">Expanda **Funciones comunes** de nuevo y haga clic en **Agregado**.</span><span class="sxs-lookup"><span data-stu-id="c64de-329">Expand **Common Functions** again and click **Aggregate**.</span></span>  
  
25. <span data-ttu-id="c64de-330">En la lista **Elemento**, haga doble clic en **Promedio**.</span><span class="sxs-lookup"><span data-stu-id="c64de-330">In the **Item** list, double-click **Avg**.</span></span>  
  
26. <span data-ttu-id="c64de-331">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-331">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
27. <span data-ttu-id="c64de-332">En la lista **Valores**, haga doble clic en **YTDPurchase**.</span><span class="sxs-lookup"><span data-stu-id="c64de-332">In the **Values** list, double-click **YTDPurchase**.</span></span>  
  
28. <span data-ttu-id="c64de-333">Si el cursor no está ya inmediatamente después de `Fields!YTDPurchase.Value`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-333">If the cursor is not already immediately after `Fields!YTDPurchase.Value`, place it there.</span></span>  
  
29. <span data-ttu-id="c64de-334">Escriba **, "Expressions")) < 0**</span><span class="sxs-lookup"><span data-stu-id="c64de-334">Type **, "Expressions")) < 0**</span></span>  
  
     <span data-ttu-id="c64de-335">La expresión completa es la siguiente: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span><span class="sxs-lookup"><span data-stu-id="c64de-335">The completed expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) < 0`</span></span>  
  
30. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
31. <span data-ttu-id="c64de-336">En el cuadro de texto del valor **Final** , escriba **0**</span><span class="sxs-lookup"><span data-stu-id="c64de-336">In the text box for the **End** value, type **0**</span></span>  
  
32. <span data-ttu-id="c64de-337">Haga clic en la fila con la flecha horizontal y haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-337">Click the row with the horizontal-pointing arrow and click **Delete**.</span></span>  
  
33. <span data-ttu-id="c64de-338">En la fila con la flecha hacia arriba, en el cuadro **Inicio** , escriba **0**</span><span class="sxs-lookup"><span data-stu-id="c64de-338">In the row with the up-pointing arrow, in the **Start** box, type **0**</span></span>  
  
34. <span data-ttu-id="c64de-339">Haga clic en el botón **fx** a la derecha del cuadro de texto del valor **Final** .</span><span class="sxs-lookup"><span data-stu-id="c64de-339">Click the **fx** button to the right of the text box for the **End** value.</span></span>  
  
35. <span data-ttu-id="c64de-340">En el cuadro de diálogo **expresión** , cree la expresión:`=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span><span class="sxs-lookup"><span data-stu-id="c64de-340">In the **Expression** dialog box, create the expression: `=Round(Fields!YTDPurchase.Value - Avg(Fields!YTDPurchase.Value, "Expressions")) >0`</span></span>  
  
36. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
37. <span data-ttu-id="c64de-341">Haga clic en **Aceptar** de nuevo para cerrar el cuadro de diálogo **Propiedades de indicador** .</span><span class="sxs-lookup"><span data-stu-id="c64de-341">Click **OK** again to close the **Indicator properties** dialog box.</span></span>  
  
38. <span data-ttu-id="c64de-342">Haga clic en **Ejecutar** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="c64de-342">Click **Run** to preview the report.</span></span>  
  
##  <a name="8-make-the-report-a-green-bar-report"></a><a name="GreenBar"></a><span data-ttu-id="c64de-343">8. convierta el informe en un informe de "barra verde"</span><span class="sxs-lookup"><span data-stu-id="c64de-343">8. Make the Report a "Green Bar" Report</span></span>  
 <span data-ttu-id="c64de-344">Use un parámetro para especificar el color que se aplicará a filas alternativas del informe, convirtiéndolo en un informe con barras.</span><span class="sxs-lookup"><span data-stu-id="c64de-344">Use a parameter to specify the color to apply to alternating rows in the report, making it a barred report.</span></span>  
  
#### <a name="to-add-a-parameter"></a><span data-ttu-id="c64de-345">Para agregar un parámetro</span><span class="sxs-lookup"><span data-stu-id="c64de-345">To add a parameter</span></span>  
  
1.  <span data-ttu-id="c64de-346">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="c64de-346">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c64de-347">En el panel **Datos de informe** , haga clic con el botón derecho en **Parámetros** y haga clic en **Agregar parámetro**.</span><span class="sxs-lookup"><span data-stu-id="c64de-347">In the **Report Data** pane, right-click **Parameters** and click **Add Parameter**.</span></span>  
  
     <span data-ttu-id="c64de-348">Se abrirá el cuadro de diálogo **Propiedades de parámetro de informe** .</span><span class="sxs-lookup"><span data-stu-id="c64de-348">The **Report Parameter Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="c64de-349">En **Pedir datos**, escriba **Elegir color**</span><span class="sxs-lookup"><span data-stu-id="c64de-349">In **Prompt**, type **Choose color**</span></span>  
  
4.  <span data-ttu-id="c64de-350">En **Nombre**, escriba **RowColor**</span><span class="sxs-lookup"><span data-stu-id="c64de-350">In **Name**, type **RowColor**</span></span>  
  
5.  <span data-ttu-id="c64de-351">En el panel izquierdo, haga clic en **Valores disponibles**.</span><span class="sxs-lookup"><span data-stu-id="c64de-351">In the left pane, click **Available Values**.</span></span>  
  
6.  <span data-ttu-id="c64de-352">Haga clic en **Especificar valores**.</span><span class="sxs-lookup"><span data-stu-id="c64de-352">Click **Specify values**.</span></span>  
  
7.  <span data-ttu-id="c64de-353">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-353">Click **Add**.</span></span>  
  
8.  <span data-ttu-id="c64de-354">En el cuadro **etiqueta** , escriba: **amarillo** .</span><span class="sxs-lookup"><span data-stu-id="c64de-354">In the **Label** box, type: **Yellow**</span></span>  
  
9. <span data-ttu-id="c64de-355">En el cuadro **Valor** , escriba **Amarillo**</span><span class="sxs-lookup"><span data-stu-id="c64de-355">In the **Value** box, type **Yellow**</span></span>  
  
10. <span data-ttu-id="c64de-356">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-356">Click **Add**.</span></span>  
  
11. <span data-ttu-id="c64de-357">En el cuadro **Etiqueta** , escriba **Verde**</span><span class="sxs-lookup"><span data-stu-id="c64de-357">In the **Label** box, type **Green**</span></span>  
  
12. <span data-ttu-id="c64de-358">En el cuadro **Valor** , escriba **VerdePálido**</span><span class="sxs-lookup"><span data-stu-id="c64de-358">In the **Value** box, type **PaleGreen**</span></span>  
  
13. <span data-ttu-id="c64de-359">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-359">Click **Add**.</span></span>  
  
14. <span data-ttu-id="c64de-360">En el cuadro **Etiqueta** , escriba **Azul**</span><span class="sxs-lookup"><span data-stu-id="c64de-360">In the **Label** box, type **Blue**</span></span>  
  
15. <span data-ttu-id="c64de-361">En el cuadro **Valor** , escriba **AzulClaro**</span><span class="sxs-lookup"><span data-stu-id="c64de-361">In the **Value** box, type **LightBlue**</span></span>  
  
16. <span data-ttu-id="c64de-362">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-362">Click **Add**.</span></span>  
  
17. <span data-ttu-id="c64de-363">En el cuadro **Etiqueta** , escriba **Rosa**</span><span class="sxs-lookup"><span data-stu-id="c64de-363">In the **Label** box, type **Pink**</span></span>  
  
18. <span data-ttu-id="c64de-364">En el cuadro **Valor** , escriba **Rosa**</span><span class="sxs-lookup"><span data-stu-id="c64de-364">In the **Value** box, type **Pink**</span></span>  
  
19. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-apply-alternating-colors-to-detail-rows"></a><span data-ttu-id="c64de-365">Para aplicar colores alternativos a las filas de detalle.</span><span class="sxs-lookup"><span data-stu-id="c64de-365">To apply alternating colors to detail rows</span></span>  
  
1.  <span data-ttu-id="c64de-366">Haga clic en la pestaña **Vista** de la cinta de opciones y compruebe que está seleccionado **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c64de-366">Click the **View** tab on the ribbon and verify that **Properties** is selected.</span></span>  
  
2.  <span data-ttu-id="c64de-367">Haga clic en la celda de datos de la columna **Nombre** y pulse la tecla Mayús.</span><span class="sxs-lookup"><span data-stu-id="c64de-367">Click the data cell for the **Name** column and press the Shift key.</span></span>  
  
3.  <span data-ttu-id="c64de-368">Una a una, haga clic en el resto de celdas de la fila.</span><span class="sxs-lookup"><span data-stu-id="c64de-368">One by one, click the other cells in the row.</span></span>  
  
4.  <span data-ttu-id="c64de-369">En el panel Propiedades, haga clic en **BackgroundColor**.</span><span class="sxs-lookup"><span data-stu-id="c64de-369">In the Properties pane, click **BackgroundColor**.</span></span>  
  
     <span data-ttu-id="c64de-370">Si en el panel Propiedades se muestran las propiedades según la categoría, encontrará **BackgroundColor** en la categoría **Relleno**.</span><span class="sxs-lookup"><span data-stu-id="c64de-370">If your Properties pane lists properties by category, you will find the **BackgroundColor** under the **Fill** category.</span></span>  
  
5.  <span data-ttu-id="c64de-371">Haga clic en la flecha hacia abajo y, después, en **Expresión**.</span><span class="sxs-lookup"><span data-stu-id="c64de-371">Click the down arrow and then click **Expression**.</span></span>  
  
6.  <span data-ttu-id="c64de-372">En el cuadro de diálogo **Expresión** , expanda **Funciones comunes**y, después, haga clic en **Flujo de programa**.</span><span class="sxs-lookup"><span data-stu-id="c64de-372">In the **Expression** dialog box, expand **Common Functions**, and then click **Program Flow**.</span></span>  
  
7.  <span data-ttu-id="c64de-373">En la lista **Elemento** , haga doble clic en **SiInm**.</span><span class="sxs-lookup"><span data-stu-id="c64de-373">In the **Item** list, double-click **IIf**.</span></span>  
  
8.  <span data-ttu-id="c64de-374">Expanda **Funciones comunes** y haga clic en **Agregado**.</span><span class="sxs-lookup"><span data-stu-id="c64de-374">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
9. <span data-ttu-id="c64de-375">En la lista **Elemento**, haga doble clic en **RunningValue**.</span><span class="sxs-lookup"><span data-stu-id="c64de-375">In the **Item** list, double-click **RunningValue**.</span></span>  
  
10. <span data-ttu-id="c64de-376">En la lista **Categoría** , haga clic en **Campos (Expresiones)**.</span><span class="sxs-lookup"><span data-stu-id="c64de-376">In the **Category** list, click **Fields (Expressions)**.</span></span>  
  
11. <span data-ttu-id="c64de-377">En la lista **Valores** , haga doble clic en **FirstName**.</span><span class="sxs-lookup"><span data-stu-id="c64de-377">In the **Values** list, double-click **FirstName**.</span></span>  
  
12. <span data-ttu-id="c64de-378">Si el cursor no está ya inmediatamente después de `Fields!FirstName.Value`, colóquelo ahí y escriba **,**</span><span class="sxs-lookup"><span data-stu-id="c64de-378">If the cursor is not already immediately after `Fields!FirstName.Value`, place it there and type **,**</span></span>  
  
13. <span data-ttu-id="c64de-379">Expanda **Funciones comunes** y haga clic en **Agregado**.</span><span class="sxs-lookup"><span data-stu-id="c64de-379">Expand **Common Functions** and click **Aggregate**.</span></span>  
  
14. <span data-ttu-id="c64de-380">En la lista **Elemento**, haga doble clic en **Recuento**.</span><span class="sxs-lookup"><span data-stu-id="c64de-380">In the **Item** list, double-click **Count**.</span></span>  
  
15. <span data-ttu-id="c64de-381">Si el cursor no está ya inmediatamente después de `Count(`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-381">If the cursor is not already immediately after `Count(`, place it there.</span></span>  
  
16. <span data-ttu-id="c64de-382">Elimine el paréntesis de apertura y, a continuación, escriba **"expresiones")**</span><span class="sxs-lookup"><span data-stu-id="c64de-382">Delete the left parenthesis and then type **,"Expressions")**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c64de-383">Expressions es el nombre del conjunto de datos en el que contabilizar las filas de datos.</span><span class="sxs-lookup"><span data-stu-id="c64de-383">Expressions is the name of the dataset in which to count data rows.</span></span>  
  
17. <span data-ttu-id="c64de-384">Expanda **Operadores** y haga clic en **Aritméticos**.</span><span class="sxs-lookup"><span data-stu-id="c64de-384">Expand **Operators** and click **Arithmetic**.</span></span>  
  
18. <span data-ttu-id="c64de-385">En la lista **Elemento**, haga doble clic en **Resto**.</span><span class="sxs-lookup"><span data-stu-id="c64de-385">In the **Item** list, double-click **Mod**.</span></span>  
  
19. <span data-ttu-id="c64de-386">Si el cursor no está ya inmediatamente después de `Mod`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-386">If the cursor is not already immediately after `Mod`, place it there.</span></span>  
  
20. <span data-ttu-id="c64de-387">Escriba **2 =0,**</span><span class="sxs-lookup"><span data-stu-id="c64de-387">Type  **2 =0,**</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c64de-388">Asegúrese de incluir un espacio antes de escribir el número 2.</span><span class="sxs-lookup"><span data-stu-id="c64de-388">Be sure you include a space before you type the number 2.</span></span>  
  
21. <span data-ttu-id="c64de-389">Haga clic en **Parámetros** y en la lista **Valores** , haga doble clic en **RowColor**.</span><span class="sxs-lookup"><span data-stu-id="c64de-389">Click **Parameters** and in the **Values** list, double-click **RowColor**.</span></span>  
  
22. <span data-ttu-id="c64de-390">Si el cursor no está ya inmediatamente después de `Parameters!RowColor.Value`, colóquelo ahí.</span><span class="sxs-lookup"><span data-stu-id="c64de-390">If the cursor is not already immediately after `Parameters!RowColor.Value`, place it there.</span></span>  
  
23. <span data-ttu-id="c64de-391">Tipo **, "blanco")**</span><span class="sxs-lookup"><span data-stu-id="c64de-391">Type **, "White")**</span></span>  
  
     <span data-ttu-id="c64de-392">La expresión completa es la siguiente: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span><span class="sxs-lookup"><span data-stu-id="c64de-392">The completed expression: `=IIf(RunningValue(Fields!FirstName.Value,Count, "Expressions") Mod 2 =0, Parameters!RowColor.Value, "White")`</span></span>  
  
24. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="run-the-report"></a><span data-ttu-id="c64de-393">Ejecutar el informe</span><span class="sxs-lookup"><span data-stu-id="c64de-393">Run the Report</span></span>  
  
1.  <span data-ttu-id="c64de-394">Si no está en la pestaña **Inicio**, haga clic en **Inicio** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="c64de-394">If not on the **Home** tab, click **Home** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c64de-395">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="c64de-395">Click **Run**.</span></span>  
  
3.  <span data-ttu-id="c64de-396">En la lista desplegable **Elegir color**, seleccione el color de las barras que no son blancas del informe.</span><span class="sxs-lookup"><span data-stu-id="c64de-396">In the **Choose color** drop-down list, select the color of the non-white bars on the report.</span></span>  
  
4.  <span data-ttu-id="c64de-397">Haga clic en **Ver informe**.</span><span class="sxs-lookup"><span data-stu-id="c64de-397">Click **View Report**.</span></span>  
  
     <span data-ttu-id="c64de-398">Los representadores de informes y las filas alternativas tienen el fondo que elija.</span><span class="sxs-lookup"><span data-stu-id="c64de-398">The report renders and alternating rows have the background that you chose.</span></span>  
  
##  <a name="optional-format-date-column"></a><a name="DateFormat"></a><span data-ttu-id="c64de-399">opta Dar formato a la columna de fecha</span><span class="sxs-lookup"><span data-stu-id="c64de-399">(optional) Format Date Column</span></span>  
 <span data-ttu-id="c64de-400">Dé formato a la columna **Last Purchase**, que contiene fechas.</span><span class="sxs-lookup"><span data-stu-id="c64de-400">Format the **Last Purchase** column, which contains dates.</span></span>  
  
#### <a name="to-format-date-column"></a><span data-ttu-id="c64de-401">Para dar formato a la columna de fecha</span><span class="sxs-lookup"><span data-stu-id="c64de-401">To format date column</span></span>  
  
1.  <span data-ttu-id="c64de-402">Haga clic en **Diseño** para volver a la vista de diseño.</span><span class="sxs-lookup"><span data-stu-id="c64de-402">Click **Design** to return to design view.</span></span>  
  
2.  <span data-ttu-id="c64de-403">Haga clic con el botón derecho en la celda de datos de **Última compra** y haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="c64de-403">Right-click the data cell for the **Last Purchase** column and click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="c64de-404">En el cuadro de diálogo **Propiedades de cuadro de texto** haga clic en **Número**, haga clic en **Fecha**, y, después, en el tipo **\*31/1/2000**.</span><span class="sxs-lookup"><span data-stu-id="c64de-404">In the **Text Box Properties** dialog box, click **Number**, click **Date**, and then click the type **\*1/31/2000**.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-add-a-report-title"></a><a name="Title"></a><span data-ttu-id="c64de-405">opta Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="c64de-405">(optional) Add a Report Title</span></span>  
 <span data-ttu-id="c64de-406">Agregue un título al informe.</span><span class="sxs-lookup"><span data-stu-id="c64de-406">Add a title to the report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="c64de-407">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="c64de-407">To add a report title</span></span>  
  
1.  <span data-ttu-id="c64de-408">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="c64de-408">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="c64de-409">Escriba **Resumen de comparación de ventas** y, después, haga clic fuera del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="c64de-409">Type **Sales Comparison Summary**, and then click outside the text box.</span></span>  
  
3.  <span data-ttu-id="c64de-410">Haga clic con el botón derecho en el cuadro de texto que contiene **Resumen de comparación de ventas** y haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="c64de-410">Right-click the text box that contains **Sales Comparison Summary** and click **Text Box Properties**.</span></span>  
  
4.  <span data-ttu-id="c64de-411">En el cuadro de diálogo **Propiedades de cuadro de texto** , haga clic en **Fuente**.</span><span class="sxs-lookup"><span data-stu-id="c64de-411">In the **Text Box Properties** dialog box, click **Font**.</span></span>  
  
5.  <span data-ttu-id="c64de-412">En la lista **Tamaño** , seleccione **18 pt**.</span><span class="sxs-lookup"><span data-stu-id="c64de-412">In the **Size** list, select **18pt**.</span></span>  
  
6.  <span data-ttu-id="c64de-413">En la lista **Color**, seleccione **Gris**.</span><span class="sxs-lookup"><span data-stu-id="c64de-413">In the **Color** list, select **Gray**.</span></span>  
  
7.  <span data-ttu-id="c64de-414">Seleccione **Negrita** y **Cursiva**.</span><span class="sxs-lookup"><span data-stu-id="c64de-414">Select  **Bold** and  **Italic**.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="optional-save-the-report"></a><a name="Save"></a><span data-ttu-id="c64de-415">opta Guardar el informe</span><span class="sxs-lookup"><span data-stu-id="c64de-415">(optional) Save the Report</span></span>  
 <span data-ttu-id="c64de-416">Puede guardar los informes en un servidor de informes, en una biblioteca de SharePoint o en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c64de-416">You can save reports to a report server, SharePoint library, or your computer.</span></span> <span data-ttu-id="c64de-417">Para obtener más información, consulte [Guardar informes &#40;Generador de informes&#41;](report-builder/saving-reports-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c64de-417">For more information, see [Saving Reports &#40;Report Builder&#41;](report-builder/saving-reports-report-builder.md).</span></span>  
  
 <span data-ttu-id="c64de-418">En este tutorial, guarde el informe en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c64de-418">In this tutorial, save the report to a report server.</span></span> <span data-ttu-id="c64de-419">Si no tiene acceso a un servidor de informes, guarde el informe en su equipo.</span><span class="sxs-lookup"><span data-stu-id="c64de-419">If you do not have access to a report server, save the report to your computer.</span></span>  
  
#### <a name="to-save-the-report-to-a-report-server"></a><span data-ttu-id="c64de-420">Para guardar el informe en un servidor de informes</span><span class="sxs-lookup"><span data-stu-id="c64de-420">To save the report to a report server</span></span>  
  
1.  <span data-ttu-id="c64de-421">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="c64de-421">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="c64de-422">Haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="c64de-422">Click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="c64de-423">Seleccione o escriba el nombre del servidor de informes donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="c64de-423">Select or type the name of the report server where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="c64de-424">Aparecerá el mensaje "Conectando con el servidor de informes".</span><span class="sxs-lookup"><span data-stu-id="c64de-424">The message "Connecting to report server" appears.</span></span> <span data-ttu-id="c64de-425">Una vez completada la conexión, verá el contenido de la carpeta de informes que el administrador del servidor de informes especificó como ubicación predeterminada para los informes.</span><span class="sxs-lookup"><span data-stu-id="c64de-425">When the connection is complete, you will see the contents of the report folder that the report server administrator specified as the default report location.</span></span>  
  
4.  <span data-ttu-id="c64de-426">En **Nombre**, reemplace el nombre predeterminado por **Resumen de comparación de ventas**.</span><span class="sxs-lookup"><span data-stu-id="c64de-426">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
5.  <span data-ttu-id="c64de-427">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="c64de-427">Click **Save**.</span></span>  
  
 <span data-ttu-id="c64de-428">El informe se guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="c64de-428">The report is saved to the report server.</span></span> <span data-ttu-id="c64de-429">El nombre del servidor de informes al que está conectado aparecerá en la barra de estado en la parte inferior de la ventana.</span><span class="sxs-lookup"><span data-stu-id="c64de-429">The name of report server that you are connected to appears in the status bar at the bottom of the window.</span></span>  
  
#### <a name="to-save-the-report-to-your-computer"></a><span data-ttu-id="c64de-430">Para guardar el informe en el equipo</span><span class="sxs-lookup"><span data-stu-id="c64de-430">To save the report to your computer</span></span>  
  
1.  <span data-ttu-id="c64de-431">En el botón **Generador de informes** , haga clic en **Guardar como**.</span><span class="sxs-lookup"><span data-stu-id="c64de-431">From the **Report Builder** button, click **Save As**.</span></span>  
  
2.  <span data-ttu-id="c64de-432">Haga clic en **Escritorio**, **Mis documentos**o **Mi PC**y vaya a la carpeta donde desea guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="c64de-432">Click **Desktop**, **My Documents**, or **My computer**, and then browse to the folder where you want to save the report.</span></span>  
  
3.  <span data-ttu-id="c64de-433">En **Nombre**, reemplace el nombre predeterminado por **Resumen de comparación de ventas**.</span><span class="sxs-lookup"><span data-stu-id="c64de-433">In **Name**, replace the default name with **Sales Comparison Summary**.</span></span>  
  
4.  <span data-ttu-id="c64de-434">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="c64de-434">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64de-435">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c64de-435">See Also</span></span>  
 <span data-ttu-id="c64de-436">[Expresiones &#40;Generador de informes y SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c64de-436">[Expressions &#40;Report Builder and SSRS&#41;](report-design/expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c64de-437">[Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c64de-437">[Expression Examples &#40;Report Builder and SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c64de-438">[Indicadores &#40;Generador de informes y SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c64de-438">[Indicators &#40;Report Builder and SSRS&#41;](report-design/indicators-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c64de-439">[Imágenes, cuadros de texto, rectángulos y líneas &#40;Generador de informes y SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c64de-439">[Images, Text Boxes, Rectangles, and Lines &#40;Report Builder and SSRS&#41;](report-design/rectangles-and-lines-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c64de-440">[Tablas &#40;Generador de informes y SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c64de-440">[Tables &#40;Report Builder  and SSRS&#41;](report-design/tables-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c64de-441">Agregar datos a un informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c64de-441">Add Data to a Report &#40;Report Builder and SSRS&#41;</span></span>](report-data/report-datasets-ssrs.md)  
  
  
