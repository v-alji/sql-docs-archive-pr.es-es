---
title: Destino de Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldest.f1
helpviewer_keywords:
- destinations [Integration Services], Excel
- Excel [Integration Services]
ms.assetid: 37c07446-1264-4814-b4f5-9c66d333bb24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e959f14e52fc045cb0cbc2ba0255d20bd0356d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751342"
---
# <a name="excel-destination"></a><span data-ttu-id="a9d0e-102">Destino de Excel</span><span class="sxs-lookup"><span data-stu-id="a9d0e-102">Excel Destination</span></span>
  <span data-ttu-id="a9d0e-103">El destino de Excel carga datos en hojas de cálculo o rangos en libros de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-103">The Excel destination loads data into worksheets or ranges in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbooks.</span></span>  
  
## <a name="access-modes"></a><span data-ttu-id="a9d0e-104">Modos de acceso</span><span class="sxs-lookup"><span data-stu-id="a9d0e-104">Access Modes</span></span>  
 <span data-ttu-id="a9d0e-105">El destino de Excel proporciona tres modos diferentes de acceso a los datos para cargar datos:</span><span class="sxs-lookup"><span data-stu-id="a9d0e-105">The Excel destination provides three different data access modes for loading data:</span></span>  
  
-   <span data-ttu-id="a9d0e-106">Una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-106">A table or view.</span></span>  
  
-   <span data-ttu-id="a9d0e-107">Una tabla o vista especificadas en una variable.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-107">A table or view specified in a variable.</span></span>  
  
-   <span data-ttu-id="a9d0e-108">Los resultados de una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-108">The results of an SQL statement.</span></span> <span data-ttu-id="a9d0e-109">La consulta puede tener parámetros.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-109">The query can be a parameterized query.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a9d0e-110">En Excel, una hoja o un rango equivalen a una tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-110">In Excel, a worksheet or range is the equivalent of a table or view.</span></span> <span data-ttu-id="a9d0e-111">Las listas de tablas disponibles en los editores de Origen y Destino de Excel muestran solo las hojas de cálculo existentes (identificadas con el signo $ anexado al nombre de la hoja de cálculo, como, por ejemplo, Hoja1$) y rangos con nombre (identificados por la falta del signo $, como por ejemplo, MiRango).</span><span class="sxs-lookup"><span data-stu-id="a9d0e-111">The lists of available tables in the Excel Source and Destination editors display only existing worksheets (identified by the $ sign appended to the worksheet name, such as Sheet1$) and named ranges (identified by the absence of the $ sign, such as MyRange).</span></span>  
  
## <a name="usage-considerations"></a><span data-ttu-id="a9d0e-112">Consideraciones de uso</span><span class="sxs-lookup"><span data-stu-id="a9d0e-112">Usage Considerations</span></span>  
 <span data-ttu-id="a9d0e-113">El Administrador de conexiones con Excel usa el Proveedor OLE DB de [!INCLUDE[msCoName](../../includes/msconame-md.md)] para Jet 4.0 y el controlador ISAM (Método de acceso secuencial indexado) de Excel asociado para conectar con orígenes Excel de datos y leer y escribir datos en ellos.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-113">The Excel Connection Manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span>  
  
 <span data-ttu-id="a9d0e-114">Muchos artículos de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base documentan el comportamiento de este proveedor y el controlador. Aunque estos artículos no son específicos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ni de Servicios de transformación de datos (su predecesor), posiblemente le interese conocer determinados comportamientos que pueden provocar resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-114">Many existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles document the behavior of this provider and driver, and although these articles are not specific to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] or its predecessor Data Transformation Services, you may want to know about certain behaviors that can lead to unexpected results.</span></span> <span data-ttu-id="a9d0e-115">Para obtener información general sobre el uso y el comportamiento del controlador de Excel, vea [Cómo usar ADO con datos de Excel procedentes de Visual Basic o VBA](https://support.microsoft.com/kb/257819).</span><span class="sxs-lookup"><span data-stu-id="a9d0e-115">For general information on the use and behavior of the Excel driver, see [HOWTO: Use ADO with Excel Data from Visual Basic or VBA](https://support.microsoft.com/kb/257819).</span></span>  
  
 <span data-ttu-id="a9d0e-116">Los siguientes comportamientos del proveedor Jet que se incluye con el controlador de Excel pueden provocar resultados inesperados al guardar datos en un destino de Excel.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-116">The following behaviors of the Jet provider that is included with the Excel driver can lead to unexpected results when saving data to an Excel destination.</span></span>  
  
-   <span data-ttu-id="a9d0e-117">**Guardar datos de texto**.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-117">**Saving text data**.</span></span> <span data-ttu-id="a9d0e-118">Cuando el controlador de Excel guarda valores de datos de texto en un destino de Excel, el controlador precede el texto en cada celda con el carácter de comilla simple (') para garantizar que los valores guardados se interpreten como valores de texto.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-118">When the Excel driver saves text data values to an Excel destination, the driver precedes the text in each cell with the single quote character (') to ensure that the saved values will be interpreted as text values.</span></span> <span data-ttu-id="a9d0e-119">Si posee o desarrolla otras aplicaciones que leen o procesan los datos guardados, es posible que necesite un tratamiento especial para el carácter de comilla simple que precede cada valor de texto.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-119">If you have or develop other applications that read or process the saved data, you may need to include special handling for the single quote character that precedes each text value.</span></span>  
  
     <span data-ttu-id="a9d0e-120">Si desea información sobre cómo evitar incluir las comillas simples, consulte esta entrada de blog, [Se añade una comilla simple a todas las cadenas al transformar los datos a Excel cuando se utiliza el componente de flujo de datos de destino Excel en un paquete SSIS](https://go.microsoft.com/fwlink/?LinkId=400876), en msdn.com.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-120">For information on how to avoid including the single quote, see this blog post, [Single quote is appended to all strings when data is transformed to excel when using Excel destination data flow component in SSIS package](https://go.microsoft.com/fwlink/?LinkId=400876), on msdn.com.</span></span>  
  
-   <span data-ttu-id="a9d0e-121">**Guardar datos de memorando (ntext)**.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-121">**Saving memo (ntext) da**ta.</span></span> <span data-ttu-id="a9d0e-122">Para poder guardar correctamente cadenas de más de 255 caracteres en una columna de Excel, el controlador debe reconocer el tipo de datos de la columna de destino como **memorando** y no como **cadena**.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-122">Before you can successfully save strings longer than 255 characters to an Excel column, the driver must recognize the data type of the destination column as **memo** and not **string**.</span></span> <span data-ttu-id="a9d0e-123">Si la tabla de destino ya contiene filas de datos, las primeras filas que pruebe el controlador deberán contener por lo menos una instancia de un valor de más de 255 caracteres en la columna de memorando.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-123">If the destination table already contains rows of data, then the first few rows that are sampled by the driver must contain at least one instance of a value longer than 255 characters in the memo column.</span></span> <span data-ttu-id="a9d0e-124">Si la tabla de destino se crea durante el diseño del paquete o en tiempo de ejecución, la instrucción CREATE TABLE debe utilizar LONGTEXT (o uno de sus sinónimos) como tipo de datos de la columna de memorando.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-124">If the destination table is created during package design or at run time, then the CREATE TABLE statement must use LONGTEXT (or one of its synonyms) as the data type of the memo column.</span></span>  
  
-   <span data-ttu-id="a9d0e-125">**Tipos de datos**.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-125">**Data types**.</span></span> <span data-ttu-id="a9d0e-126">El controlador de Excel reconoce solo un conjunto limitado de tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-126">The Excel driver recognizes only a limited set of data types.</span></span> <span data-ttu-id="a9d0e-127">Por ejemplo, todas las columnas numéricas se interpretan como dobles (DT_R8) y todas las columnas de cadena (a excepción de las columnas memorando) se interpretan como cadenas Unicode de 255 caracteres (DT_WSTR).</span><span class="sxs-lookup"><span data-stu-id="a9d0e-127">For example, all numeric columns are interpreted as doubles (DT_R8), and all string columns (other than memo columns) are interpreted as 255-character Unicode strings (DT_WSTR).</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="a9d0e-128">asigna los tipos de datos de Excel de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a9d0e-128">maps the Excel data types as follows:</span></span>  
  
    -   <span data-ttu-id="a9d0e-129">Numérico    flotante de doble precisión (DT_R8)</span><span class="sxs-lookup"><span data-stu-id="a9d0e-129">Numeric    double-precision float (DT_R8)</span></span>  
  
    -   <span data-ttu-id="a9d0e-130">Moneda     moneda (DT_CY)</span><span class="sxs-lookup"><span data-stu-id="a9d0e-130">Currency     currency (DT_CY)</span></span>  
  
    -   <span data-ttu-id="a9d0e-131">Booleano     booleano (DT_BOOL)</span><span class="sxs-lookup"><span data-stu-id="a9d0e-131">Boolean     Boolean (DT_BOOL)</span></span>  
  
    -   <span data-ttu-id="a9d0e-132">Fecha y hora `datetime` (DT_DATE)</span><span class="sxs-lookup"><span data-stu-id="a9d0e-132">Date/time     `datetime` (DT_DATE)</span></span>  
  
    -   <span data-ttu-id="a9d0e-133">Cadena    cadena Unicode, longitud de 255 caracteres (DT_WSTR)</span><span class="sxs-lookup"><span data-stu-id="a9d0e-133">String     Unicode string, length 255 (DT_WSTR)</span></span>  
  
    -   <span data-ttu-id="a9d0e-134">Memorando     flujo de texto Unicode (DT_NTEXT)</span><span class="sxs-lookup"><span data-stu-id="a9d0e-134">Memo     Unicode text stream (DT_NTEXT)</span></span>  
  
-   <span data-ttu-id="a9d0e-135">**Tipos de datos y conversiones de longitud**.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-135">**Data type and length conversions**.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="a9d0e-136">no convierte tipos de datos de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-136">does not implicitly convert data types.</span></span> <span data-ttu-id="a9d0e-137">Como resultado, probablemente necesite usar las transformaciones Columna derivada o Conversión de datos para convertir datos de Excel de forma explícita antes de cargarlos en un destino diferente de Excel, o para convertir datos que no son de Excel antes de cargarlos en un destino de Excel.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-137">As a result, you may need to use the Derived Column or Data Conversion transformations to convert Excel data explicitly before loading it into a non-Excel destination, or to convert non-Excel data before loading it into an Excel destination.</span></span> <span data-ttu-id="a9d0e-138">En este caso, puede resultar útil crear el paquete inicial a través del Asistente para importación y exportación, que le configura las conversiones necesarias.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-138">In this case, it may be useful to create the initial package by using the Import and Export Wizard, which configures the necessary conversions for you.</span></span> <span data-ttu-id="a9d0e-139">Entre algunos ejemplos de las conversiones que se pueden requerir, figuran:</span><span class="sxs-lookup"><span data-stu-id="a9d0e-139">Some examples of the conversions that may be required include the following:</span></span>  
  
    -   <span data-ttu-id="a9d0e-140">Conversión entre columnas de cadena de Excel Unicode y columnas de cadena no Unicode con páginas de códigos específicas.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-140">Conversion between Unicode Excel string columns and non-Unicode string columns with specific codepages.</span></span>  
  
    -   <span data-ttu-id="a9d0e-141">Conversión entre columnas de cadena de Excel de 255 caracteres y columnas de cadena de diferentes longitudes.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-141">Conversion between 255-character Excel string columns and string columns of different lengths.</span></span>  
  
    -   <span data-ttu-id="a9d0e-142">Conversión entre columnas numéricas de Excel de doble precisión y columnas numéricas de otros tipos.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-142">Conversion between double-precision Excel numeric columns and numeric columns of other types.</span></span>  
  
## <a name="configuration-of-the-excel-destination"></a><span data-ttu-id="a9d0e-143">Configuración del destino de Excel</span><span class="sxs-lookup"><span data-stu-id="a9d0e-143">Configuration of the Excel Destination</span></span>  
 <span data-ttu-id="a9d0e-144">El destino de Excel usa un administrador de conexiones de Excel para conectarse a un origen de datos, y el administrador de conexiones especifica el archivo de libro que se debe usar.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-144">The Excel destination uses an Excel connection manager to connect to a data source, and the connection manager specifies the workbook file to use.</span></span> <span data-ttu-id="a9d0e-145">Para más información, consulte [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a9d0e-145">For more information, see [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span></span>  
  
 <span data-ttu-id="a9d0e-146">El destino de Excel tiene una entrada normal y una salida de error.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-146">The Excel destination has one regular input and one error output.</span></span>  
  
 <span data-ttu-id="a9d0e-147">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-147">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a9d0e-148">Para obtener más información sobre las propiedades que se pueden configurar en el cuadro de diálogo **Editor de destino de Excel** , haga clic en uno de los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="a9d0e-148">For more information about the properties that you can set in the **Excel Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a9d0e-149">Editor de destino de Excel &#40;página Administrador de conexiones&#41;</span><span class="sxs-lookup"><span data-stu-id="a9d0e-149">Excel Destination Editor &#40;Connection Manager Page&#41;</span></span>](../excel-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="a9d0e-150">Editor de destino de Excel &#40;página Asignaciones&#41;</span><span class="sxs-lookup"><span data-stu-id="a9d0e-150">Excel Destination Editor &#40;Mappings Page&#41;</span></span>](../excel-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="a9d0e-151">Editor de destino de Excel &#40;página Salida de error&#41;</span><span class="sxs-lookup"><span data-stu-id="a9d0e-151">Excel Destination Editor &#40;Error Output Page&#41;</span></span>](../excel-destination-editor-error-output-page.md)  
  
 <span data-ttu-id="a9d0e-152">El cuadro de diálogo **Editor avanzado** indica todas las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a9d0e-152">The **Advanced Editor** dialog box reflects all the properties that can be set programmatically.</span></span> <span data-ttu-id="a9d0e-153">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9d0e-153">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a9d0e-154">Common Properties</span><span class="sxs-lookup"><span data-stu-id="a9d0e-154">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="a9d0e-155">Propiedades personalizadas de Excel</span><span class="sxs-lookup"><span data-stu-id="a9d0e-155">Excel Custom Properties</span></span>](excel-custom-properties.md)  
  
 <span data-ttu-id="a9d0e-156">Para más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a9d0e-156">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a9d0e-157">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a9d0e-157">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a9d0e-158">Importación de datos desde Excel o exportación de datos a Excel con SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="a9d0e-158">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)  
  
-   [<span data-ttu-id="a9d0e-159">Crear bucles entre archivos y tablas de Excel mediante un contenedor de bucles ForEach</span><span class="sxs-lookup"><span data-stu-id="a9d0e-159">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="a9d0e-160">Establecer las propiedades de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="a9d0e-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9d0e-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9d0e-161">See Also</span></span>  
 <span data-ttu-id="a9d0e-162">[Origen de Excel](excel-source.md) </span><span class="sxs-lookup"><span data-stu-id="a9d0e-162">[Excel Source](excel-source.md) </span></span>  
 <span data-ttu-id="a9d0e-163">[Variables de Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a9d0e-163">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="a9d0e-164">[Flujo de datos](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="a9d0e-164">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="a9d0e-165">Trabajar con archivos de Excel con la tarea Script</span><span class="sxs-lookup"><span data-stu-id="a9d0e-165">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
  
  
