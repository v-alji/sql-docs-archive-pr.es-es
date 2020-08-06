---
title: Origen ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.f1
ms.assetid: abcf34eb-9140-4100-82e6-b85bccd22abe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 792557839d60f34bdf944dab150959d4df7cb8cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670476"
---
# <a name="odbc-source"></a><span data-ttu-id="5d9b1-102">Origen ODBC</span><span class="sxs-lookup"><span data-stu-id="5d9b1-102">ODBC Source</span></span>
  <span data-ttu-id="5d9b1-103">El origen ODBC extrae los datos de una base de datos con ODBC mediante una tabla de base de datos, una vista o una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-103">The ODBC source extracts data from ODBC-supported database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="5d9b1-104">El origen ODBC tiene los modos de acceso a datos siguientes para extraer datos:</span><span class="sxs-lookup"><span data-stu-id="5d9b1-104">The ODBC source has the following data access modes for extracting data:</span></span>  
  
-   <span data-ttu-id="5d9b1-105">Una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-105">A table or view.</span></span>  
  
-   <span data-ttu-id="5d9b1-106">Los resultados de una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-106">The results of an SQL statement.</span></span>  
  
 <span data-ttu-id="5d9b1-107">El origen utiliza un administrador de conexiones ODBC, que especifica el proveedor que usar.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-107">The source uses an ODBC connection manager, which specifies the provider to use.</span></span>  
  
 <span data-ttu-id="5d9b1-108">Un origen ODBC incluye las columnas de salida de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-108">An ODBC source includes the source data output columns.</span></span> <span data-ttu-id="5d9b1-109">Cuando las columnas de salida se asignan en el destino ODBC a las columnas de destino, pueden aparecer errores si no se ha asignado ninguna columna de salida a las columnas de destino.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-109">When output columns are mapped in the ODBC destination to the destination columns, errors may occur if no output columns are mapped to the destination columns.</span></span> <span data-ttu-id="5d9b1-110">Se pueden asignar columnas de tipos diferentes, sin embargo, si los datos de salida no son compatibles con el destino, se produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-110">Columns of different types can be mapped, however if the output data is not compatible for the destination then an error occurs at runtime.</span></span> <span data-ttu-id="5d9b1-111">En función de la opción de comportamiento del error, se omitirá el error, se producirá un error o la fila se enviará a la salida de error.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-111">Depending on the error behavior, setting the error will be ignored, cause a failure, or the row is sent to the error output.</span></span>  
  
 <span data-ttu-id="5d9b1-112">El origen ODBC tiene una salida normal y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-112">The ODBC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="5d9b1-113">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="5d9b1-113">Error Handling</span></span>  
 <span data-ttu-id="5d9b1-114">El origen ODBC tiene una salida de error.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-114">The ODBC source has an error output.</span></span> <span data-ttu-id="5d9b1-115">La salida de error del componente incluye las columnas de salida siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d9b1-115">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="5d9b1-116">**Código de error**: número que corresponde al error actual.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-116">**Error Code**: The number that corresponds to the current error.</span></span> <span data-ttu-id="5d9b1-117">Vea la documentación de la base de datos con ODBC que usa para obtener una lista de errores.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-117">See the documentation for the ODBC-supported database you are using for a list of errors.</span></span> <span data-ttu-id="5d9b1-118">Para obtener una lista de códigos de errores de SSIS, vea la referencia Código de errores y mensajes de SSIS.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-118">For a list of SSIS error codes, see the SSIS Error Code and Message Reference.</span></span>  
  
-   <span data-ttu-id="5d9b1-119">**Columna de error**: columna de origen que produce el error (para los errores de conversión).</span><span class="sxs-lookup"><span data-stu-id="5d9b1-119">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="5d9b1-120">Columnas estándar de datos de salida.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-120">The standard output data columns.</span></span>  
  
 <span data-ttu-id="5d9b1-121">Según la configuración del comportamiento de los errores, el origen ODBC permite devolver los errores (conversión de datos, truncamiento) que aparecerán durante el proceso de extracción en la salida de error.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-121">Depending on the error behavior setting, the ODBC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="5d9b1-122">Para obtener más información, vea [Editor de destino de ODBC &#40;página Administrador de conexiones&#41;](../odbc-destination-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="5d9b1-122">For more information, see [ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="5d9b1-123">Compatibilidad con tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5d9b1-123">Data Type Support</span></span>  
 <span data-ttu-id="5d9b1-124">Para obtener información acerca de los tipos de datos admitidos por el origen ODBC, vea Connector for Open Database Connectivity (ODBC) de Attunity.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-124">For information about the data types supported by the ODBC source, see Connector for Open Database Connectivity (ODBC) by Attunity.</span></span>  
  
## <a name="extract-options"></a><span data-ttu-id="5d9b1-125">Opciones de extracción</span><span class="sxs-lookup"><span data-stu-id="5d9b1-125">Extract Options</span></span>  
 <span data-ttu-id="5d9b1-126">El origen ODBC funciona en modo **Lote** o **Fila a fila** .</span><span class="sxs-lookup"><span data-stu-id="5d9b1-126">The ODBC source operates in either **Batch** or **Row-by-Row** mode.</span></span> <span data-ttu-id="5d9b1-127">La propiedad **FetchMethod** determina el modo usado.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-127">The mode used is determined by the **FetchMethod** property.</span></span> <span data-ttu-id="5d9b1-128">En la lista siguiente, se describen los modos.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-128">The following list describes the modes.</span></span>  
  
-   <span data-ttu-id="5d9b1-129">**Lote**: el componente intenta usar el método más eficaz de búsqueda en función de las capacidades del proveedor ODBC percibidas.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-129">**Batch**: The component attempts to use the most efficient fetch method based on the perceived ODBC provider capabilities.</span></span> <span data-ttu-id="5d9b1-130">Para la mayoría de los proveedores ODBC modernos, es SQLFetchScroll con enlace de matriz (donde el tamaño de la matriz se determina mediante la propiedad **BatchSize** ).</span><span class="sxs-lookup"><span data-stu-id="5d9b1-130">For most modern ODBC providers, this is SQLFetchScroll with array binding (where the array size is determined by the **BatchSize** property).</span></span> <span data-ttu-id="5d9b1-131">Si selecciona **Lote** y el proveedor no admite este método, el destino ODBC cambia automáticamente los modificadores al modo **Fila a fila** .</span><span class="sxs-lookup"><span data-stu-id="5d9b1-131">If you select **Batch** and the provider does not support this method, the ODBC destination automatically switches to the **Row-by-row** mode.</span></span>  
  
-   <span data-ttu-id="5d9b1-132">**Fila a fila**: el componente usa SQLFetch para recuperar las filas de una en una.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-132">**Row-by Row**: The component uses SQLFetch to retrieve the rows one at a time.</span></span>  
  
 <span data-ttu-id="5d9b1-133">Para obtener más información acerca de la la propiedad **FetchMethod** , vea [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5d9b1-133">For more information about the **FetchMethod** property, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="parallelism"></a><span data-ttu-id="5d9b1-134">Paralelismo</span><span class="sxs-lookup"><span data-stu-id="5d9b1-134">Parallelism</span></span>  
 <span data-ttu-id="5d9b1-135">No hay límite en el número de componentes de origen ODBC que se pueden ejecutar en paralelo en la misma tabla o en tablas diferentes, en el mismo equipo o en equipos diferentes (que no sean los límites normales de la sesión global).</span><span class="sxs-lookup"><span data-stu-id="5d9b1-135">There is no limitation on the number of ODBC source components that can run in parallel against the same table or different tables, on the same machine or on different machines (other than normal global session limits).</span></span>  
  
 <span data-ttu-id="5d9b1-136">Sin embargo, las limitaciones del proveedor ODBC que se usa pueden restringir el número de conexiones simultáneas a través del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-136">However, limitations of the ODBC provider being used may restrict the number of concurrent connections through the provider.</span></span> <span data-ttu-id="5d9b1-137">Estas limitaciones limitan el número de instancias en paralelo admitidas posibles para el origen ODBC.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-137">These limitations limit the number of supported parallel instances possible for the ODBC source.</span></span> <span data-ttu-id="5d9b1-138">El desarrollador de SSIS debe tener en cuenta las limitaciones de cualquier proveedor ODBC que se vaya a usar y tomarlas en cuenta al generar paquetes SSIS.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-138">The SSIS developer must be aware of the limitations of any ODBC provider being used and take them into consideration when building SSIS packages.</span></span>  
  
## <a name="troubleshooting-the-odbc-source"></a><span data-ttu-id="5d9b1-139">Solucionar problemas del origen de ODBC</span><span class="sxs-lookup"><span data-stu-id="5d9b1-139">Troubleshooting the ODBC Source</span></span>  
 <span data-ttu-id="5d9b1-140">Puede registrar las llamadas que el origen ODBC realiza a proveedores de datos externos.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-140">You can log the calls that the ODBC source makes to external data providers.</span></span> <span data-ttu-id="5d9b1-141">Puede usar esta capacidad de registro para solucionar los problemas relacionados con la carga de datos de orígenes de datos externos que realiza el origen ODBC.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-141">You can use this logging capability to troubleshoot the loading of data from external data sources that the ODBC source performs.</span></span> <span data-ttu-id="5d9b1-142">Para registrar las llamadas realizadas por el origen ODBC a proveedores de datos externos, habilite el seguimiento del administrador de controladores ODBC.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-142">To log the calls that the ODBC source makes to external data providers, enable the ODBC driver manager trace.</span></span> <span data-ttu-id="5d9b1-143">Para obtener más información, vea la documentación de Microsoft sobre *cómo generar un seguimiento ODBC con el administrador de orígenes de datos.*</span><span class="sxs-lookup"><span data-stu-id="5d9b1-143">For more information, see the Microsoft documentation on *How To Generate an ODBC Trace with ODBC the Data Source Administrator.*</span></span>  
  
## <a name="configuring-the-odbc-source"></a><span data-ttu-id="5d9b1-144">Configurar el origen ODBC</span><span class="sxs-lookup"><span data-stu-id="5d9b1-144">Configuring the ODBC Source</span></span>  
 <span data-ttu-id="5d9b1-145">Puede configurar el origen ODBC mediante programación o través del Diseñador SSIS.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-145">You can configure the ODBC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="5d9b1-146">Para obtener más información, vea uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5d9b1-146">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="5d9b1-147">Editor de orígenes ODBC &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="5d9b1-147">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="5d9b1-148">Editor de orígenes ODBC &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="5d9b1-148">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="5d9b1-149">Editor de orígenes ODBC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="5d9b1-149">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="5d9b1-150">El cuadro de diálogo **Editor avanzado** contiene las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-150">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="5d9b1-151">Para abrir el cuadro de diálogo **Editor avanzado** :</span><span class="sxs-lookup"><span data-stu-id="5d9b1-151">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="5d9b1-152">En la pantalla **Flujo de datos** del proyecto de [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , haga clic con el botón secundario en el origen ODBC y seleccione **Mostrar editor avanzado**.</span><span class="sxs-lookup"><span data-stu-id="5d9b1-152">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the ODBC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="5d9b1-153">Para obtener más información acerca de las propiedades que se pueden establecer en el cuadro de diálogo Editor avanzado, vea [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5d9b1-153">For more information about the properties that you can set in the Advanced Editor dialog box, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5d9b1-154">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5d9b1-154">In This Section</span></span>  
  
-   [<span data-ttu-id="5d9b1-155">Editor de orígenes ODBC &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="5d9b1-155">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="5d9b1-156">Editor de orígenes ODBC &#40;página Columnas&#41;</span><span class="sxs-lookup"><span data-stu-id="5d9b1-156">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="5d9b1-157">Editor de orígenes ODBC &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="5d9b1-157">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="5d9b1-158">Extraer datos mediante el origen de ODBC</span><span class="sxs-lookup"><span data-stu-id="5d9b1-158">Extract Data by Using the ODBC Source</span></span>](odbc-source.md)  
  
-   [<span data-ttu-id="5d9b1-159">ODBC Source Custom Properties</span><span class="sxs-lookup"><span data-stu-id="5d9b1-159">ODBC Source Custom Properties</span></span>](odbc-source-custom-properties.md)  
  
  
