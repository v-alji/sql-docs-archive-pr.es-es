---
title: Recuperar datos de un modelo de minería de datos (DMX) (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- retrieving report data
- datasets [Reporting Services], with DMX queries
- datasets [Reporting Services], Analysis Services
- queries [Reporting Services], data mining prediction
ms.assetid: d9cd3624-1594-4707-8887-55437dd7e07c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a59184524967a9bfe772e41890afc3b900cc9e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748668"
---
# <a name="retrieve-data-from-a-data-mining-model-dmx-ssrs"></a><span data-ttu-id="fb3eb-102">Recuperar datos de un modelo de minería de datos (DMX) (SSRS)</span><span class="sxs-lookup"><span data-stu-id="fb3eb-102">Retrieve Data from a Data Mining Model (DMX) (SSRS)</span></span>
  <span data-ttu-id="fb3eb-103">Para usar los datos de un modelo de minería de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en el informe, debe definir un origen de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] y uno o más conjuntos de datos de informe.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-103">To use data from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data mining model in your report, you must define a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source and one or more report datasets.</span></span> <span data-ttu-id="fb3eb-104">Al crear la definición de origen de datos, debe especificar una cadena de conexión y unas credenciales para poder tener acceso al origen de datos desde el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-104">When you create the data source definition, you must specify a connection string and credentials so that you can access the data source from your client computer.</span></span>  
  
 <span data-ttu-id="fb3eb-105">Puede crear una definición de origen de datos incrustada para su uso en un solo informe o una definición de origen de datos compartida que se pueda usar en varios informes.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-105">You can create an embedded data source definition for use by a single report or a shared data source definition that can be used by multiple reports.</span></span> <span data-ttu-id="fb3eb-106">Los procedimientos de este tema explican cómo crear un origen de datos incrustado.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-106">The procedures in this topic describe how to create an embedded data source.</span></span> <span data-ttu-id="fb3eb-107">Para más información sobre los orígenes de datos compartidos, vea [Conexiones de datos u orígenes de datos compartidos e incrustados &#40;Generador de informes y SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) y [Crear, modificar y eliminar orígenes de datos compartidos &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fb3eb-107">For more information about shared data sources, see [Embedded and Shared Data Connections or Data Sources &#40;Report Builder and SSRS&#41;](../embedded-and-shared-data-connections-or-data-sources-report-builder-and-ssrs.md) and [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
 <span data-ttu-id="fb3eb-108">Después de crear un origen de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], puede crear uno o más conjuntos de datos.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-108">After you create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you can create one or more datasets.</span></span> <span data-ttu-id="fb3eb-109">Para cada conjunto de datos, use un diseñador de consultas de predicción de minería de datos (DMX) para crear una consulta DMX que especifique la colección de campos.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-109">For each dataset, you use a Data Mining Prediction Expression (DMX) query designer to create a DMX query that specifies the field collection.</span></span> <span data-ttu-id="fb3eb-110">Para más información, consulte [Interfaz de usuario del Diseñador de consultas DMX de Analysis Services](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fb3eb-110">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
 <span data-ttu-id="fb3eb-111">Después de crear un conjunto de datos, el nombre de éste aparece en el panel Datos de informe como un nodo bajo su origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-111">After you create a dataset, the name of the dataset appears in the Report Data pane as a node under its data source.</span></span>  
  
 <span data-ttu-id="fb3eb-112">Después de publicar el informe, es posible que necesite cambiar las credenciales para el origen de datos de tal forma que, cuando el informe se ejecute en el servidor de informes, los permisos para recuperar los datos sean válidos.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-112">After you publish your report, you may need to change the credentials for the data source so that when the report runs on the report server, the permissions to retrieve the data are valid.</span></span>  
  
### <a name="to-create-an-embedded-microsoft-sql-server-analysis-services-data-source"></a><span data-ttu-id="fb3eb-113">Para crear un origen de datos de Microsoft SQL Server Analysis Services incrustado</span><span class="sxs-lookup"><span data-stu-id="fb3eb-113">To create an embedded Microsoft SQL Server Analysis Services data source</span></span>  
  
1.  <span data-ttu-id="fb3eb-114">En la barra de herramientas del panel Datos de informe, haga clic en **Nuevo**y, a continuación, haga clic en **Origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-114">On the toolbar in the Report Data pane, click **New**, and then click **Data Source**.</span></span>  
  
2.  <span data-ttu-id="fb3eb-115">En el cuadro de diálogo **Propiedades del origen de datos** , escriba un nombre en el cuadro de texto **Nombre** o acepte el nombre predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-115">In the **Data Source Properties** dialog box, type a name in the **Name** text box, or accept the default name.</span></span>  
  
3.  <span data-ttu-id="fb3eb-116">Compruebe que la opción **Conexión incrustada** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-116">Verify that **Embedded connection** is selected.</span></span>  
  
4.  <span data-ttu-id="fb3eb-117">En la lista desplegable **Tipo** , seleccione **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-117">From the **Type** drop-down list, select **Microsoft SQL Server Analysis Services**.</span></span>  
  
5.  <span data-ttu-id="fb3eb-118">Especifique una cadena de conexión que funcione con el origen de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb3eb-118">Specify a connection string that works with your [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
     <span data-ttu-id="fb3eb-119">Póngase en contacto con el administrador de bases de datos y solicite la información de conexión y las credenciales que debe usar para conectar con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-119">Contact your database administrator for connection information and for the credentials to use to connect to the data source.</span></span> <span data-ttu-id="fb3eb-120">En el siguiente ejemplo de cadena de conexión, se especifica la base de datos de ejemplo [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] en el cliente local.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-120">The following connection string example specifies the sample [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)] database on the local client.</span></span>  
  
    ```  
    Data Source=localhost;Initial Catalog=AdventureWorksDW2012  
    ```  
  
6.  <span data-ttu-id="fb3eb-121">Haga clic en **Credenciales**.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-121">Click **Credentials**.</span></span>  
  
     <span data-ttu-id="fb3eb-122">Establezca las credenciales que se deben usar para conectar con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-122">Set the credentials to use to connect to the data source.</span></span> <span data-ttu-id="fb3eb-123">Para más información, consulte [Especificar información de credenciales y conexión para los orígenes de datos de informes](../../integration-services/connection-manager/data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="fb3eb-123">For more information, see [Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb3eb-124">Para probar la conexión del origen de datos, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-124">To test the data source connection, click **Edit**.</span></span> <span data-ttu-id="fb3eb-125">En el cuadro de diálogo **Propiedades de conexión** , haga clic en **Probar conexión**.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-125">In the **Connection Properties** dialog box, click **Test Connection**.</span></span> <span data-ttu-id="fb3eb-126">Si la prueba es correcta, aparecerá un mensaje de información que indica que se estableció correctamente la conexión de prueba.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-126">If the test is successful, you will see the information message "Test connection succeeded."</span></span> <span data-ttu-id="fb3eb-127">Si la prueba no es correcta, aparecerá un mensaje de advertencia con más información acerca de las razones por las que la prueba no se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-127">If the test fails, you will see a warning message with more information about why the test was not successful.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="fb3eb-128">El origen de datos aparece en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-128">The data source appears in the Report Data pane.</span></span>  
  
### <a name="to-create-a-dataset-for-a-microsoft-sql-server-analysis-services"></a><span data-ttu-id="fb3eb-129">Crear un conjunto de datos de Microsoft SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="fb3eb-129">To create a dataset for a Microsoft SQL Server Analysis Services</span></span>  
  
1.  <span data-ttu-id="fb3eb-130">En el panel **Datos de informe**, haga clic con el botón derecho en el nombre del origen de datos que se conecta a un origen de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] y, después, haga clic en **Agregar conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-130">In the **Report Data** pane, right-click the name of the data source that connects to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, and then click **Add Dataset**.</span></span>  
  
2.  <span data-ttu-id="fb3eb-131">En el cuadro de diálogo **Propiedades del conjunto de datos** , escriba un nombre en el cuadro de texto **Nombre** .</span><span class="sxs-lookup"><span data-stu-id="fb3eb-131">In the **Dataset Properties** dialog box, type a name in the **Name** text box.</span></span>  
  
3.  <span data-ttu-id="fb3eb-132">En el cuadro **Origen de datos**, compruebe que el nombre es el nombre de un origen de datos que se conecta con un origen de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb3eb-132">In the **Data source box**, verify that the name is the name of a data source that connects to an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source.</span></span>  
  
4.  <span data-ttu-id="fb3eb-133">Haga clic en **Diseñador de consultas** para abrir el diseñador gráfico de consultas y generar interactivamente una consulta.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-133">Click **Query Designer** to open the graphical query designer to build a query interactively.</span></span> <span data-ttu-id="fb3eb-134">Si el diseñador de consultas se abre en modo MDX, haga clic en **Tipo de comando DMX** (![Cambiar a la vista del lenguaje de consultas DMX](../media/rsqdicon-commandtypedmx.gif "Cambio a la vista del lenguaje de consultas DMX")) en la barra de herramientas para cambiar al diseñador de consultas de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-134">If the query designer opens in MDX mode, click **Command Type DMX** (![Change to DMX query language view](../media/rsqdicon-commandtypedmx.gif "Change to DMX query language view")) on the toolbar to switch to the data mining query designer.</span></span> <span data-ttu-id="fb3eb-135">Para más información, consulte [Interfaz de usuario del Diseñador de consultas DMX de Analysis Services](analysis-services-dmx-query-designer-user-interface.md).</span><span class="sxs-lookup"><span data-stu-id="fb3eb-135">For more information, see [Analysis Services DMX Query Designer User Interface](analysis-services-dmx-query-designer-user-interface.md).</span></span>  
  
     <span data-ttu-id="fb3eb-136">O bien, para importar una consulta DMX existente desde otro informe, haga clic en **Importar**y, a continuación, navegue hasta el archivo .rdl que contiene la consulta DMX.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-136">Alternatively, to import an existing DMX query from another report, click **Import**, and then navigate to the .rdl file with the DMX query.</span></span> <span data-ttu-id="fb3eb-137">No se admite la importación de una consulta desde un archivo .dmx.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-137">Importing a query from an .dmx file is not supported.</span></span>  
  
5.  <span data-ttu-id="fb3eb-138">Después de crear y ejecutar la consulta para ver los resultados del ejemplo, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-138">After you create and run your query to see sample results, click **OK**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     <span data-ttu-id="fb3eb-139">El conjunto de datos y su colección de campos aparecen en el panel Datos de informe bajo el nodo del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fb3eb-139">The dataset and its field collection appear in the Report Data pane under the data source node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3eb-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fb3eb-140">See Also</span></span>  
 <span data-ttu-id="fb3eb-141">[Tipo de conexión de Analysis Services para DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fb3eb-141">[Analysis Services Connection Type for DMX &#40;SSRS&#41;](analysis-services-connection-type-for-dmx-ssrs.md) </span></span>  
 <span data-ttu-id="fb3eb-142">[Conexiones de datos, orígenes de datos y cadenas de conexión en Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="fb3eb-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="fb3eb-143">[Colección Campos del conjunto de datos &#40;Generador de informes y SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fb3eb-143">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fb3eb-144">Conjuntos de datos incrustados y compartidos de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fb3eb-144">Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;</span></span>](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md)  
  
  
