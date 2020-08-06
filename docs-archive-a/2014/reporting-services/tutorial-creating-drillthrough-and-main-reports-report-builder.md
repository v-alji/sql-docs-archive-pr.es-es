---
title: 'Tutorial: Crear informes principales y de obtención de detalles (Generador de informes) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7168c8d3-cef5-4c4a-a0bf-fff1ac5b8b71
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d7d30b59a0c5523ed50df06f8587bbd701ae4c79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748599"
---
# <a name="tutorial-creating-drillthrough-and-main-reports-report-builder"></a><span data-ttu-id="e0ac7-102">Tutorial: Crear informes principales y de obtención de detalles (Generador de informes)</span><span class="sxs-lookup"><span data-stu-id="e0ac7-102">Tutorial: Creating Drillthrough and Main Reports (Report Builder)</span></span>
  <span data-ttu-id="e0ac7-103">Este tutorial le enseña cómo crear dos tipos de informes: un informe detallado y un informe principal.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-103">This tutorial teaches you how to create two kinds of reports: a drillthrough report and a main report.</span></span> <span data-ttu-id="e0ac7-104">Los datos de ventas de ejemplo utilizados en estos informes se recuperan de un cubo de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-104">The sample sales data used in these reports is retrieved from an Analysis Services cube.</span></span> <span data-ttu-id="e0ac7-105">En la siguiente ilustración se muestran los informes que creará.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-105">The following illustration shows the reports you will create.</span></span>  
  
 <span data-ttu-id="e0ac7-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span><span class="sxs-lookup"><span data-stu-id="e0ac7-106">![rs_DrillthroughCubeTutorial](../../2014/tutorials/media/rs-drillthroughcubetutorial.gif "rs_DrillthroughCubeTutorial")</span></span>  
  
 <span data-ttu-id="e0ac7-107">En la ilustración siguiente se muestra cómo se muestra el valor del campo, juegos y juguetes, en el informe principal en el título del informe de obtención de detalles.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-107">The following illustration shows how the field value, Games and Toys, in the main report displays in the drillthrough report's title.</span></span> <span data-ttu-id="e0ac7-108">Los datos de la obtención de detalles pertenecen a la categoría de producto de Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-108">The data in the drillthrough pertains to the Games and Toys product category.</span></span>  
  
 <span data-ttu-id="e0ac7-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span><span class="sxs-lookup"><span data-stu-id="e0ac7-109">![rs_DrillthroughCubeTutorialParmExpr](../../2014/tutorials/media/rs-drillthroughcubetutorialparmexpr.gif "rs_DrillthroughCubeTutorialParmExpr")</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="e0ac7-110">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="e0ac7-110">What You Will Learn</span></span>  
 <span data-ttu-id="e0ac7-111">**En el informe detallado aprenderá a:**</span><span class="sxs-lookup"><span data-stu-id="e0ac7-111">**In the drillthrough report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="e0ac7-112">Crear un informe de matriz de obtención de detalles y un conjunto de datos desde el asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="e0ac7-112">Create a Drillthrough Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#DMatrixAndDataset)  
  
    1.  [<span data-ttu-id="e0ac7-113">Especificar una conexión de datos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-113">Specify a Data Connection</span></span>](#DConnection)  
  
    2.  [<span data-ttu-id="e0ac7-114">Crear una consulta MDX</span><span class="sxs-lookup"><span data-stu-id="e0ac7-114">Create an MDX Query</span></span>](#DMDXQuery)  
  
    3.  [<span data-ttu-id="e0ac7-115">Organizar los datos en estilo de grupos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-115">Organize Data into Groups Style</span></span>](#DLayout)  
  
    4.  [<span data-ttu-id="e0ac7-116">Agregar subtotales y totales</span><span class="sxs-lookup"><span data-stu-id="e0ac7-116">Add Subtotals and Totals</span></span>](#DTotals)  
  
    5.  [<span data-ttu-id="e0ac7-117">Elegir un estilo</span><span class="sxs-lookup"><span data-stu-id="e0ac7-117">Choose a Style</span></span>](#DStyle)  
  
2.  [<span data-ttu-id="e0ac7-118">Dar formato a los datos como moneda</span><span class="sxs-lookup"><span data-stu-id="e0ac7-118">Format Data as Currency</span></span>](#DFormat)  
  
3.  [<span data-ttu-id="e0ac7-119">Agregar columnas para mostrar valores de ventas en minigráficos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-119">Add columns to Show Sales Values in Sparklines</span></span>](#DSparkline)  
  
4.  [<span data-ttu-id="e0ac7-120">Agregar el título de informe con el nombre de categoría del producto</span><span class="sxs-lookup"><span data-stu-id="e0ac7-120">Add Report Title with Product Category Name</span></span>](#DReportTitle)  
  
5.  [<span data-ttu-id="e0ac7-121">Actualizar las propiedades de parámetro</span><span class="sxs-lookup"><span data-stu-id="e0ac7-121">Update Parameter Properties</span></span>](#DParameter)  
  
6.  [<span data-ttu-id="e0ac7-122">Guardar el informe en una biblioteca de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e0ac7-122">Save the Report to a SharePoint Library</span></span>](#DSave)  
  
 <span data-ttu-id="e0ac7-123">**En el informe principal aprenderá a:**</span><span class="sxs-lookup"><span data-stu-id="e0ac7-123">**In the main report you will learn how to:**</span></span>  
  
1.  [<span data-ttu-id="e0ac7-124">Crear un informe de matriz principal y un conjunto de datos desde el Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="e0ac7-124">Create the Main Matrix Report and Dataset from the Table or Matrix Wizard</span></span>](#MMatrixAndDataset)  
  
    1.  [<span data-ttu-id="e0ac7-125">Especificar una conexión de datos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-125">Specify a Data Connection</span></span>](#MConnection)  
  
    2.  [<span data-ttu-id="e0ac7-126">Crear una consulta MDX</span><span class="sxs-lookup"><span data-stu-id="e0ac7-126">Create an MDX Query</span></span>](#MMDXQuery)  
  
    3.  [<span data-ttu-id="e0ac7-127">Organizar los datos en grupos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-127">Organize Data into Groups</span></span>](#MLayout)  
  
    4.  [<span data-ttu-id="e0ac7-128">Agregar subtotales y totales</span><span class="sxs-lookup"><span data-stu-id="e0ac7-128">Add Subtotals and Totals</span></span>](#MTotals)  
  
    5.  [<span data-ttu-id="e0ac7-129">Elegir un estilo</span><span class="sxs-lookup"><span data-stu-id="e0ac7-129">Choose a Style</span></span>](#MStyle)  
  
2.  [<span data-ttu-id="e0ac7-130">Quitar la fila Total general</span><span class="sxs-lookup"><span data-stu-id="e0ac7-130">Remove the Grand Total Row</span></span>](#MGrandTotal)  
  
3.  [<span data-ttu-id="e0ac7-131">Configurar la acción del cuadro de texto para la obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="e0ac7-131">Configure Text Box Action for Drillthrough</span></span>](#MDrillthrough)  
  
4.  [<span data-ttu-id="e0ac7-132">Reemplazar los valores numérico por indicadores</span><span class="sxs-lookup"><span data-stu-id="e0ac7-132">Replace Numeric Values with Indicators</span></span>](#MIndicators)  
  
5.  [<span data-ttu-id="e0ac7-133">Actualizar las propiedades de parámetro</span><span class="sxs-lookup"><span data-stu-id="e0ac7-133">Update Parameter Properties</span></span>](#MParameter)  
  
6.  [<span data-ttu-id="e0ac7-134">Agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="e0ac7-134">Add a Report Title</span></span>](#MTitle)  
  
7.  [<span data-ttu-id="e0ac7-135">Guardar el informe en una biblioteca de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e0ac7-135">Save the Report to a SharePoint Library</span></span>](#MSave)  
  
8.  [<span data-ttu-id="e0ac7-136">Ejecutar los informes principal y detallado</span><span class="sxs-lookup"><span data-stu-id="e0ac7-136">Run the Main and Drillthrough Reports</span></span>](#MRunReports)  
  
 <span data-ttu-id="e0ac7-137">Tiempo estimado para completar este tutorial: 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-137">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ac7-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-138">Requirements</span></span>  
 <span data-ttu-id="e0ac7-139">Este tutorial requiere acceso al cubo de ventas de Contoso.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-139">This tutorial requires access to the Contoso Sales cube.</span></span> <span data-ttu-id="e0ac7-140">Este requisito se aplica al informe principal y al detallado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-140">This requirement applies to both the drillthrough and the main reports.</span></span> <span data-ttu-id="e0ac7-141">Para obtener más información sobre los requisitos, consulte [Requisitos previos para los tutoriales &#40;Generador de informes&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-141">For more information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-drillthrough-report-from-the-table-or-matrix-wizard"></a><a name="DMatrixAndDataset"></a><span data-ttu-id="e0ac7-142">1. crear un informe detallado desde el Asistente para tablas o matrices</span><span class="sxs-lookup"><span data-stu-id="e0ac7-142">1. Create a Drillthrough Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="e0ac7-143">En el cuadro de diálogo Introducción , cree un informe de matriz usando el **Asistente para tabla o matriz**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-143">From the Getting Started dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span> <span data-ttu-id="e0ac7-144">Hay dos modos disponibles en el asistente: diseño de informe y diseño de conjunto de datos compartido.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-144">There are two modes available in the wizard: report design and shared dataset design.</span></span> <span data-ttu-id="e0ac7-145">En este tutorial, utilizará el modo de diseño de informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-145">In this tutorial, you will use the report design mode.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="e0ac7-146">Para crear un informe nuevo</span><span class="sxs-lookup"><span data-stu-id="e0ac7-146">To create a new report</span></span>  
  
1.  <span data-ttu-id="e0ac7-147">Haga clic en **Inicio**, seleccione **Programas**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Generador de informes**y luego haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-147">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="e0ac7-148">Se abre el cuadro de diálogo **Introducción**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-148">The **Getting Started** dialog box opens.</span></span> <span data-ttu-id="e0ac7-149">Si no aparece, en el botón **generador de informes** , haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-149">If it does not appear, from the **Report Builder** button, click **New**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-150">En el panel de la izquierda, compruebe que está seleccionada la opción **Nuevo informe** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-150">In the left pane, verify that **New Report** is selected.</span></span>  
  
3.  <span data-ttu-id="e0ac7-151">En el panel derecho, compruebe que **Asistente para tabla o matriz** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-151">In the right pane, verify that **Table or Matrix Wizard** is selected.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="DConnection"></a><span data-ttu-id="e0ac7-152">1Una.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-152">1a.</span></span> <span data-ttu-id="e0ac7-153">Especificar una conexión de datos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-153">Specify a Data Connection</span></span>  
 <span data-ttu-id="e0ac7-154">Una conexión de datos contiene la información necesaria para conectarse a un origen de datos externo, por ejemplo un cubo de Analysis Services o una base de datos de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-154">A data connection contains the information necessary to connect to an external data source such as an Analysis Services cube or a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="e0ac7-155">Para especificar una conexión de datos, puede utilizar un origen de datos compartido del servidor de informes o crear un origen de datos incrustado que solo se utilice en este informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-155">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in this report.</span></span> <span data-ttu-id="e0ac7-156">En este tutorial, utilizará un origen del datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-156">In this tutorial, you will use an embedded data source.</span></span> <span data-ttu-id="e0ac7-157">Para obtener más información sobre cómo usar orígenes de datos compartidos, vea [Maneras alternativas de obtener una conexión de datos &#40;Generador de informes&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-157">To learn more about using a shared data source, see [Alternative Ways to Get a Data Connection &#40;Report Builder&#41;](../reporting-services/alternative-ways-to-get-a-data-connection-report-builder.md).</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="e0ac7-158">Para crear un origen de datos incrustado</span><span class="sxs-lookup"><span data-stu-id="e0ac7-158">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="e0ac7-159">En la página **Elegir un conjunto de datos** , seleccione **Crear un conjunto de datos**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-159">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="e0ac7-160">Se abre la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-160">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="e0ac7-161">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-161">Click **New**.</span></span> <span data-ttu-id="e0ac7-162">Se abre el cuadro de diálogo **Propiedades del origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-162">The **Data Source Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="e0ac7-163">En **Nombre**, escriba **Detalle de ventas en línea y por distribuidor** como nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-163">In **Name**, type **Online and Reseller Sales Detail** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="e0ac7-164">En **Seleccionar un tipo de conexión**, seleccione **Microsoft SQL Server Analysis Services**y, después, haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-164">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="e0ac7-165">En **Origen de datos**, compruebe que el origen de datos es **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-165">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="e0ac7-166">En **Nombre del servidor**, escriba el nombre de un servidor donde esté instalada una instancia de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-166">In **Server name**, type the name of a server where an instance of Analysis Services is installed.</span></span>  
  
7.  <span data-ttu-id="e0ac7-167">En la lista **Seleccione o escriba un nombre de base de datos**, seleccione el cubo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-167">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="e0ac7-168">Compruebe que **Cadena de conexión** contiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e0ac7-168">Verify that **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
     <span data-ttu-id="e0ac7-169">`<servername>` es el nombre de una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] con Analysis Services instalado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-169">The `<servername>` is the name of an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] with Analysis Services installed.</span></span>  
  
10. <span data-ttu-id="e0ac7-170">Haga clic en **Tipo de credenciales**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-170">Click **Credentials type**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0ac7-171">Dependiendo de cómo se configuran los permisos en el origen de datos, podría necesitar cambiar las opciones de autenticación predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-171">Depending on how permissions are configured on the data source, you might need to change the default authentication options.</span></span> <span data-ttu-id="e0ac7-172">Para más información, vea [Seguridad &#40;Generador de informes&#41;](report-builder/security-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-172">For more information, see [Security &#40;Report Builder&#41;](report-builder/security-report-builder.md).</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="e0ac7-173">Se abre la página **Elegir una conexión a un origen de datos** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-173">The **Choose a connection to a data source** page appears.</span></span>  
  
12. <span data-ttu-id="e0ac7-174">Para comprobar que se puede conectar al origen de datos, haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-174">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="e0ac7-175">Aparece el mensaje **Conexión creada correctamente** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-175">The message **Connection created successfully** appears.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="e0ac7-176">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-176">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="DMDXQuery"></a><span data-ttu-id="e0ac7-177">ter.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-177">1b.</span></span> <span data-ttu-id="e0ac7-178">Crear una consulta MDX</span><span class="sxs-lookup"><span data-stu-id="e0ac7-178">Create an MDX Query</span></span>  
 <span data-ttu-id="e0ac7-179">En un informe puede usar un conjunto de datos compartido que tenga una consulta predefinida o crear un conjunto de datos incrustado para usarlo exclusivamente en ese informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-179">In a report, you can use a shared dataset that has a predefined query, or you can create an embedded dataset for use only in your report.</span></span> <span data-ttu-id="e0ac7-180">En este tutorial, creará un conjunto de datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-180">In this tutorial, you will create an embedded dataset.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="e0ac7-181">Crear filtros de consulta</span><span class="sxs-lookup"><span data-stu-id="e0ac7-181">To create query filters</span></span>  
  
1.  <span data-ttu-id="e0ac7-182">En la página **diseñar una consulta** , en el panel metadatos, haga clic en el botón **(...)**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-182">On the **Design a query** page, in the Metadata pane, click the button **(...)**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-183">En el cuadro de diálogo **Selección de cubo** , haga clic en Ventas y, después, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-183">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="e0ac7-184">Si no quiere compilar la consulta MDX manualmente, haga clic en el icono ![Cambiar al modo de diseño](media/rsqdicon-designmode.gif "Cambiar al modo de diseño"), alterne el diseñador de consultas al modo Consulta, pegue la MDX completada en el diseñador de consultas y, después, vaya al paso 6 de [Crear el conjunto de datos](#DSkip).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-184">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 6 in [To create the dataset](#DSkip).</span></span>  
  
    ```  
    SELECT NON EMPTY { [Measures].[Sales Amount], [Measures].[Sales Return Amount] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS * [Product].[Product Subcategory Name].[Product Subcategory Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGS  
    ```  
  
3.  <span data-ttu-id="e0ac7-185">En el panel de Grupo de medida, expanda Canal y, después, arrastre la columna Nombre de canal hasta la columna **Jerarquía** del panel de filtro.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-185">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="e0ac7-186">El nombre de la dimensión, Canal, se agrega automáticamente a la columna **Dimensión** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-186">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="e0ac7-187">No cambie las columnas de **Dimensión** u **Operador** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-187">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="e0ac7-188">Para abrir la lista **Filtrar expresión** , haga clic en la flecha abajo en la columna **Filtrar expresión** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-188">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="e0ac7-189">En la lista de expresiones de filtro, expanda **Todos los canales**, haga clic en **En línea**, en **Distribuidor**y, después, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-189">In the filter expression list, expand **All Channel**, click **Online**, click **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e0ac7-190">La consulta incluye ahora un filtro para incluir solo estos canales: En línea y Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-190">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="e0ac7-191">Expanda la dimensión Territorio de ventas y arrastre el Grupo del territorio de ventas a la columna **Jerarquía** (bajo **Nombre de canal**).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-191">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column (below **Channel Name**).</span></span>  
  
7.  <span data-ttu-id="e0ac7-192">Abra la lista **Filtrar expresión** , expanda **All Sales Territory**(Todos los territorios de ventas), haga clic en **Norteamérica**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-192">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e0ac7-193">La consulta tiene ahora un filtro para incluir solamente las ventas de Norteamérica</span><span class="sxs-lookup"><span data-stu-id="e0ac7-193">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="e0ac7-194">En el panel Grupo de medida, expanda Fecha y, después, arrastre Año natural a la columna **Jerarquía** en el panel de filtro.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-194">In the Measure Group pane, expand Date, and then drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="e0ac7-195">El nombre de la dimensión, Fecha, se agrega automáticamente a la columna **Dimensión** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-195">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="e0ac7-196">No cambie las columnas de **Dimensión** u **Operador** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-196">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="e0ac7-197">Para abrir la lista **Filtrar expresión** , haga clic en la flecha abajo en la columna **Filtrar expresión** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-197">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="e0ac7-198">En la lista de expresiones de filtro, expanda **Todas las fechas**, haga clic en **Año 2009**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-198">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e0ac7-199">La consulta incluye ahora un filtro para incluir solo el año natural 2009.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-199">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="e0ac7-200">Crear el parámetro</span><span class="sxs-lookup"><span data-stu-id="e0ac7-200">To create the parameter</span></span>  
  
1.  <span data-ttu-id="e0ac7-201">Expanda la dimensión Producto y, después, arrastre el miembro Nombre de categoría de producto hasta la columna **Jerarquía** , bajo **Año natural**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-201">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Calendar Year**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-202">Abra la lista **Expresión de filtro** , haga clic en **Todos los productos**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-202">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-203">Active la casilla **Parámetro** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-203">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="e0ac7-204">La consulta incluye ahora el parámetro ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-204">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0ac7-205">El parámetro contiene los nombres de categorías de producto.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-205">The parameter contains the names of product categories.</span></span> <span data-ttu-id="e0ac7-206">Al hacer clic en el informe principal en un nombre de categoría de producto, su nombre se pasa al informe detallado utilizando este parámetro.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-206">When you click a product category name in the main report, its name is passed to the drillthrough report by using this parameter.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="DSkip"></a><span data-ttu-id="e0ac7-207">Para crear el conjunto de</span><span class="sxs-lookup"><span data-stu-id="e0ac7-207">To create the dataset</span></span>  
  
1.  <span data-ttu-id="e0ac7-208">Desde la dimensión Canal, arrastre Nombre de canal hasta el panel de datos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-208">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="e0ac7-209">Desde la dimensión Producto, arrastre Nombre de categoría de producto hasta el panel de datos y, después, colóquelo a la derecha de Nombre del canal.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-209">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="e0ac7-210">Desde la dimensión Producto, arrastre Product Subcategory Name (Nombre de subcategoría de producto) hasta el panel de datos y, después, colóquelo a la derecha de Nombre de categoría de producto.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-210">From the Product dimension, drag Product Subcategory Name to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="e0ac7-211">En el panel Metadatos, expanda **Medida**y, después, expanda Ventas.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-211">In the Metadata pane, expand **Measure**, and then expand Sales.</span></span>  
  
5.  <span data-ttu-id="e0ac7-212">Arrastre la medida Importe de venta hasta el panel de datos y, después, colóquela a la derecha de Product Subcategory Name (Nombre de subcategoría de producto).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-212">Drag the Sales Amount measure to the data pane, and then place it to the right of Product Subcategory Name.</span></span>  
  
6.  <span data-ttu-id="e0ac7-213">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar (!)**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-213">On the query designer toolbar, click **Run (!)**.</span></span>  
  
7.  <span data-ttu-id="e0ac7-214">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-214">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="DLayout"></a><span data-ttu-id="e0ac7-215">1C.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-215">1c.</span></span> <span data-ttu-id="e0ac7-216">Organizar los datos en grupos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-216">Organize Data into Groups</span></span>  
 <span data-ttu-id="e0ac7-217">Al seleccionar los campos por los que desea agrupar los datos, diseñe una matriz con filas y columnas que muestre datos detallados y datos agregados.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-217">When you select the fields on which to group the data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="e0ac7-218">Para organizar los datos en grupos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-218">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="e0ac7-219">Para cambiar a la vista de diseño, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-219">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-220">En la página **Organizar campos** , arrastre Product_Subcategory_Name a **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-220">On the **Arrange fields** page, drag Product_Subcategory_Name to **Row groups**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0ac7-221">Los espacios en los nombres se reemplazan con caracteres de subrayado (_).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-221">The spaces in the names are replaced with underscores (_).</span></span> <span data-ttu-id="e0ac7-222">Por ejemplo, Nombre de categoría de producto (Product Category Name) es Product_Category_Name.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-222">For example Product Category Name is Product_Category_Name.</span></span>  
  
3.  <span data-ttu-id="e0ac7-223">Arrastre Channel_Name a **Grupos de columnas**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-223">Drag Channel_Name to **Column groups**.</span></span>  
  
4.  <span data-ttu-id="e0ac7-224">Arrastre Sales_Amount a **Valores**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-224">Drag Sales_Amount to **Values**.</span></span>  
  
     <span data-ttu-id="e0ac7-225">Sales_Amount se agrega automáticamente mediante la función Sum, que es el agregado predeterminado para los campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-225">Sales_Amount is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="e0ac7-226">el valor es `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-226">The value is `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="e0ac7-227">Puede abrir la lista desplegable Para ver las demás funciones de agregado disponibles, abra la lista desplegable (no cambie la función de agregado).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-227">To view the other aggregate functions available, open the drop-down list (do not change the aggregate function).</span></span>  
  
5.  <span data-ttu-id="e0ac7-228">Arrastre Sales_Return_Amount hacia **Valores**y, después, colóquelo bajo `[Sum(Sales_Amount)]`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-228">Drag Sales_Return_Amount to **Values**, and then place it below `[Sum(Sales_Amount)]`.</span></span>  
  
     <span data-ttu-id="e0ac7-229">Los pasos 4 y 5 especifican los datos que deben aparecer en la matriz.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-229">Steps 4 and 5 specify the data to display in the matrix.</span></span>  
  
6.  <span data-ttu-id="e0ac7-230">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-230">Click **Next**.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="DTotals"></a><span data-ttu-id="e0ac7-231">1D.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-231">1d.</span></span> <span data-ttu-id="e0ac7-232">Agregar subtotales y totales</span><span class="sxs-lookup"><span data-stu-id="e0ac7-232">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="e0ac7-233">Después de crear grupos, puede agregar filas y darles formato, donde se mostrarán los valores agregados para los campos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-233">After you create groups, you can add and format rows where the aggregate values for the fields will display.</span></span> <span data-ttu-id="e0ac7-234">Puede decidir también si mostrar todos los datos o permitir que los usuarios expandan y contraigan de forma interactiva los datos agrupados.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-234">You can also choose whether to show all the data or to let a user expand and collapse grouped data interactively.</span></span>  
  
#### <a name="to-add-subtotals-and-totals"></a><span data-ttu-id="e0ac7-235">Para agregar subtotales y totales</span><span class="sxs-lookup"><span data-stu-id="e0ac7-235">To add subtotals and totals</span></span>  
  
1.  <span data-ttu-id="e0ac7-236">En la página **Elegir el diseño** , en **Opciones**, compruebe que esté seleccionada la opción **Mostrar subtotales y totales generales** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-236">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="e0ac7-237">El panel Vista previa del asistente muestra una matriz con cuatro filas.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-237">The wizard Preview pane displays a matrix with four rows.</span></span>  
  
2.  <span data-ttu-id="e0ac7-238">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-238">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="DStyle"></a><span data-ttu-id="e0ac7-239">1E.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-239">1e.</span></span> <span data-ttu-id="e0ac7-240">Elegir un estilo</span><span class="sxs-lookup"><span data-stu-id="e0ac7-240">Choose a Style</span></span>  
 <span data-ttu-id="e0ac7-241">Un estilo especifica un estilo de fuente, un conjunto de colores y un estilo de borde.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-241">A style specifies a font style, a set of colors, and a border style.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="e0ac7-242">Para especificar un estilo</span><span class="sxs-lookup"><span data-stu-id="e0ac7-242">To specify a style</span></span>  
  
1.  <span data-ttu-id="e0ac7-243">En la página **elegir un estilo** , en el panel estilos, seleccione pizarra.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-243">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="e0ac7-244">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="e0ac7-244">Click **Finish**.</span></span>  
  
     <span data-ttu-id="e0ac7-245">La tabla se agrega a la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-245">The table is added to the design surface.</span></span>  
  
3.  <span data-ttu-id="e0ac7-246">Haga clic en **Ejecutar (!)** para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-246">To preview the report, click **Run (!)**.</span></span>  
  
##  <a name="2-format-data-as-currency"></a><a name="DFormat"></a><span data-ttu-id="e0ac7-247">2. dar formato a los datos como moneda</span><span class="sxs-lookup"><span data-stu-id="e0ac7-247">2. Format Data as Currency</span></span>  
 <span data-ttu-id="e0ac7-248">Aplique el formato de moneda a los campos de cantidad de ventas en el informe detallado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-248">Apply currency formatting to the sales amount fields in the drillthrough report.</span></span>  
  
#### <a name="to-format-data-as-currency"></a><span data-ttu-id="e0ac7-249">Dar formato a los datos como moneda</span><span class="sxs-lookup"><span data-stu-id="e0ac7-249">To format data as currency</span></span>  
  
1.  <span data-ttu-id="e0ac7-250">Para cambiar a la vista de diseño, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-250">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-251">Para seleccionar y dar formato una vez a varias celdas, presione la tecla Ctrl y, a continuación, seleccione las celdas que contienen los datos de ventas numéricos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-251">To select and format multiple cells at one time, press the Ctrl key, and then select the cells that contain the numeric sales data.</span></span>  
  
3.  <span data-ttu-id="e0ac7-252">En la pestaña **Inicio** , en el grupo **Número** , haga clic en el botón **Moneda**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-252">On the **Home** tab, in the **Number** group, click **Currency**.</span></span>  
  
##  <a name="3-add-columns-to-show-sales-values-in-sparklines"></a><a name="DSparkline"></a><span data-ttu-id="e0ac7-253">3. Agregar columnas para mostrar valores de ventas en minigráficos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-253">3. Add Columns to Show Sales Values in Sparklines</span></span>  
 <span data-ttu-id="e0ac7-254">En lugar de mostrar de ventas y retornos de ventas como valores de moneda, el informe muestra los valores en un minigráfico.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-254">Instead of showing sales and sales returns as currency values, the report shows the values in a sparkline.</span></span>  
  
#### <a name="to-add-sparklines-to-columns"></a><span data-ttu-id="e0ac7-255">Para agregar minigráficos a las columnas</span><span class="sxs-lookup"><span data-stu-id="e0ac7-255">To add sparklines to columns</span></span>  
  
1.  <span data-ttu-id="e0ac7-256">Para cambiar a la vista de diseño, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-256">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-257">En el grupo Total de la matriz, Haga clic con el botón derecho en la columna **Importe de venta** , haga clic en **Insertar Columna**y, después, en **Derecha**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-257">In the Total group of the matrix, right-click the **Sales Amount** column, click **Insert Column**, and then click **Right**.</span></span>  
  
     <span data-ttu-id="e0ac7-258">Se agrega una columna vacía a la derecha de **Importe de venta**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-258">An empty column is added to the right of **Sales Amount**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-259">En la cinta de opciones, haga clic en **Rectángulo**y, después, haga clic en la celda vacía situada a la derecha de la celda `[Sum(Sales_Amount)]` en el grupo de filas [Product_Subcategory].</span><span class="sxs-lookup"><span data-stu-id="e0ac7-259">On the ribbon, click **Rectangle**, and then click the empty cell to the right of the `[Sum(Sales_Amount)]` cell in the [Product_Subcategory] row group.</span></span>  
  
4.  <span data-ttu-id="e0ac7-260">En la cinta de opciones, haga clic en el icono **Minigráficos** y, después, haga clic en la celda donde se agregó el rectángulo.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-260">On the ribbon, click the **Sparkline** icon, and then click the cell where the rectangle was added.</span></span>  
  
5.  <span data-ttu-id="e0ac7-261">En el cuadro de diálogo **Seleccionar tipo de minigráfico** , compruebe que está seleccionado el tipo **Columna** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-261">In the **Select Sparkline Type** dialog box, verify that **Column** type is selected.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="e0ac7-262">Haga clic con el botón secundario en el minigráfico.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-262">Right-click the sparkline.</span></span>  
  
8.  <span data-ttu-id="e0ac7-263">En el panel Datos del gráfico, haga clic en el icono **Agregar campo** y, después, haga clic en Sales_Amount.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-263">In the Chart Data pane, click the **Add field** icon, and then click Sales_Amount.</span></span>  
  
9. <span data-ttu-id="e0ac7-264">Haga clic con el botón secundario en la columna `Sales_Return_Amount` y, a continuación, agregue una columna a la derecha.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-264">Right-click the `Sales_Return_Amount` column, and then add a column to the right of it.</span></span>  
  
10. <span data-ttu-id="e0ac7-265">Repita los pasos del 2 al 6.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-265">Repeat steps 2 through 6.</span></span>  
  
11. <span data-ttu-id="e0ac7-266">Haga clic con el botón secundario en el minigráfico.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-266">Right-click the sparkline.</span></span>  
  
12. <span data-ttu-id="e0ac7-267">En el panel Datos del gráfico, haga clic en el icono **Agregar campo** y, después, haga clic en Sales_Return_Amount.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-267">In the Chart Data pane, click the **Add field** icon, and then click Sales_Return_Amount.</span></span>  
  
13. <span data-ttu-id="e0ac7-268">Haga clic en **Ejecutar**para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-268">To preview the report, click **Run**.</span></span>  
  
##  <a name="4-add-report-title-with-product-category-name"></a><a name="DReportTitle"></a><span data-ttu-id="e0ac7-269">4. agregar el título de informe con el nombre de categoría de producto</span><span class="sxs-lookup"><span data-stu-id="e0ac7-269">4. Add Report Title with Product Category Name</span></span>  
 <span data-ttu-id="e0ac7-270">Los títulos de informe aparecen en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-270">A report title appears at the top of the report.</span></span> <span data-ttu-id="e0ac7-271">Puede situar el título del informe en un encabezado de informe o, si el informe no lo utiliza, en un cuadro de texto en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-271">You can place the report title in a report header or, if the report does not use one, in a text box at the top of the report body.</span></span> <span data-ttu-id="e0ac7-272">En este tutorial, deberá utilizar el cuadro de texto que se coloca automáticamente en la parte superior del cuerpo del informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-272">In this tutorial, you will use the text box that is automatically placed at the top of the report body.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="e0ac7-273">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="e0ac7-273">To add a report title</span></span>  
  
1.  <span data-ttu-id="e0ac7-274">Para cambiar a la vista de diseño, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-274">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-275">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-275">On the design surface, click **Click to add title**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-276">Escriba **Ventas y devoluciones por categoría:**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-276">Type **Sales and Returns for Category:**.</span></span>  
  
4.  <span data-ttu-id="e0ac7-277">Haga clic con el botón derecho y, después, haga clic en **Crear marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-277">Right-click, and then click **Create Placeholder**.</span></span>  
  
5.  <span data-ttu-id="e0ac7-278">Haga clic en el botón **(fx)** , a la derecha de la lista **Valor** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-278">Click the **(fx)** button to the right of the **Value** list.</span></span>  
  
6.  <span data-ttu-id="e0ac7-279">En el cuadro de diálogo **Expresión** , en el panel Categoría, haga clic en **Conjunto de datos**y, después, haga doble clic en **en la lista** Valores `First(Product_Category_Name)`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-279">In the **Expression** dialog box, in the Category pane, click **Dataset**, and then in the **Values** list double-click `First(Product_Category_Name)`.</span></span>  
  
     <span data-ttu-id="e0ac7-280">El cuadro **Expresión** contiene la siguiente expresión:</span><span class="sxs-lookup"><span data-stu-id="e0ac7-280">The **Expression** box contains the following expression:</span></span>  
  
    ```  
    =First(Fields!Product_Category_Name.Value, "DataSet1")  
    ```  
  
7.  <span data-ttu-id="e0ac7-281">Haga clic en **Ejecutar**para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-281">To preview the report, click **Run**.</span></span>  
  
 <span data-ttu-id="e0ac7-282">El título del informe incluye el nombre de la primera categoría de producto.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-282">The report title includes the name of the first product category.</span></span> <span data-ttu-id="e0ac7-283">Después, tras ejecutar este informe como un informe detallado, el nombre de la categoría de producto cambiará dinámicamente, para reflejar el nombre de la categoría de producto en la que se hizo clic en el informe principal.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-283">Later, after you run this report as a drillthrough report, the product category name will dynamically change to reflect the name of the product category that was clicked in the main report.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="DParameter"></a><span data-ttu-id="e0ac7-284">5. actualizar las propiedades de los parámetros</span><span class="sxs-lookup"><span data-stu-id="e0ac7-284">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="e0ac7-285">De forma predeterminada los parámetros están visibles, lo que no es adecuado para este informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-285">By default parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="e0ac7-286">Actualizará las propiedades de parámetro para el informe detallado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-286">You will update the parameter properties for the drillthrough report.</span></span>  
  
#### <a name="to-hide-a-parameter"></a><span data-ttu-id="e0ac7-287">Ocultar un parámetro</span><span class="sxs-lookup"><span data-stu-id="e0ac7-287">To hide a parameter</span></span>  
  
1.  <span data-ttu-id="e0ac7-288">En el panel Datos de informe, expanda **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-288">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-289">Haga clic con el botón secundario en \@ ProductProductCategoryName y, a continuación, haga clic en **propiedades de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-289">Right-click \@ProductProductCategoryName, and then click **Parameter Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0ac7-290">El carácter \@ situado al lado del nombre indica que se trata de un parámetro.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-290">The \@ character next to the name indicates that this is a parameter.</span></span>  
  
3.  <span data-ttu-id="e0ac7-291">En la pestaña **General** , haga clic en **Oculto**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-291">On the **General** tab, click **Hidden**.</span></span>  
  
4.  <span data-ttu-id="e0ac7-292">En el cuadro **Pedir datos** , escriba **Categoría de producto**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-292">In the **Prompt** box, type **Product Category**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0ac7-293">Dado que se oculta el parámetro, nunca se utiliza esta petición.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-293">Because the parameter is hidden, this prompt is never used.</span></span>  
  
5.  <span data-ttu-id="e0ac7-294">Opcionalmente, haga clic en **Valores disponibles** y en **Valores predeterminados** para revisar sus opciones.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-294">Optionally, click **Available Values** and **Default Values** and review their options.</span></span> <span data-ttu-id="e0ac7-295">No cambie ninguna opción en estas pestañas.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-295">Do not change any options on these tabs.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-save-the-report-to-a-sharepoint-library"></a><a name="DSave"></a><span data-ttu-id="e0ac7-296">6. guardar el informe en una biblioteca de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e0ac7-296">6. Save the Report to a SharePoint Library</span></span>  
 <span data-ttu-id="e0ac7-297">Puede guardar el informe en una biblioteca de SharePoint, en un servidor de informes o en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-297">You can save the report to a SharePoint library, report server, or your computer.</span></span> <span data-ttu-id="e0ac7-298">Si guarda el informe en su equipo, no estarán disponibles varias características de [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , como elementos de informe y subinformes, no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-298">If you save the report to your computer, a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features such as report parts and subreports are not available.</span></span> <span data-ttu-id="e0ac7-299">En este tutorial guardará el informe en una biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-299">In this tutorial, you will save the report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="e0ac7-300">Para guardar el informe</span><span class="sxs-lookup"><span data-stu-id="e0ac7-300">To save the report</span></span>  
  
1.  <span data-ttu-id="e0ac7-301">Desde el botón Generador de informes, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-301">From the Report Builder button, click **Save**.</span></span> <span data-ttu-id="e0ac7-302">Se abre el cuadro de diálogo **Guardar como informe** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-302">The **Save As Report** dialog box opens.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0ac7-303">Si vuelve a guardar un informe, automáticamente se guarda en su ubicación anterior.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-303">If you are resaving a report, it is automatically resaved to its previous location.</span></span> <span data-ttu-id="e0ac7-304">Para cambiar la ubicación, use la opción **Guardar como** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-304">To change the location, use the **Save As** option.</span></span>  
  
2.  <span data-ttu-id="e0ac7-305">Para mostrar una lista de servidores de informes y sitios de SharePoint usados recientemente, haga clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-305">To show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-306">Seleccione o escriba el nombre del sitio de SharePoint donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-306">Select or type the name of the SharePoint site where you have permission to save reports.</span></span>  
  
     <span data-ttu-id="e0ac7-307">La URL de la biblioteca de SharePoint tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e0ac7-307">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
4.  <span data-ttu-id="e0ac7-308">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-308">Click **Save**.</span></span>  
  
     <span data-ttu-id="e0ac7-309">En**Sitios y servidores recientes** se enumeran las bibliotecas del sitio de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-309">**Recent Sites and Servers** lists the libraries on the SharePoint site.</span></span>  
  
5.  <span data-ttu-id="e0ac7-310">Navegue hasta la biblioteca donde guardará el informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-310">Navigate to the library where you will save the report.</span></span>  
  
6.  <span data-ttu-id="e0ac7-311">En el cuadro **Nombre** , reemplace el nombre predeterminado por **ResellerVSOnlineDrillthrough**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-311">In the **Name** box, replace the default name with **ResellerVSOnlineDrillthrough**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e0ac7-312">Guardará el informe principal en la misma ubicación.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-312">You will save the main report to the same location.</span></span> <span data-ttu-id="e0ac7-313">Si quiere guardar los informes detallados y principal en sitios o bibliotecas diferentes, debe actualizar la ruta de acceso de la acción **Ir a informe** en el informe principal.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-313">If you want to save the main and drillthrough reports to different sites or libraries, you must update the path of the **Go to report** action in the main report.</span></span>  
  
7.  <span data-ttu-id="e0ac7-314">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-314">Click **Save**.</span></span>  
  
##  <a name="1-create-a-new-report-from-the-table-or-matrix-wizard"></a><a name="MMatrixAndDataset"></a><span data-ttu-id="e0ac7-315">1. crear un nuevo informe a partir del Asistente para tabla o matriz</span><span class="sxs-lookup"><span data-stu-id="e0ac7-315">1. Create a New Report from the Table or Matrix Wizard</span></span>  
 <span data-ttu-id="e0ac7-316">En el cuadro de diálogo **Introducción** , cree un informe de matriz usando el **Asistente para tabla o matriz**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-316">From the **Getting Started** dialog box, create a matrix report by using the **Table or Matrix Wizard**.</span></span>  
  
#### <a name="to-create-a-new-report"></a><span data-ttu-id="e0ac7-317">Para crear un informe nuevo</span><span class="sxs-lookup"><span data-stu-id="e0ac7-317">To create a new report</span></span>  
  
1.  <span data-ttu-id="e0ac7-318">Haga clic en **Inicio**, seleccione **Programas**, [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Generador de informes**y luego haga clic en **Generador de informes**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-318">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Report Builder**, and then click **Report Builder**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-319">En el cuadro de diálogo **Introducción** , compruebe que está seleccionado **Nuevo informe** y, después, haga clic en **Asistente para tabla o matriz**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-319">In the **Getting Started** dialog box, verify that **New Report** is selected, and then click **Table or Matrix Wizard**.</span></span>  
  
##  <a name="1a-specify-a-data-connection"></a><a name="MConnection"></a><span data-ttu-id="e0ac7-320">1Una.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-320">1a.</span></span> <span data-ttu-id="e0ac7-321">Especificar una conexión de datos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-321">Specify a Data Connection</span></span>  
 <span data-ttu-id="e0ac7-322">Agregará un origen de datos incrustados al informe principal.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-322">You will add an embedded data source to the main report.</span></span>  
  
#### <a name="to-create-an-embedded-data-source"></a><span data-ttu-id="e0ac7-323">Para crear un origen de datos incrustado</span><span class="sxs-lookup"><span data-stu-id="e0ac7-323">To create an embedded data source</span></span>  
  
1.  <span data-ttu-id="e0ac7-324">En la página **Elegir un conjunto de datos** , seleccione **Crear un conjunto de datos**y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-324">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-325">Haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-325">Click **New**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-326">En **Nombre**, escriba **Ventas principales en línea y de distribuidor** como el nombre del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-326">In **Name**, type **Online and Reseller Sales Main** as the name for the data source.</span></span>  
  
4.  <span data-ttu-id="e0ac7-327">En **Seleccionar un tipo de conexión**, seleccione **Microsoft SQL Server Analysis Services**y, después, haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-327">In **Select a connection type**, select **Microsoft SQL Server Analysis Services**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="e0ac7-328">En **Origen de datos**, compruebe que el origen de datos es **Microsoft SQL Server Analysis Services (AdomdClient)**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-328">In **Data source**, verify that the data source is **Microsoft SQL Server Analysis Services (AdomdClient)**.</span></span>  
  
6.  <span data-ttu-id="e0ac7-329">En **nombre del servidor**, escriba el nombre de un servidor donde [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] esté instalada una instancia de.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-329">In **Server name**, type the name of a server where an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is installed.</span></span>  
  
7.  <span data-ttu-id="e0ac7-330">En la lista **Seleccione o escriba un nombre de base de datos**, seleccione el cubo de Contoso.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-330">In **Select or enter a database name**, select the Contoso cube.</span></span>  
  
8.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
9. <span data-ttu-id="e0ac7-331">Compruebe que la **Cadena de conexión** contiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e0ac7-331">Verify that the **Connection string** contains the following syntax:</span></span>  
  
    ```  
    Data Source=<servername>; Initial Catalog = Contoso  
    ```  
  
10. <span data-ttu-id="e0ac7-332">Haga clic en **Tipo de credenciales**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-332">Click **Credentials type**.</span></span>  
  
     <span data-ttu-id="e0ac7-333">Dependiendo de cómo se configuran los permisos en el origen de datos, podría necesitar cambiar la autenticación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-333">Depending on how permissions are configured on the data source, you might need to change the default authentication.</span></span>  
  
11. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
12. <span data-ttu-id="e0ac7-334">Para comprobar que se puede conectar al origen de datos, haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-334">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
13. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
14. <span data-ttu-id="e0ac7-335">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-335">Click **Next**.</span></span>  
  
##  <a name="1b-create-an-mdx-query"></a><a name="MMDXQuery"></a><span data-ttu-id="e0ac7-336">ter.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-336">1b.</span></span> <span data-ttu-id="e0ac7-337">Crear una consulta MDX</span><span class="sxs-lookup"><span data-stu-id="e0ac7-337">Create an MDX Query</span></span>  
 <span data-ttu-id="e0ac7-338">Después, cree un conjunto de datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-338">Next, create an embedded dataset.</span></span> <span data-ttu-id="e0ac7-339">Para esto, utilizará el diseñador de consultas para crear filtros, parámetros y miembros calculados, así como el propio conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-339">To do so, you will use the query designer to create filters, parameters, and calculated members as well as the dataset itself.</span></span>  
  
#### <a name="to-create-query-filters"></a><span data-ttu-id="e0ac7-340">Crear filtros de consulta</span><span class="sxs-lookup"><span data-stu-id="e0ac7-340">To create query filters</span></span>  
  
1.  <span data-ttu-id="e0ac7-341">En la página **diseñar una consulta** , en el panel metadatos, en la sección cubo, haga clic en los puntos suspensivos **(...)**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-341">On the **Design a query** page, in the Metadata pane, in the cube section, click the ellipsis **(...)**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-342">En el cuadro de diálogo **Selección de cubo** , haga clic en Ventas y, después, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-342">In the **Cube Selection** dialog box, click Sales, and then click **OK**.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="e0ac7-343">Si no quiere compilar la consulta MDX manualmente, haga clic en el icono ![Cambiar al modo de diseño](media/rsqdicon-designmode.gif "Cambiar al modo de diseño"), alterne el diseñador de consultas al modo Consulta, pegue la MDX completada en el diseñador de consultas y, después, vaya al paso 5 de [Crear el conjunto de datos](#MSkip).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-343">If you do not want to build the MDX query manually, click the ![Switch to Design mode](media/rsqdicon-designmode.gif "Switch to Design mode") icon, toggle the query designer to Query mode, paste the completed MDX to the query designer, and then proceed to step 5 in [To create the dataset](#MSkip).</span></span>  
  
    ```  
    WITH MEMBER [Measures].[Net QTY] AS [Measures].[Sales Quantity] -[Measures].[Sales Return Quantity] MEMBER [Measures].[Net Sales] AS [Measures].[Sales Amount] - [Measures].[Sales Return Amount] SELECT NON EMPTY { [Measures].[Net QTY], [Measures].[Net Sales] } ON COLUMNS, NON EMPTY { ([Channel].[Channel Name].[Channel Name].ALLMEMBERS * [Product].[Product Category Name].[Product Category Name].ALLMEMBERS ) } DIMENSION PROPERTIES MEMBER_CAPTION, MEMBER_UNIQUE_NAME ON ROWS FROM ( SELECT ( { [Date].[Calendar Year].&[2009] } ) ON COLUMNS FROM ( SELECT ( STRTOSET(@ProductProductCategoryName, CONSTRAINED) ) ON COLUMNS FROM ( SELECT ( { [Sales Territory].[Sales Territory Group].&[North America] } ) ON COLUMNS FROM ( SELECT ( { [Channel].[Channel Name].&[2], [Channel].[Channel Name].&[4] } ) ON COLUMNS FROM [Sales])))) WHERE ( [Sales Territory].[Sales Territory Group].&[North America], [Date].[Calendar Year].&[2009] ) CELL PROPERTIES VALUE, BACK_COLOR, FORE_COLOR, FORMATTED_VALUE, FORMAT_STRING, FONT_NAME, FONT_SIZE, FONT_FLAGSQuery text: Code.  
    ```  
  
3.  <span data-ttu-id="e0ac7-344">En el panel de Grupo de medida, expanda Canal y, después, arrastre la columna Nombre de canal hasta la columna **Jerarquía** del panel de filtro.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-344">In the Measure Group pane, expand Channel, and then drag Channel Name to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="e0ac7-345">El nombre de la dimensión, Canal, se agrega automáticamente a la columna **Dimensión** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-345">The dimension name, Channel, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="e0ac7-346">No cambie las columnas de **Dimensión** u **Operador** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-346">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
4.  <span data-ttu-id="e0ac7-347">Para abrir la lista **Filtrar expresión** , haga clic en la flecha abajo en la columna **Filtrar expresión** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-347">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
5.  <span data-ttu-id="e0ac7-348">En la lista de expresiones de filtro, expanda **Todos los canales**, haga clic en **En línea** y en **Distribuidor**y, después, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-348">In the filter expression list, expand **All Channel**, click **Online** and **Reseller**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e0ac7-349">La consulta incluye ahora un filtro para incluir solo estos canales: En línea y Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-349">The query now includes a filter to include only these channels: Online and Reseller.</span></span>  
  
6.  <span data-ttu-id="e0ac7-350">Expanda la dimensión territorio de ventas y, a continuación, arrastre el grupo territorio de ventas a la columna **jerarquía** , debajo de **nombre de canal**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-350">Expand the Sales Territory dimension, and then drag Sales Territory Group to the **Hierarchy** column, below **Channel Name**.</span></span>  
  
7.  <span data-ttu-id="e0ac7-351">Abra la lista **Filtrar expresión** , expanda **All Sales Territory**(Todos los territorios de ventas), haga clic en **Norteamérica**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-351">Open the **Filter Expression** list, expand **All Sales Territory**, click **North America**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e0ac7-352">La consulta tiene ahora un filtro para incluir solamente las ventas de Norteamérica</span><span class="sxs-lookup"><span data-stu-id="e0ac7-352">The query now has a filter to include only sales in North America.</span></span>  
  
8.  <span data-ttu-id="e0ac7-353">En el panel Grupo de medida, expanda Fecha y, después, arrastre Año natural a la columna **Jerarquía** en el panel de filtro.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-353">In the Measure Group pane, expand Date, and drag Calendar Year to the **Hierarchy** column in the filter pane.</span></span>  
  
     <span data-ttu-id="e0ac7-354">El nombre de la dimensión, Fecha, se agrega automáticamente a la columna **Dimensión** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-354">The dimension name, Date, is automatically added to the **Dimension** column.</span></span> <span data-ttu-id="e0ac7-355">No cambie las columnas de **Dimensión** u **Operador** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-355">Do not change the **Dimension** or **Operator** columns.</span></span>  
  
9. <span data-ttu-id="e0ac7-356">Para abrir la lista **Filtrar expresión** , haga clic en la flecha abajo en la columna **Filtrar expresión** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-356">To open the **Filter Expression** list, click the down arrow in the **Filter Expression** column.</span></span>  
  
10. <span data-ttu-id="e0ac7-357">En la lista de expresiones de filtro, expanda **Todas las fechas**, haga clic en **Año 2009**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-357">In the filter expression list, expand **All Date**, click **Year 2009**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e0ac7-358">La consulta incluye ahora un filtro para incluir solo el año natural 2009.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-358">The query now includes a filter to include only the calendar year 2009.</span></span>  
  
#### <a name="to-create-the-parameter"></a><span data-ttu-id="e0ac7-359">Crear el parámetro</span><span class="sxs-lookup"><span data-stu-id="e0ac7-359">To create the parameter</span></span>  
  
1.  <span data-ttu-id="e0ac7-360">Expanda la dimensión Producto y, después, arrastre el miembro Nombre de categoría de producto hasta la columna **Jerarquía** , bajo **Grupo del territorio de ventas**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-360">Expand the Product dimension, and then drag the Product Category Name member to the **Hierarchy** column below **Sales Territory Group**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-361">Abra la lista **Expresión de filtro** , haga clic en **Todos los productos**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-361">Open the **Filter Expression** list, click **All Products**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-362">Active la casilla **Parámetro** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-362">Click the **Parameter** checkbox.</span></span> <span data-ttu-id="e0ac7-363">La consulta incluye ahora el parámetro ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-363">The query now includes the parameter ProductProductCategoryName.</span></span>  
  
#### <a name="to-create-calculated-members"></a><span data-ttu-id="e0ac7-364">Crear miembros calculados</span><span class="sxs-lookup"><span data-stu-id="e0ac7-364">To create calculated members</span></span>  
  
1.  <span data-ttu-id="e0ac7-365">Coloque el cursor dentro del panel Miembros calculados, haga clic con el botón derecho y, después, haga clic en **Nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-365">Place the cursor inside the Calculated Members pane, right-click, and then click **New Calculated Member**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-366">En el panel metadatos, expanda **medidas** y, a continuación, expanda ventas.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-366">In the Metadata pane, expand **Measures** and then expand Sales.</span></span>  
  
3.  <span data-ttu-id="e0ac7-367">Arrastre la medida Sales Quantity al cuadro **Expresión** , escriba el carácter de resta (-) y, después, arrastre la medida Sales Return Quantity al cuadro **Expresión** ; colóquela después del carácter de resta.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-367">Drag the Sales Quantity measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Quantity measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="e0ac7-368">El siguiente código muestra la expresión:</span><span class="sxs-lookup"><span data-stu-id="e0ac7-368">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Quantity] - [Measures].[Sales Return Quantity]  
    ```  
  
4.  <span data-ttu-id="e0ac7-369">En el cuadro Nombre, escriba **Net QTY**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-369">In the Name box, type **Net QTY**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e0ac7-370">En el panel Miembros calculados se muestra el miembro calculado **Net QTY** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-370">The Calculated Members pane lists the **Net QTY** calculated member.</span></span>  
  
5.  <span data-ttu-id="e0ac7-371">Haga clic con el botón derecho en **Miembros calculados**y, después, haga clic en **Nuevo miembro calculado**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-371">Right-click **Calculated Members**, and then click **New Calculated Member**.</span></span>  
  
6.  <span data-ttu-id="e0ac7-372">En el panel Metadatos, expanda **Medidas**y, después, expanda Ventas.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-372">In the Metadata pane, expand **Measures**, and then expand Sales.</span></span>  
  
7.  <span data-ttu-id="e0ac7-373">Arrastre la medida Sales Amount al cuadro **Expresión** , escriba el carácter de resta (-) y, después, arrastre la medida Sales Return Amount al cuadro **Expresión** ; colóquela después del carácter de resta.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-373">Drag the Sales Amount measure to the **Expression** box, type the subtraction character (-), and then drag the Sales Return Amount measure to the **Expression** box; place it after the subtraction character.</span></span>  
  
     <span data-ttu-id="e0ac7-374">El siguiente código muestra la expresión:</span><span class="sxs-lookup"><span data-stu-id="e0ac7-374">The following code shows the expression:</span></span>  
  
    ```  
    [Measures].[Sales Amount] - [Measures].[Sales Return Amount]  
    ```  
  
8.  <span data-ttu-id="e0ac7-375">En el cuadro **Nombre** , escriba  **Ventas netas**y, después, haga clic en **Aceptar**. En el panel Miembros calculados se muestra el miembro calculado **Ventas netas** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-375">In the **Name** box, type  **Net Sales**, and then click **OK**.The Calculated Members pane lists the **Net Sales** calculated member.</span></span>  
  
###  <a name="to-create-the-dataset"></a><a name="MSkip"></a><span data-ttu-id="e0ac7-376">Para crear el conjunto de</span><span class="sxs-lookup"><span data-stu-id="e0ac7-376">To create the dataset</span></span>  
  
1.  <span data-ttu-id="e0ac7-377">Desde la dimensión Canal, arrastre Nombre de canal hasta el panel de datos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-377">From the Channel dimension, drag Channel Name to the data pane.</span></span>  
  
2.  <span data-ttu-id="e0ac7-378">Desde la dimensión Producto, arrastre Nombre de categoría de producto hasta el panel de datos y, después, colóquelo a la derecha de Nombre del canal.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-378">From the Product dimension, drag Product Category Name to the data pane, and then place it to the right of Channel Name.</span></span>  
  
3.  <span data-ttu-id="e0ac7-379">Desde **Miembros calculados**, arrastre `Net QTY` al panel de datos y colóquelo a la derecha de Nombre de categoría de producto.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-379">From **Calculated Members**, drag `Net QTY` to the data pane, and then place it to the right of Product Category Name.</span></span>  
  
4.  <span data-ttu-id="e0ac7-380">Desde Miembros calculados, arrastre Ventas netas al panel de datos y colóquelo a la derecha de `Net QTY`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-380">From Calculated Members, drag Net Sales to the data pane, and then place it to the right of `Net QTY`.</span></span>  
  
5.  <span data-ttu-id="e0ac7-381">En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar (!)**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-381">On the query designer toolbar, click **Run (!)**.</span></span>  
  
     <span data-ttu-id="e0ac7-382">Revise el conjunto de resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-382">Review the query result set.</span></span>  
  
6.  <span data-ttu-id="e0ac7-383">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-383">Click **Next**.</span></span>  
  
##  <a name="1c-organize-data-into-groups"></a><a name="MLayout"></a><span data-ttu-id="e0ac7-384">1C.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-384">1c.</span></span> <span data-ttu-id="e0ac7-385">Organizar los datos en grupos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-385">Organize Data into Groups</span></span>  
 <span data-ttu-id="e0ac7-386">Al seleccionar los campos por los que desea agrupar los datos, diseñe una matriz con filas y columnas que muestre datos detallados y datos agregados.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-386">When you select the fields on which to group data, you design a matrix with rows and columns that displays detail and aggregated data.</span></span>  
  
#### <a name="to-organize-data-into-groups"></a><span data-ttu-id="e0ac7-387">Para organizar los datos en grupos</span><span class="sxs-lookup"><span data-stu-id="e0ac7-387">To organize data into groups</span></span>  
  
1.  <span data-ttu-id="e0ac7-388">En la página **Organizar campos** , arrastre Product_Category_Name a **Grupos de filas**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-388">On the **Arrange fields** page, drag Product_Category_Name to **Row groups**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-389">Arrastre Channel_Name a **Grupos de columnas**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-389">Drag Channel_Name to **Column groups**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-390">Arrastre `Net_QTY` a **Valores**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-390">Drag `Net_QTY` to **Values**.</span></span>  
  
     <span data-ttu-id="e0ac7-391">`Net_QTY` se suma automáticamente mediante la función Sum, que es el agregado predeterminado para los campos numéricos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-391">`Net_QTY` is automatically aggregated by the Sum function, the default aggregate for numeric fields.</span></span> <span data-ttu-id="e0ac7-392">el valor es `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-392">The value is `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="e0ac7-393">Para ver las demás funciones de agregado disponibles abra la lista desplegable .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-393">To view the other aggregate functions available, open the drop-down list.</span></span> <span data-ttu-id="e0ac7-394">No cambie la función de agregado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-394">Do not change the aggregate function.</span></span>  
  
4.  <span data-ttu-id="e0ac7-395">Arrastre `Net_Sales_Return` a **Valores** y después colóquelo bajo `[Sum(Net_QTY)]`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-395">Drag `Net_Sales_Return` to **Values** and then place it below `[Sum(Net_QTY)]`.</span></span>  
  
     <span data-ttu-id="e0ac7-396">Los pasos 3 y 4 especifican los datos que deben mostrarse en la matriz.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-396">Steps 3 and 4 specify the data to display in the matrix.</span></span>  
  
##  <a name="1d-add-subtotals-and-totals"></a><a name="MTotals"></a><span data-ttu-id="e0ac7-397">1D.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-397">1d.</span></span> <span data-ttu-id="e0ac7-398">Agregar subtotales y totales</span><span class="sxs-lookup"><span data-stu-id="e0ac7-398">Add Subtotals and Totals</span></span>  
 <span data-ttu-id="e0ac7-399">Puede mostrar subtotales y totales generales en informes.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-399">You can show subtotals and grand totals in reports.</span></span> <span data-ttu-id="e0ac7-400">Los datos del informe principal muestran como un indicador; quitará el total general cuando complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-400">The data in the main report displays as an indicator; you will remove the grand total after you complete the wizard.</span></span>  
  
#### <a name="to-add-subtotals-and-grand-totals"></a><span data-ttu-id="e0ac7-401">Agregar subtotales y totales generales</span><span class="sxs-lookup"><span data-stu-id="e0ac7-401">To add subtotals and grand totals</span></span>  
  
1.  <span data-ttu-id="e0ac7-402">En la página **Elegir el diseño** , en **Opciones**, compruebe que esté seleccionada la opción **Mostrar subtotales y totales generales** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-402">On the **Choose the layout** page, under **Options**, verify that **Show subtotals and grand totals** is selected.</span></span>  
  
     <span data-ttu-id="e0ac7-403">El panel Vista previa del asistente muestra una matriz con cuatro filas.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-403">The wizard Preview pane displays a matrix with four rows.</span></span>  <span data-ttu-id="e0ac7-404">Al ejecutar el informe, cada fila se mostrará de la siguiente manera: la primera fila es el grupo de columnas, la segunda fila contiene los encabezados de columna, la tercera fila contiene los datos de la categoría de producto (`[Sum(Net_ QTY)]` y `[Sum(Net_Sales)]`y la fila cuarta contiene los totales.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-404">When you run the report, each row will display in the following way: The first row is the column group, the second row contains the column headings, the third row contains the product category data (`[Sum(Net_ QTY)]` and `[Sum(Net_Sales)]`, and the fourth row contains the totals.</span></span>  
  
2.  <span data-ttu-id="e0ac7-405">Haga clic en **Next**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-405">Click **Next**.</span></span>  
  
##  <a name="1e-choose-a-style"></a><a name="MStyle"></a><span data-ttu-id="e0ac7-406">1E.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-406">1e.</span></span> <span data-ttu-id="e0ac7-407">Elegir un estilo</span><span class="sxs-lookup"><span data-stu-id="e0ac7-407">Choose a Style</span></span>  
 <span data-ttu-id="e0ac7-408">Aplique el estilo Pizarra al informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-408">Apply the Slate style to the report.</span></span> <span data-ttu-id="e0ac7-409">Es el mismo estilo que usa el informe detallado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-409">This is the same style that the drillthrough report uses.</span></span>  
  
#### <a name="to-specify-a-style"></a><span data-ttu-id="e0ac7-410">Para especificar un estilo</span><span class="sxs-lookup"><span data-stu-id="e0ac7-410">To specify a style</span></span>  
  
1.  <span data-ttu-id="e0ac7-411">En la página **elegir un estilo** , en el panel estilos, seleccione pizarra.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-411">On the **Choose a Style** page, in the Styles pane, select Slate.</span></span>  
  
2.  <span data-ttu-id="e0ac7-412">Haga clic en **Finalizar**</span><span class="sxs-lookup"><span data-stu-id="e0ac7-412">Click **Finish**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-413">Haga clic en **Ejecutar**para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-413">To preview the report, click **Run**.</span></span>  
  
##  <a name="2-remove-the-grand-total-row"></a><a name="MGrandTotal"></a><span data-ttu-id="e0ac7-414">2. quitar la fila de total general</span><span class="sxs-lookup"><span data-stu-id="e0ac7-414">2. Remove the Grand Total Row</span></span>  
 <span data-ttu-id="e0ac7-415">Los valores de datos se muestran como estados del indictor, incluyendo los totales del grupo de columna.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-415">The data values are shown as indictor states, including the column group totals.</span></span> <span data-ttu-id="e0ac7-416">Quite la fila que muestra el total general.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-416">Remove the row that displays the grand total.</span></span>  
  
#### <a name="to-remove-the-grand-total-row"></a><span data-ttu-id="e0ac7-417">Quitar la fila del total general</span><span class="sxs-lookup"><span data-stu-id="e0ac7-417">To remove the grand total row</span></span>  
  
1.  <span data-ttu-id="e0ac7-418">Para cambiar a la vista de diseño, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-418">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-419">Haga clic en la fila Total (la última fila de la matriz), haga clic con el botón derecho y, después, haga clic en **Eliminar filas**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-419">Click the Total row (the last row in the matrix), right-click, and then click **Delete Rows**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-420">Haga clic en **Ejecutar**para obtener la vista previa del informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-420">To preview the report, click **Run**.</span></span>  
  
##  <a name="3-configure-text-box-action-for-drillthrough"></a><a name="MDrillthrough"></a><span data-ttu-id="e0ac7-421">3. configurar la acción del cuadro de texto para la obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="e0ac7-421">3. Configure Text Box Action for Drillthrough</span></span>  
 <span data-ttu-id="e0ac7-422">Para habilitar la obtención de detalles, especifique una acción en un cuadro de texto en el informe principal.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-422">To enable the drillthrough, specify an action on a text box in the main report.</span></span>  
  
#### <a name="to-enable-an-action"></a><span data-ttu-id="e0ac7-423">Habilitar una acción</span><span class="sxs-lookup"><span data-stu-id="e0ac7-423">To enable an action</span></span>  
  
1.  <span data-ttu-id="e0ac7-424">Para cambiar a la vista de diseño, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-424">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-425">Haga clic con el botón derecho en la celda que contiene Product_Category_Name y, después, haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-425">Right-click the cell that contains Product_Category_Name, and then click **Text Box Properties**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-426">Haz clic en la pestaña **Acción**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-426">Click the **Action** tab.</span></span>  
  
4.  <span data-ttu-id="e0ac7-427">Seleccione **ir a informe.**</span><span class="sxs-lookup"><span data-stu-id="e0ac7-427">Select **Go to report.**</span></span>  
  
5.  <span data-ttu-id="e0ac7-428">En **Especificar un informe**, haga clic en **Examinar**y, después, ubique el informe detallado denominado ResellerVSOnlineDrillthrough.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-428">In **Specify a report**, click **Browse**, and then locate the drillthrough report named ResellerVSOnlineDrillthrough.</span></span>  
  
6.  <span data-ttu-id="e0ac7-429">Agregue un nuevo parámetro para pasárselo al informe detallado y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-429">To add a parameter to run the drillthrough report, click **Add**.</span></span>  
  
7.  <span data-ttu-id="e0ac7-430">En la lista **Nombre** , seleccione ProductProductCategoryName.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-430">In the **Name** list, select ProductProductCategoryName.</span></span>  
  
8.  <span data-ttu-id="e0ac7-431">En **Valor**, escriba `[Product_Category_Name.UniqueName]`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-431">In **Value**, type `[Product_Category_Name.UniqueName]`.</span></span>  
  
     <span data-ttu-id="e0ac7-432">Product_Category_Name es un campo del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-432">Product_Category_Name is a field in the dataset.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e0ac7-433">Debe incluir la propiedad `UniqueName` porque la acción de obtención de detalles requiere un valor único.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-433">You must include the `UniqueName` property because the drillthrough action requires a unique value.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-format-the-drillthrough-field"></a><span data-ttu-id="e0ac7-434">Dar formato al campo de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="e0ac7-434">To format the drillthrough field</span></span>  
  
1.  <span data-ttu-id="e0ac7-435">Haga clic con el botón derecho en la celda que contiene `Product_Category_Name`y, después, haga clic en **Propiedades de cuadro de texto**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-435">Right-click the cell that contains the `Product_Category_Name`, and then click **Text Box Properties**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-436">Haga clic en la pestaña **Fuente** .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-436">Click the **Font** tab.</span></span>  
  
3.  <span data-ttu-id="e0ac7-437">En la lista **Efectos** , seleccione **Subrayado**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-437">In the **Effects** list, select **Underline**.</span></span>  
  
4.  <span data-ttu-id="e0ac7-438">En la lista **Color** , seleccione **Azul**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-438">In the **Color** list, select **Blue**.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="e0ac7-439">Para obtener una vista previa de un informe, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-439">To preview your report, click **Run**.</span></span>  
  
 <span data-ttu-id="e0ac7-440">Los nombres de la categoría de producto tienen el formato de vínculo común (azul y subrayado).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-440">The product category names are in the common link format (blue and underlined).</span></span>  
  
##  <a name="4-replace-numeric-values-with-indicators"></a><a name="MIndicators"></a><span data-ttu-id="e0ac7-441">4. reemplazar valores numéricos por indicadores</span><span class="sxs-lookup"><span data-stu-id="e0ac7-441">4. Replace Numeric Values with Indicators</span></span>  
 <span data-ttu-id="e0ac7-442">Utilice los indicadores para mostrar el estado de cantidades y ventas para los canales En línea y Distribuidor.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-442">Use indicators to show the state of quantities and sales for Online and Reseller channels.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-qty-values"></a><span data-ttu-id="e0ac7-443">Agregar un indicador para los valores Net QTY</span><span class="sxs-lookup"><span data-stu-id="e0ac7-443">To add an indicator for Net QTY values</span></span>  
  
1.  <span data-ttu-id="e0ac7-444">Para cambiar a la vista de diseño, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-444">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-445">En la cinta de opciones, haga clic en el icono **Rectángulo** y, después, haga clic en la celda `[Sum(Net QTY)]` del grupo de filas `[Product_Category_Name]` del grupo de columnas `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-445">On the ribbon, click the **Rectangle** icon, and then click in the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
3.  <span data-ttu-id="e0ac7-446">En la cinta de opciones, haga clic en el icono **Indicador** y, después, haga clic dentro del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-446">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span> <span data-ttu-id="e0ac7-447">El cuadro de diálogo **Seleccionar tipo de indicador** se abre con el indicador **Direccional** seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-447">The **Select Indicator Type** dialog box opens with the **Directional** indicator selected.</span></span>  
  
4.  <span data-ttu-id="e0ac7-448">Escriba el tipo **3 Señales** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-448">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e0ac7-449">Haga clic con el botón derecho en el indicador y en el panel de Datos del medidor, haga clic en la flecha abajo situada junto a **(No especificado)**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-449">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="e0ac7-450">Seleccione `Net_QTY`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-450">Select `Net_QTY`.</span></span>  
  
6.  <span data-ttu-id="e0ac7-451">Repita los pasos del 2 al 5 para la celda `[Sum(Net QTY)]` del grupo de filas `[Product_Category_Name]` dentro de **Total**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-451">Repeat steps 2 through 5 for the `[Sum(Net QTY)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
#### <a name="to-add-an-indicator-for-net-sales-values"></a><span data-ttu-id="e0ac7-452">Agregar un indicador para los valores Net Sales</span><span class="sxs-lookup"><span data-stu-id="e0ac7-452">To add an indicator for Net Sales values</span></span>  
  
1.  <span data-ttu-id="e0ac7-453">En la cinta de opciones, haga clic en el icono **Rectángulo** y, después, haga clic dentro de la celda `[Sum(Net_Sales)]` del grupo de filas `[Product_Category_Name]` del grupo de columnas `Channel_Name` .</span><span class="sxs-lookup"><span data-stu-id="e0ac7-453">On the ribbon, click the **Rectangle** icon, and then click inside the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group in the `Channel_Name` column group.</span></span>  
  
2.  <span data-ttu-id="e0ac7-454">En la cinta de opciones, haga clic en el icono **Indicador** y, después, haga clic dentro del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-454">On the ribbon, click the **Indicator** icon, and then click inside the rectangle.</span></span>  
  
3.  <span data-ttu-id="e0ac7-455">Escriba el tipo **3 Señales** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-455">Click the **3 Signs** type, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="e0ac7-456">Haga clic con el botón derecho en el indicador y en el panel de Datos del medidor, haga clic en la flecha abajo situada junto a **(No especificado)**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-456">Right-click the indicator and in the Gauge Data pane, click the down arrow next to **(Unspecified)**.</span></span> <span data-ttu-id="e0ac7-457">Seleccione `Net_Sales`.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-457">Select `Net_Sales`.</span></span>  
  
5.  <span data-ttu-id="e0ac7-458">Repita los pasos del 1 al 4 para la celda `[Sum(Net_Sales)]` del grupo de filas `[Product_Category_Name]` dentro de **Total**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-458">Repeat steps 1 through 4 for the `[Sum(Net_Sales)]` cell in the `[Product_Category_Name]` row group within **Total**.</span></span>  
  
6.  <span data-ttu-id="e0ac7-459">Para obtener una vista previa de un informe, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-459">To preview your report, click **Run**.</span></span>  
  
##  <a name="5-update-parameter-properties"></a><a name="MParameter"></a><span data-ttu-id="e0ac7-460">5. actualizar las propiedades de los parámetros</span><span class="sxs-lookup"><span data-stu-id="e0ac7-460">5. Update Parameter Properties</span></span>  
 <span data-ttu-id="e0ac7-461">De forma predeterminada, los parámetros están visibles, lo que no es adecuado para este informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-461">By default, parameters are visible, which is not appropriate for this report.</span></span> <span data-ttu-id="e0ac7-462">Actualizará las propiedades de parámetro para hacer el parámetro interno.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-462">You will update the parameter properties to make the parameter internal.</span></span>  
  
#### <a name="to-make-the-parameter-internal"></a><span data-ttu-id="e0ac7-463">Realizar el parámetro interno</span><span class="sxs-lookup"><span data-stu-id="e0ac7-463">To make the parameter internal</span></span>  
  
1.  <span data-ttu-id="e0ac7-464">En el panel Datos de informe, expanda **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-464">In the Report Data pane, expand **Parameters**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-465">Haga clic con el botón derecho en `@ProductProductCategoryName,` y, después, haga clic en **Propiedades de parámetro**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-465">Right-click `@ProductProductCategoryName,` and then click **Parameter Properties**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-466">En la pestaña **General** , haga clic en **Interno**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-466">On the **General** tab, click **Internal**.</span></span>  
  
4.  <span data-ttu-id="e0ac7-467">Opcionalmente, haga clic en las pestañas **Valores disponibles** y **Valores predeterminados** para revisar sus opciones.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-467">Optionally, click the **Available Values** and **Default Values** tabs and review their options.</span></span> <span data-ttu-id="e0ac7-468">No cambie ninguna opción en estas pestañas.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-468">Do not change any options on these tabs.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="6-add-a-report-title"></a><a name="MTitle"></a><span data-ttu-id="e0ac7-469">6. agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="e0ac7-469">6. Add a Report Title</span></span>  
 <span data-ttu-id="e0ac7-470">Agregar un título al informe principal.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-470">Add a title to the main report.</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="e0ac7-471">Para agregar un título de informe</span><span class="sxs-lookup"><span data-stu-id="e0ac7-471">To add a report title</span></span>  
  
1.  <span data-ttu-id="e0ac7-472">En la superficie de diseño, haga clic en **Haga clic para agregar título**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-472">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-473">Escriba **Ventas por categoría de producto de 2009: categoría En línea y Distribuidor**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-473">Type **2009 Product Category Sales: Online and Reseller Category:**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-474">Seleccione el texto que escribió.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-474">Select the text you typed.</span></span>  
  
4.  <span data-ttu-id="e0ac7-475">En la pestaña **Inicio** de la cinta de opciones, en el grupo Fuentes, seleccione la fuente **Times New Roman** , tamaño **16 pt** , y los estilos **negrita** y **cursiva** Cinta de opciones.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-475">On the **Home** tab of the ribbon, in the Font group, select the **Times New Roman** font, **16pt** size, and the **Bold** and **Italic** styles.</span></span>  
  
5.  <span data-ttu-id="e0ac7-476">Para obtener una vista previa de un informe, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-476">To preview your report, click **Run**.</span></span>  
  
##  <a name="7-save-the-main-report-to-a-sharepoint-library"></a><a name="MSave"></a><span data-ttu-id="e0ac7-477">7. guardar el informe principal en una biblioteca de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e0ac7-477">7. Save the Main Report to a SharePoint Library</span></span>  
 <span data-ttu-id="e0ac7-478">Guarde el informe principal en una biblioteca de SharePoint</span><span class="sxs-lookup"><span data-stu-id="e0ac7-478">Save the main report to a SharePoint library.</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="e0ac7-479">Para guardar el informe</span><span class="sxs-lookup"><span data-stu-id="e0ac7-479">To save the report</span></span>  
  
1.  <span data-ttu-id="e0ac7-480">Para cambiar a la vista de diseño, haga clic en **Diseño**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-480">To switch to design view, click **Design**.</span></span>  
  
2.  <span data-ttu-id="e0ac7-481">Desde el botón Generador de informes, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-481">From the Report Builder button, click **Save**.</span></span>  
  
3.  <span data-ttu-id="e0ac7-482">Si quiere mostrar una lista de servidores de informes y sitios de SharePoint usados recientemente, puede hacer clic en **Sitios y servidores recientes**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-482">Optionally, to show a list of recently used report servers and SharePoint sites, click **Recent Sites and Servers**.</span></span>  
  
4.  <span data-ttu-id="e0ac7-483">Seleccione o escriba el nombre del sitio de SharePoint donde tiene el permiso para guardar los informes.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-483">Select or type the name of the SharePoint site where you have permission to save reports.</span></span> <span data-ttu-id="e0ac7-484">La URL de la biblioteca de SharePoint tiene la siguiente sintaxis:</span><span class="sxs-lookup"><span data-stu-id="e0ac7-484">The URL of the SharePoint library has the following syntax:</span></span>  
  
    ```  
    Http://<ServerName>/<Sites>/  
    ```  
  
5.  <span data-ttu-id="e0ac7-485">Navegue hasta la biblioteca donde quieren guardar el informe.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-485">Navigate to the library where you want to save the report.</span></span>  
  
6.  <span data-ttu-id="e0ac7-486">En **Nombre**, reemplace el nombre predeterminado por **ResellerVSOnlineMain**.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-486">In **Name**, replace the default name with **ResellerVSOnlineMain**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e0ac7-487">Guarde el informe principal en la misma ubicación donde guardó el informe detallado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-487">Save the main report to the same location where you saved the drillthrough report.</span></span> <span data-ttu-id="e0ac7-488">Para guardar los informes detallados y principal en sitios o bibliotecas diferentes, confirme que la acción **Ir a informe** del informe principal señala a la ubicación correcta del informe detallado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-488">To save the main and drillthrough reports to different sites or libraries, confirm that the **Go to report** action in the main report, points to the correct location of the drillthrough report.</span></span>  
  
7.  <span data-ttu-id="e0ac7-489">Haga clic en **Save**(Guardar).</span><span class="sxs-lookup"><span data-stu-id="e0ac7-489">Click **Save**.</span></span>  
  
##  <a name="8-run-the-main-and-drillthrough-reports"></a><a name="MRunReports"></a><span data-ttu-id="e0ac7-490">8. ejecutar los informes principal y de obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="e0ac7-490">8. Run the Main and Drillthrough Reports</span></span>  
 <span data-ttu-id="e0ac7-491">Ejecute el informe principal y, a continuación, haga clic en los valores de la columna de categoría de producto para ejecutar el informe detallado.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-491">Run the main report, and then click values in the product category column to run the drillthrough report.</span></span>  
  
#### <a name="to-run-the-reports"></a><span data-ttu-id="e0ac7-492">Para ejecutar los informes</span><span class="sxs-lookup"><span data-stu-id="e0ac7-492">To run the reports</span></span>  
  
1.  <span data-ttu-id="e0ac7-493">Abra la biblioteca de SharePoint donde los informes están guardados.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-493">Open the SharePoint library where the reports are saved.</span></span>  
  
2.  <span data-ttu-id="e0ac7-494">Haga doble clic en ResellerVSOnlineMain.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-494">Double-click ResellerVSOnlineMain.</span></span>  
  
     <span data-ttu-id="e0ac7-495">El informe se ejecuta y muestra la información de ventas de la categoría de producto.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-495">The report runs and displays product category sales information.</span></span>  
  
3.  <span data-ttu-id="e0ac7-496">Haga clic en el vínculo **Games and Toys** de la columna que contiene los nombres de categoría de producto.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-496">Click the **Games and Toys** link in the column that contains product category names.</span></span>  
  
     <span data-ttu-id="e0ac7-497">Se ejecuta el informe detallados, mostrando solo los valores para la categoría de producto Games and Toys.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-497">The drillthrough report runs, displaying only the values for the Games and Toys product category.</span></span>  
  
4.  <span data-ttu-id="e0ac7-498">Para volver al informe principal, haga clic en el botón atrás de Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-498">To return to the main report, click the Internet Explorer back button.</span></span>  
  
5.  <span data-ttu-id="e0ac7-499">Opcionalmente, explore otras categorías de producto haciendo clic en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="e0ac7-499">Optionally, explore other product categories by clicking their names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ac7-500">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e0ac7-500">See Also</span></span>  
 [<span data-ttu-id="e0ac7-501">Tutoriales &#40;Generador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="e0ac7-501">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
