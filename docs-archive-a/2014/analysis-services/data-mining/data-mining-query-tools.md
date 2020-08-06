---
title: Interfaces de consulta de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- predictions [Analysis Services], DMX prediction queries
- predictions [DMX]
- DMX [Analysis Services], prediction queries
- prediction queries [DMX]
- predictions [Analysis Services]
- queries [DMX], prediction queries
- mining models [Analysis Services], DMX
ms.assetid: a8952427-fd8c-4300-8f62-25f57ac1be0c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1702ad82c65b5a7370a62c4bc31a08007f374c9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677301"
---
# <a name="data-mining-query-interfaces"></a><span data-ttu-id="394ef-102">Interfaces de consultas de minería de datos</span><span class="sxs-lookup"><span data-stu-id="394ef-102">Data Mining Query Interfaces</span></span>
  <span data-ttu-id="394ef-103">Las consultas de minería de datos se basan en el lenguaje DMX (Extensiones de minería de datos).</span><span class="sxs-lookup"><span data-stu-id="394ef-103">Data mining queries are based on the Data Mining Extensions (DMX) language.</span></span> <span data-ttu-id="394ef-104">DMX se usa para todas las tareas de predicción y modelado, incluida la clasificación, el análisis de riesgos, la generación de recomendaciones y la regresión lineal.</span><span class="sxs-lookup"><span data-stu-id="394ef-104">You use DMX for all prediction and modeling tasks, including classification, risk analysis, generation of recommendations, and linear regression.</span></span> <span data-ttu-id="394ef-105">También puede recuperar los patrones y estadísticas que se generaron al procesar el modelo.</span><span class="sxs-lookup"><span data-stu-id="394ef-105">You can also retrieve the patterns and statistics that were generated when you processed the model.</span></span>  
  
 <span data-ttu-id="394ef-106">La sintaxis para una consulta de predicción usando DMX es similar a la sintaxis para una consulta de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="394ef-106">The syntax for a prediction query using DMX is similar to the syntax for a query in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="394ef-107">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] y [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] proporcionan herramientas que le ayudarán a generar las consultas de predicción DMX.</span><span class="sxs-lookup"><span data-stu-id="394ef-107">Both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] provide tools that help you build DMX prediction queries.</span></span>  
  
 <span data-ttu-id="394ef-108">En este tema se describen las interfaces que puede usar para crear y ejecutar consultas de minería de datos con DMX.</span><span class="sxs-lookup"><span data-stu-id="394ef-108">This topic describes the interfaces that you can use to create and execute data mining queries using DMX.</span></span>  
  
 [<span data-ttu-id="394ef-109">Herramientas de consulta</span><span class="sxs-lookup"><span data-stu-id="394ef-109">Query Tools</span></span>](#bkmk_Tools)  
  
-   [<span data-ttu-id="394ef-110">Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="394ef-110">Prediction Query Builder</span></span>](#bkmk_Builder)  
  
-   [<span data-ttu-id="394ef-111">Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="394ef-111">Query Editor</span></span>](#bkmk_QueryEditor)  
  
-   [<span data-ttu-id="394ef-112">Plantillas DMX</span><span class="sxs-lookup"><span data-stu-id="394ef-112">DMX Templates</span></span>](#bkmk_Templates)  
  
-   [<span data-ttu-id="394ef-113">Servicio de integración</span><span class="sxs-lookup"><span data-stu-id="394ef-113">Integration Services</span></span>](#bkmk_SSIS)  
  
 [<span data-ttu-id="394ef-114">Interfaces de programación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="394ef-114">Application Programming Interfaces</span></span>](#bkmk_API)  
  
##  <a name="data-mining-query-tools"></a><a name="bkmk_Tools"></a><span data-ttu-id="394ef-115">Herramientas de consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="394ef-115">Data Mining Query Tools</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="394ef-116">dispone de las siguientes herramientas que puede utilizar para compilar consultas de predicción, consultas de contenido y consultas de definición de datos en objetos de minería de datos:</span><span class="sxs-lookup"><span data-stu-id="394ef-116">provides the following tools that you can use to build prediction queries, content queries, and data definition queries against data mining objects:</span></span>  
  
-   <span data-ttu-id="394ef-117">Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="394ef-117">Prediction Query Builder</span></span>  
  
-   <span data-ttu-id="394ef-118">Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="394ef-118">Query Editor</span></span>  
  
-   <span data-ttu-id="394ef-119">Plantillas DMX</span><span class="sxs-lookup"><span data-stu-id="394ef-119">DMX templates</span></span>  
  
-   <span data-ttu-id="394ef-120">Componentes de minería de datos de Integration Services</span><span class="sxs-lookup"><span data-stu-id="394ef-120">Integration Services data mining components</span></span>  
  
###  <a name="prediction-query-builder"></a><a name="bkmk_Builder"></a><span data-ttu-id="394ef-121">Generador de consultas de predicción</span><span class="sxs-lookup"><span data-stu-id="394ef-121">Prediction Query Builder</span></span>  
 <span data-ttu-id="394ef-122">El Generador de consultas de predicción se incluye en la pestaña **Predicción de modelo de minería de datos** del Diseñador de minería de datos, el cual está disponible en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]y en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="394ef-122">Prediction Query Builder is included in the **Mining Model Prediction** tab of Data Mining Designer, which is available in both [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="394ef-123">Si utiliza el generador de consultas, puede utilizar las herramientas gráficas para seleccionar un modelo de minería de datos, agregar nuevos datos del caso y agregar funciones de predicción.</span><span class="sxs-lookup"><span data-stu-id="394ef-123">When you use the query builder, you can use graphical tools to select a mining model, add new case data, and add prediction functions.</span></span> <span data-ttu-id="394ef-124">La predicción Generador de consultas incluye un editor de texto que puede usar para modificar manualmente la consulta y un panel de **resultados** sencillo para ver los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="394ef-124">The Prediction Query Builder includes a text editor that you can use to modify the query manually, and a simple **Results** pane to view the results of the query.</span></span>  
  
###  <a name="query-editor"></a><a name="bkmk_QueryEditor"></a><span data-ttu-id="394ef-125">Editor de consultas</span><span class="sxs-lookup"><span data-stu-id="394ef-125">Query Editor</span></span>  
 <span data-ttu-id="394ef-126">El editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] proporciona herramientas que puede utilizar para compilar y ejecutar consultas DMX.</span><span class="sxs-lookup"><span data-stu-id="394ef-126">The Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides tools that you can use to build and run DMX queries.</span></span> <span data-ttu-id="394ef-127">Puede conectar a una instancia de SQL Server Analysis Services y, a continuación, seleccionar una base de datos, columnas de estructura de minería de datos y un modelo de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="394ef-127">You can connect to an instance of SQL Server Analysis Services, and then select a database, mining structure columns, and a mining model.</span></span> <span data-ttu-id="394ef-128">El **Explorador de metadatos** contiene una lista de funciones de predicción que puede examinar.</span><span class="sxs-lookup"><span data-stu-id="394ef-128">The **Metadata Explorer** contains a list of prediction functions that you can browse.</span></span>  
  
###  <a name="dmx-templates"></a><a name="bkmk_Templates"></a><span data-ttu-id="394ef-129">Plantillas DMX</span><span class="sxs-lookup"><span data-stu-id="394ef-129">DMX Templates</span></span>  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="394ef-130">proporciona plantillas de consulta DMX interactivas que puede usar para compilar consultas DMX.</span><span class="sxs-lookup"><span data-stu-id="394ef-130">provides interactive DMX query templates that you can use to build DMX queries.</span></span> <span data-ttu-id="394ef-131">Si no ve la lista de plantillas, haga clic en **Ver** en la barra de herramientas y seleccione **Explorador de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="394ef-131">If you do not see the list of templates, click **View** on the toolbar, and select **Template Explorer**.</span></span> <span data-ttu-id="394ef-132">Para ver todas las plantillas de Analysis Services, incluidas las plantillas para DMX, MDX y XMLA, haga clic en el icono de cubo.</span><span class="sxs-lookup"><span data-stu-id="394ef-132">To see all Analysis Services templates, including templates for DMX, MDX, and XMLA, click the cube icon.</span></span>  
  
 <span data-ttu-id="394ef-133">Para compilar una consulta mediante una plantilla, puede arrastrar la plantilla a una ventana de consulta abierta, o puede hacer doble clic en la plantilla para abrir una nueva conexión y un nuevo panel de consulta.</span><span class="sxs-lookup"><span data-stu-id="394ef-133">To build a query using a template, you can drag the template into an open query window, or you can double-click the template to open a new connection and a new query pane.</span></span>  
  
 <span data-ttu-id="394ef-134">Para consultar un ejemplo de cómo crear una consulta de predicción a partir de una plantilla, vea [Crear una consulta de predicción singleton desde una plantilla](create-a-singleton-prediction-query-from-a-template.md).</span><span class="sxs-lookup"><span data-stu-id="394ef-134">For an example of how to create a prediction query from a template, see [Create a Singleton Prediction Query from a Template](create-a-singleton-prediction-query-from-a-template.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="394ef-135">El Complemento de minería de datos para Microsoft Office Excel también contiene varias plantillas, junto con un generador de consultas interactivo que puede ayudarle a crear instrucciones DMX complejas.</span><span class="sxs-lookup"><span data-stu-id="394ef-135">The Data Mining Add-in for Microsoft Office Excel also contains a number of templates, along with an interactive query builder which can help you compose complex DMX statements.</span></span> <span data-ttu-id="394ef-136">Para utilizar las plantillas, haga clic en **Consulta**, y haga clic en **Avanzadas** en el Cliente de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="394ef-136">To use the templates, click **Query**, and click **Advanced** in the Data Mining Client.</span></span>  
  
###  <a name="integration-services-data-mining-components"></a><a name="bkmk_SSIS"></a><span data-ttu-id="394ef-137">Integration Services componentes de minería de datos</span><span class="sxs-lookup"><span data-stu-id="394ef-137">Integration Services Data Mining Components</span></span>  
 <span data-ttu-id="394ef-138">También puede incluir consultas de predicción como parte de un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] paquete.</span><span class="sxs-lookup"><span data-stu-id="394ef-138">You can also include prediction queries as part of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="394ef-139">Las siguientes tareas y transformaciones de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] admiten la creación y ejecución de consultas de predicción DMX e instrucciones DMX.</span><span class="sxs-lookup"><span data-stu-id="394ef-139">The following tasks and transformations in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] support the creation and execution of DMX prediction queries and DMX statements.</span></span>  
  
|<span data-ttu-id="394ef-140">Componente</span><span class="sxs-lookup"><span data-stu-id="394ef-140">Component</span></span>|<span data-ttu-id="394ef-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="394ef-141">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="394ef-142">Tarea Consulta de minería de datos</span><span class="sxs-lookup"><span data-stu-id="394ef-142">Data Mining Query task</span></span>|<span data-ttu-id="394ef-143">Ejecuta consultas DMX y otras instrucciones DMX como parte de un flujo de control.</span><span class="sxs-lookup"><span data-stu-id="394ef-143">Executes DMX queries and other DMX statements as part of a control flow.</span></span><br /><br /> <span data-ttu-id="394ef-144">El editor de tareas incorpora el Generador de consultas de predicción y un cuadro de texto para modificar la consulta DMX manualmente.</span><span class="sxs-lookup"><span data-stu-id="394ef-144">The task editor provides the Prediction Query Builder, and a text box for modifying the DMX query manually.</span></span> <span data-ttu-id="394ef-145">Sin embargo, el editor de tareas no puede validar la consulta con los objetos de una solución de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="394ef-145">However, the task editor cannot validate the query against objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solution.</span></span> <span data-ttu-id="394ef-146">Por consiguiente, es mejor crear una consulta dentro de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] o [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] y, a continuación, pegar el texto de la instrucción o consulta en el editor de tareas.</span><span class="sxs-lookup"><span data-stu-id="394ef-146">Therefore, it is best to create a query within [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] or [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and then paste the text of the statement or query into the task editor.</span></span>|  
|<span data-ttu-id="394ef-147">Consulta de minería de datos, transformación</span><span class="sxs-lookup"><span data-stu-id="394ef-147">Data Mining Query transformation</span></span>|<span data-ttu-id="394ef-148">Ejecuta una consulta de predicción en un flujo de datos usando los datos proporcionados por un origen de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="394ef-148">Executes a prediction query within a data flow, using data supplied by a data flow source.</span></span><br /><br /> <span data-ttu-id="394ef-149">El editor de tareas incorpora el Generador de consultas de predicción y un cuadro de texto para modificar la consulta DMX manualmente.</span><span class="sxs-lookup"><span data-stu-id="394ef-149">The task editor provides the Prediction Query Builder, and a text box for modifying the DMX query manually.</span></span><br /><br /> <span data-ttu-id="394ef-150">La transformación solo se puede utilizar para crear consultas que utilicen los datos del flujo de datos; es decir, consultas que utilicen la sintaxis de PREDICTION JOIN.</span><span class="sxs-lookup"><span data-stu-id="394ef-150">The transformation can only be used for creating queries that use data in the data flow; that is, queries that use the PREDICTION JOIN syntax.</span></span> <span data-ttu-id="394ef-151">Este componente no se puede utilizar para ejecutar consultas de contenido u otros tipos de instrucciones DMX.</span><span class="sxs-lookup"><span data-stu-id="394ef-151">This component cannot be used for executing content queries or other kinds of DMX statements.</span></span>|  
  
##  <a name="application-programming-interfaces"></a><a name="bkmk_API"></a><span data-ttu-id="394ef-152">Interfaces de programación de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="394ef-152">Application Programming Interfaces</span></span>  
 <span data-ttu-id="394ef-153">Puede crear aplicaciones personalizadas que ejecuten consultas en modelos de minería de datos mediante distintos lenguajes de programación, junto con protocolos de servidor como OLE DB o el cliente ADOMD de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="394ef-153">You can create custom applications that execute queries against data mining models by using a variety of programming languages, in combination with server protocols such as OLE DB or Analysis Services ADOMD client.</span></span> <span data-ttu-id="394ef-154">Para más información, vea [Programación de minería de datos](../dev-guide/data-mining-programming.md).</span><span class="sxs-lookup"><span data-stu-id="394ef-154">For more information, see [Data Mining Programming](../dev-guide/data-mining-programming.md).</span></span>  
  
 <span data-ttu-id="394ef-155">Sin embargo, XMLA constituye el formato del mensaje subyacente para todas las interacciones con un servidor de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="394ef-155">However, XMLA constitutes the underlying message format for all interactions with an Analysis Service server.</span></span> <span data-ttu-id="394ef-156">En un mensaje XMLA, las consultas se representan de forma diferente dependiendo de si se envía una consulta de predicción basada en DMX, una consulta de contenido o una consulta que recupera metadatos del modelo mediante los conjuntos de filas de esquema de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="394ef-156">Within an XMLA message, queries are represented differently depending on whether you are sending a prediction query based on DMX, a content query, or a query that retrieves model metadata using the data mining schema rowsets.</span></span>  
  
-   <span data-ttu-id="394ef-157">El texto de las **consultas de predicción** (y el resto de las instrucciones DMX) se envían en XMLA con el [método Execute &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute), con la consulta DMX colocada como texto en el [elemento Statement &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) del [elemento Command &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/command-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="394ef-157">The text of **prediction queries** (and all other DMX statements) is sent in XMLA by using the [Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method, with the DMX query placed as text within the [Statement Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) element of the XMLA [Command Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/command-element-xmla) element.</span></span>  
  
-   <span data-ttu-id="394ef-158">Para recuperar el **contenido del modelo** y los **metadatos del modelo**, como el número de clústeres, los atributos usados en los árboles de decisión, la fecha en que se procesó el modelo por última vez y los parámetros del algoritmo que se usaron al crear el modelo, puede usar el método [Discover &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) y especificar uno de los conjuntos de filas del esquema de minería de datos en el encabezado del [elemento RequestType &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="394ef-158">To retrieve **model content** and **model metadata**, such as the number of clusters, the attributes used in decision trees, the date the model was last processed, and the algorithm parameters used when creating the model, you can use the [Discover Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) method and specify one of the data mining schema rowsets in the [RequestType Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/type-element-xmla) header.</span></span> <span data-ttu-id="394ef-159">Para restringir el ámbito de la consulta, escriba los criterios como restricciones en el [elemento RestrictionList &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictionlist-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="394ef-159">To narrow the scope of the query, enter criteria as restrictions within the [RestrictionList Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictionlist-element-xmla) element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="394ef-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="394ef-160">See Also</span></span>  
 <span data-ttu-id="394ef-161">[Referencia de extensiones de minería de datos &#40;DMX&#41;](/sql/dmx/data-mining-extensions-dmx-reference) </span><span class="sxs-lookup"><span data-stu-id="394ef-161">[Data Mining Extensions &#40;DMX&#41; Reference](/sql/dmx/data-mining-extensions-dmx-reference) </span></span>  
 <span data-ttu-id="394ef-162">[Soluciones de minería de datos](data-mining-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="394ef-162">[Data Mining Solutions](data-mining-solutions.md) </span></span>  
 <span data-ttu-id="394ef-163">[Descripción de la instrucción SELECT de DMX](/sql/dmx/understanding-the-dmx-select-statement) </span><span class="sxs-lookup"><span data-stu-id="394ef-163">[Understanding the DMX Select Statement](/sql/dmx/understanding-the-dmx-select-statement) </span></span>  
 <span data-ttu-id="394ef-164">[Estructura y uso de las consultas de predicción DMX](/sql/dmx/structure-and-usage-of-dmx-prediction-queries) </span><span class="sxs-lookup"><span data-stu-id="394ef-164">[Structure and Usage of DMX Prediction Queries](/sql/dmx/structure-and-usage-of-dmx-prediction-queries) </span></span>  
 <span data-ttu-id="394ef-165">[Cree una consulta de predicción con la predicción Generador de consultas](create-a-prediction-query-using-the-prediction-query-builder.md) </span><span class="sxs-lookup"><span data-stu-id="394ef-165">[Create a Prediction Query Using the Prediction Query Builder](create-a-prediction-query-using-the-prediction-query-builder.md) </span></span>  
 [<span data-ttu-id="394ef-166">Crear una consulta DMX en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="394ef-166">Create a DMX Query in SQL Server Management Studio</span></span>](create-a-dmx-query-in-sql-server-management-studio.md)  
  
  