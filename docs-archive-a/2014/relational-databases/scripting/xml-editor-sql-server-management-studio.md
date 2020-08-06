---
title: Editor XML
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.editorxml.f1
- sql12.swb.xmleditor.f1
- vs.xmleditor
- sql12.swb.editor.xml.f1
helpviewer_keywords:
- XML Designer [SQL Server Management Studio]
ms.assetid: 0824a5ce-e67b-4b53-98d9-d371faf2d23c
author: rothja
ms.author: jroth
ms.openlocfilehash: b7c3bbbda4f5a31c4d83b559c1aa623ca2aff89f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676445"
---
# <a name="xml-editor-sql-server-management-studio"></a><span data-ttu-id="eda91-102">Editores XML (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="eda91-102">XML Editor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="eda91-103">Proporciona un conjunto de herramientas visuales para trabajar con esquemas XML, conjuntos de datos ADO.NET y documentos XML.</span><span class="sxs-lookup"><span data-stu-id="eda91-103">Provides a set of visual tools for working with XML Schemas, ADO.NET datasets, and XML documents.</span></span> <span data-ttu-id="eda91-104">El Diseñador XML admite el lenguaje de definición de esquemas XML (XSD) definido por el World Wide Web Consortium (WC3).</span><span class="sxs-lookup"><span data-stu-id="eda91-104">The XML Designer supports the XML Schema Definition (XSD) language defined by the World Wide Web Consortium (WC3).</span></span> <span data-ttu-id="eda91-105">El diseñador no admite definiciones de tipo de documento (DTD) ni otros lenguajes de esquemas XML, como el esquema XML simplificado (XDR).</span><span class="sxs-lookup"><span data-stu-id="eda91-105">The designer does not support DTDs (document type definitions) or other XML schema languages, such as XDR (XML-Data Reduced).</span></span>  
  
 <span data-ttu-id="eda91-106">Para mostrar el diseñador, agregue un conjunto de datos, un esquema XML o un archivo XML al proyecto o abra cualquiera de los tipos de archivos que se enumeran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="eda91-106">To display the designer, add a dataset, XML Schema, or XML file to your project or open any of the file types listed in the table below.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="eda91-107">No hay ningún comando **Deshacer** cuando se trabaja en la vista Esquema.</span><span class="sxs-lookup"><span data-stu-id="eda91-107">There is no **Undo** command when working in Schema view.</span></span> <span data-ttu-id="eda91-108">Planifique su trabajo meticulosamente y guarde los archivos con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="eda91-108">Plan your work carefully and save your files often.</span></span>  
  
 <span data-ttu-id="eda91-109">El diseñador proporciona las tres siguientes vistas (o modos) para trabajar en archivos XML, esquemas XML y conjuntos de datos:</span><span class="sxs-lookup"><span data-stu-id="eda91-109">The designer provides the following three views (or modes) to work on XML files, XML Schemas, and datasets:</span></span>  
  
|<span data-ttu-id="eda91-110">Ver</span><span class="sxs-lookup"><span data-stu-id="eda91-110">View</span></span>|<span data-ttu-id="eda91-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="eda91-111">Description</span></span>|<span data-ttu-id="eda91-112">Tipos de archivos compatibles</span><span class="sxs-lookup"><span data-stu-id="eda91-112">File types supported</span></span>|  
|----------|-----------------|--------------------------|  
|<span data-ttu-id="eda91-113">**Esquema**</span><span class="sxs-lookup"><span data-stu-id="eda91-113">**Schema**</span></span>|<span data-ttu-id="eda91-114">Para crear y modificar visualmente esquemas XML y conjuntos de datos ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="eda91-114">For visually creating and modifying XML Schemas and ADO.NET datasets.</span></span>|<span data-ttu-id="eda91-115">.xsd</span><span class="sxs-lookup"><span data-stu-id="eda91-115">.xsd</span></span>|  
|<span data-ttu-id="eda91-116">**Data**</span><span class="sxs-lookup"><span data-stu-id="eda91-116">**Data**</span></span>|<span data-ttu-id="eda91-117">Para modificar visualmente archivos de datos XML en una cuadrícula de datos estructurada.</span><span class="sxs-lookup"><span data-stu-id="eda91-117">For visually modifying XML data files in a structured data grid.</span></span>|<span data-ttu-id="eda91-118">.xml</span><span class="sxs-lookup"><span data-stu-id="eda91-118">.xml</span></span>|  
|<span data-ttu-id="eda91-119">**XML**</span><span class="sxs-lookup"><span data-stu-id="eda91-119">**XML**</span></span>|<span data-ttu-id="eda91-120">Para editar XML; el editor de origen proporciona codificación de colores e IntelliSense, e incluye las características Palabra completa y Lista de miembros.</span><span class="sxs-lookup"><span data-stu-id="eda91-120">For editing XML; the source editor provides color-coding and IntelliSense, including Complete Word and List Members.</span></span>|<span data-ttu-id="eda91-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span><span class="sxs-lookup"><span data-stu-id="eda91-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span></span>|  
|<span data-ttu-id="eda91-122">**ShowPlan**</span><span class="sxs-lookup"><span data-stu-id="eda91-122">**ShowPlan**</span></span>|<span data-ttu-id="eda91-123">Muestra los planes de consulta xml creados mediante la opción SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="eda91-123">Displays xml query plans created using the SET SHOWPLAN_XML ON option.</span></span>|<span data-ttu-id="eda91-124">.showplan</span><span class="sxs-lookup"><span data-stu-id="eda91-124">.showplan</span></span>|  
  
## <a name="schema-view"></a><span data-ttu-id="eda91-125">Vista Esquema</span><span class="sxs-lookup"><span data-stu-id="eda91-125">Schema View</span></span>  
 <span data-ttu-id="eda91-126">La vista Esquema proporciona una representación visual de los elementos, atributos, tipos, etc., que componen los esquemas XML y los conjuntos de datos ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="eda91-126">Schema view provides a visual representation of the elements, attributes, types, and so on, that make up XML Schemas and ADO.NET datasets.</span></span>  
  
 <span data-ttu-id="eda91-127">En la vista Esquema se pueden crear esquemas y conjuntos de datos colocando elementos en la superficie de diseño desde la pestaña Esquema XML del Cuadro de herramientas o desde el Explorador de servidores.</span><span class="sxs-lookup"><span data-stu-id="eda91-127">In Schema view you can construct schemas and datasets by dropping elements on the design surface from either the XML Schema tab of the Toolbox or from Server Explorer.</span></span> <span data-ttu-id="eda91-128">Además, se pueden agregar elementos al diseñador haciendo clic con el botón secundario en la superficie de diseño y seleccionando Agregar desde el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="eda91-128">Additionally, you can add elements to the designer by right-clicking the design surface and selecting Add from the shortcut menu.</span></span>  
  
 <span data-ttu-id="eda91-129">En la vista Esquema se pueden realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="eda91-129">In Schema view you can:</span></span>  
  
-   <span data-ttu-id="eda91-130">Crear o modificar esquemas XML y conjuntos de datos ADO.NET existentes</span><span class="sxs-lookup"><span data-stu-id="eda91-130">Construct and modify existing XML Schemas and ADO.NET datasets</span></span>  
  
-   <span data-ttu-id="eda91-131">Crear y editar relaciones entre tablas</span><span class="sxs-lookup"><span data-stu-id="eda91-131">Create and edit relationships between tables</span></span>  
  
-   <span data-ttu-id="eda91-132">Crear y editar claves</span><span class="sxs-lookup"><span data-stu-id="eda91-132">Create and edit keys</span></span>  
  
-   <span data-ttu-id="eda91-133">Generar conjuntos de datos ADO.NET a partir de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="eda91-133">Generate ADO.NET datasets from XML Schemas</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eda91-134">El diseño de los elementos de la vista Esquema se almacena en el archivo .xsx; para poder ver este archivo, es necesario hacer clic en **Mostrar todos los archivos** en la barra de herramientas del Explorador de soluciones y, a continuación, expandir el archivo .xsd.</span><span class="sxs-lookup"><span data-stu-id="eda91-134">The layout of elements in Schema view is stored in the .xsx file, which can be seen by clicking **Show All Files** in the Solution Explorer toolbar, and then expanding the .xsd file.</span></span> <span data-ttu-id="eda91-135">Si no se muestra ningún archivo .xsx, significa que el archivo .xsd no se ha abierto nunca en el Diseñador XML.</span><span class="sxs-lookup"><span data-stu-id="eda91-135">If there is no .xsx file present, it means the .xsd file has never been opened in the XML Designer.</span></span>  
  
### <a name="customizing-schema-view"></a><span data-ttu-id="eda91-136">Personalizar la vista Esquema</span><span class="sxs-lookup"><span data-stu-id="eda91-136">Customizing Schema View</span></span>  
 <span data-ttu-id="eda91-137">Las siguientes características modifican el aspecto visual de los elementos de la vista Esquema:</span><span class="sxs-lookup"><span data-stu-id="eda91-137">The following features modify the visual layout of elements in Schema view:</span></span>  
  
-   <span data-ttu-id="eda91-138">Acercar o alejar</span><span class="sxs-lookup"><span data-stu-id="eda91-138">Zooming</span></span>  
  
-   <span data-ttu-id="eda91-139">Expandir o contraer elementos anidados</span><span class="sxs-lookup"><span data-stu-id="eda91-139">Expanding or collapsing of nested elements</span></span>  
  
-   <span data-ttu-id="eda91-140">Organizar automáticamente el diseño de los elementos</span><span class="sxs-lookup"><span data-stu-id="eda91-140">Automatically arranging layout of elements</span></span>  
  
-   <span data-ttu-id="eda91-141">Restablecer el estado predeterminado de los elementos contraídos</span><span class="sxs-lookup"><span data-stu-id="eda91-141">Resetting default state of collapsed elements</span></span>  
  
##### <a name="to-expand-hidden-nested-elements"></a><span data-ttu-id="eda91-142">Para expandir elementos anidados ocultos</span><span class="sxs-lookup"><span data-stu-id="eda91-142">To expand hidden nested elements</span></span>  
  
-   <span data-ttu-id="eda91-143">Haga clic en el icono de signo más de la parte inferior del elemento.</span><span class="sxs-lookup"><span data-stu-id="eda91-143">Click the plus icon on the bottom of the element.</span></span>  
  
##### <a name="to-collapse-nested-elements"></a><span data-ttu-id="eda91-144">Para contraer elementos anidados</span><span class="sxs-lookup"><span data-stu-id="eda91-144">To collapse nested elements</span></span>  
  
-   <span data-ttu-id="eda91-145">Haga clic en el icono de signo menos del elemento inferior que desea que aparezca en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="eda91-145">Click the minus icon on the bottom-most element that you want to appear on the designer.</span></span>  
  
## <a name="data-view"></a><span data-ttu-id="eda91-146">Vista de datos</span><span class="sxs-lookup"><span data-stu-id="eda91-146">Data View</span></span>  
 <span data-ttu-id="eda91-147">La vista de datos proporciona una cuadrícula de datos que puede utilizarse para modificar archivos .xml.</span><span class="sxs-lookup"><span data-stu-id="eda91-147">Data view provides a data grid that can be used to modify .xml files.</span></span> <span data-ttu-id="eda91-148">En la vista de datos, solo se puede editar el contenido (pero no las etiquetas ni la estructura) de un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="eda91-148">Only the content (but not the tags and structure) in an XML file can be edited in Data view.</span></span>  
  
 <span data-ttu-id="eda91-149">En la vista de datos, hay dos áreas bien diferenciadas: **Tablas de datos** y **Datos**.</span><span class="sxs-lookup"><span data-stu-id="eda91-149">There are two separate areas in Data view: **Data Tables** and **Data**.</span></span> <span data-ttu-id="eda91-150">El área **Tablas de datos** es una lista de relaciones definidas en el archivo XML, colocadas en el orden de su anidamiento (de exterior a interior).</span><span class="sxs-lookup"><span data-stu-id="eda91-150">The **Data Tables** area is a list of relations defined in the XML file, in the order of its nesting (from the outermost to the innermost).</span></span> <span data-ttu-id="eda91-151">El área **Datos** es una cuadrícula de datos que muestra los datos en función de la selección realizada en el área Tablas de datos.</span><span class="sxs-lookup"><span data-stu-id="eda91-151">The **Data** area is a data grid that displays data based on the selection in the Data Tables area.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eda91-152">Los archivos XML recién creados no contienen ningún dato y, por lo tanto, no pueden mostrarse en la vista de datos.</span><span class="sxs-lookup"><span data-stu-id="eda91-152">Newly created XML files contain no data and therefore cannot be displayed in Data view.</span></span> <span data-ttu-id="eda91-153">Existen también algunas instancias de documentos XML donde no se puede invocar la vista de datos.</span><span class="sxs-lookup"><span data-stu-id="eda91-153">There are also some instances of XML documents where data view cannot be invoked at all.</span></span> <span data-ttu-id="eda91-154">Aunque se considere que el documento XML tiene un formato correcto, si no está formado por datos estructurados que están intentando cambiar a la vista de datos, se generará el siguiente mensaje: "Aunque este documento XML está bien formado, contiene una estructura que la Vista de datos no puede mostrar".</span><span class="sxs-lookup"><span data-stu-id="eda91-154">Although the XML would be considered well formed, if it is not structured data trying to switch to Data view will generate the following message: "Although this document is well formed, it contains structure that Data View cannot display."</span></span>  
  
 <span data-ttu-id="eda91-155">En la vista de datos se pueden realizar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="eda91-155">In Data view you can:</span></span>  
  
-   <span data-ttu-id="eda91-156">Rellenar tablas de datos manualmente</span><span class="sxs-lookup"><span data-stu-id="eda91-156">Manually populate data tables</span></span>  
  
-   <span data-ttu-id="eda91-157">Editar tablas de datos existentes</span><span class="sxs-lookup"><span data-stu-id="eda91-157">Edit existing data tables</span></span>  
  
-   <span data-ttu-id="eda91-158">Generar un esquema XML a partir de un documento XML</span><span class="sxs-lookup"><span data-stu-id="eda91-158">Generate an XML Schema from an XML document</span></span>  
  
## <a name="xml-view"></a><span data-ttu-id="eda91-159">Vista XML</span><span class="sxs-lookup"><span data-stu-id="eda91-159">XML View</span></span>  
 <span data-ttu-id="eda91-160">La vista XML proporciona un editor para editar XML sin formato y proporciona también IntelliSense y codificación de colores.</span><span class="sxs-lookup"><span data-stu-id="eda91-160">XML view provides an editor for editing raw XML and provides IntelliSense and color coding.</span></span> <span data-ttu-id="eda91-161">La finalización automática de instrucciones estará disponible cuando se trabaje con archivos .xsd y .xml que dispongan de un esquema asociado.</span><span class="sxs-lookup"><span data-stu-id="eda91-161">Statement completion is available when working on .xsd files and .xml files that have an associated schema.</span></span> <span data-ttu-id="eda91-162">Escriba \< para iniciar una etiqueta y se le presentará una lista de elementos que son válidos en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="eda91-162">Type \< to initiate a tag and you will be presented with a list of elements that are valid at that location.</span></span> <span data-ttu-id="eda91-163">Después de escribir el nombre del elemento y de presionar la BARRA ESPACIADORA, se le mostrará una lista de atributos compatibles con dicho elemento.</span><span class="sxs-lookup"><span data-stu-id="eda91-163">After you type the element name and press the SPACEBAR, you will be presented with a list of attributes that the element supports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="eda91-164">IntelliSense no están disponibles en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="eda91-164">IntelliSense options are not available on the toolbar.</span></span> <span data-ttu-id="eda91-165">Para obtener acceso a las opciones desde el Editor XML, haga clic en **IntelliSense** , en el menú **Edición**.</span><span class="sxs-lookup"><span data-stu-id="eda91-165">When in the XML Editor, to access the options, on the **Edit** menu, click **IntelliSense**.</span></span>  
  
## <a name="showplan-view"></a><span data-ttu-id="eda91-166">Vista SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="eda91-166">SHOWPLAN view</span></span>  
 <span data-ttu-id="eda91-167">Los planes de consulta pueden guardarse en formato XML cuando se crean mediante la opción SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="eda91-167">Query plans can be saved in XML format when created using SET SHOWPLAN_XML ON option.</span></span> <span data-ttu-id="eda91-168">Haga doble clic en un archivo con la extensión .showplan para abrir el plan de consulta.</span><span class="sxs-lookup"><span data-stu-id="eda91-168">Double-click a file with the .showplan extension to open the query plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda91-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eda91-169">See Also</span></span>  
 [<span data-ttu-id="eda91-170">Guardar un plan de ejecución en formato XML</span><span class="sxs-lookup"><span data-stu-id="eda91-170">Save an Execution Plan in XML Format</span></span>](../performance/save-an-execution-plan-in-xml-format.md)  
  
  
