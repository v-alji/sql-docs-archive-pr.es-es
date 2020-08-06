---
title: Crear una consulta DMX en SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- templates [Analysis Services], queries
- SQL Server Management Studio [Analysis Services], DMX queries
- predictions [Analysis Services], DMX prediction queries
- predictions [DMX]
- prediction queries [DMX]
- queries [DMX], prediction queries
- mining models [Analysis Services], DMX
ms.assetid: 568ce40a-1f53-47eb-8c79-14347cdfde83
author: minewiskan
ms.author: owend
ms.openlocfilehash: d20fc7a618f4977058203d8f35d235b543609dd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674452"
---
# <a name="create-a-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="70bf6-102">Crear una consulta DMX en SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="70bf6-102">Create a DMX Query in SQL Server Management Studio</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="70bf6-103">proporciona un conjunto de características para ayudarle a crear consultas de predicción, consultas de contenido y consultas de definición de datos en los modelos y estructuras de minería de datos.</span><span class="sxs-lookup"><span data-stu-id="70bf6-103">provides a set of features to help you create prediction queries, content queries, and data definition queries against mining models and mining structures.</span></span>  
  
-   <span data-ttu-id="70bf6-104">El Generador de consultas de predicción gráfico está disponible tanto en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] como en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], para simplificar el proceso de escritura de consultas de predicción y la asignación de conjuntos de datos a un modelo.</span><span class="sxs-lookup"><span data-stu-id="70bf6-104">The graphical Prediction Query Builder is available in both [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], to simplify the process of writing prediction queries and mapping data sets to a model.</span></span>  
  
-   <span data-ttu-id="70bf6-105">Las plantillas de consulta que se proporcionan en el Explorador de plantillas agilizan la creación de muchos tipos de consultas DMX, incluidos muchos tipos de consultas de predicción.</span><span class="sxs-lookup"><span data-stu-id="70bf6-105">The query templates provided in the Template Explorer jump-start the creation of many kinds of DMX queries, including many types of prediction queries.</span></span> <span data-ttu-id="70bf6-106">Se proporcionan plantillas para las consultas de contenido, las consultas que usan conjuntos de datos anidados, las consultas que devuelven casos de la estructura de minería de datos e, incluso, las consultas de definición de datos.</span><span class="sxs-lookup"><span data-stu-id="70bf6-106">Templates are provided for content queries, queries used nested data sets, queries that return cases from the mining structure, and even data definition queries.</span></span>  
  
-   <span data-ttu-id="70bf6-107">El Explorador de metadatos en los paneles de consulta DMX y MDX proporciona una lista de los modelos disponibles y de las estructuras que se pueden arrastrar y colocar en el generador de consultas, junto con una lista de funciones DMX.</span><span class="sxs-lookup"><span data-stu-id="70bf6-107">The Metadata Explorer in the MDX and DMX query panes provides a list of available models and structures that you can drag and drop into the query builder, as well as a list of DMX functions.</span></span> <span data-ttu-id="70bf6-108">Esta característica facilita la obtención de nombres de objeto directamente, sin necesidad de escribir.</span><span class="sxs-lookup"><span data-stu-id="70bf6-108">This feature makes it easy to get object names right, without typing.</span></span>  
  
 <span data-ttu-id="70bf6-109">En este tema se describe cómo crear una consulta DMX mediante el Explorador de metadatos y el editor de consultas DMX.</span><span class="sxs-lookup"><span data-stu-id="70bf6-109">This topic describes how to build a DMX query by using the Metadata Explorer and the DMX query editor.</span></span>  
  
##  <a name="dmx-query-templates"></a><a name="BKMK_Templates"></a><span data-ttu-id="70bf6-110">Plantillas de consulta DMX</span><span class="sxs-lookup"><span data-stu-id="70bf6-110">DMX Query Templates</span></span>  
 <span data-ttu-id="70bf6-111">Las plantillas para crear consultas DMX básicas están disponibles en el Explorador de plantillas.</span><span class="sxs-lookup"><span data-stu-id="70bf6-111">Templates for creating basic DMX queries are available in Template Explorer.</span></span> <span data-ttu-id="70bf6-112">La carpeta **DMX** contiene las plantillas de minería de datos, que se dividen en las categorías siguientes:</span><span class="sxs-lookup"><span data-stu-id="70bf6-112">The **DMX** folder contains data mining templates, which are divided into these categories:</span></span>  
  
-   <span data-ttu-id="70bf6-113">**Contenido del modelo**</span><span class="sxs-lookup"><span data-stu-id="70bf6-113">**Model Content**</span></span>  
  
-   <span data-ttu-id="70bf6-114">**Administración de modelos**</span><span class="sxs-lookup"><span data-stu-id="70bf6-114">**Model Management**</span></span>  
  
-   <span data-ttu-id="70bf6-115">**Consultas de predicción**</span><span class="sxs-lookup"><span data-stu-id="70bf6-115">**Prediction Queries**</span></span>  
  
-   <span data-ttu-id="70bf6-116">**Contenido de la estructura**</span><span class="sxs-lookup"><span data-stu-id="70bf6-116">**Structure Content**</span></span>  
  
 <span data-ttu-id="70bf6-117">También puede crear plantillas personalizadas, para las consultas o los comandos que se ejecutan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="70bf6-117">You can also create custom templates, for queries or commands that you run frequently.</span></span>  
  
## <a name="xmla-query-templates"></a><span data-ttu-id="70bf6-118">Plantillas de consulta XMLA</span><span class="sxs-lookup"><span data-stu-id="70bf6-118">XMLA Query Templates</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="70bf6-119">también proporciona plantillas para las consultas XMLA.</span><span class="sxs-lookup"><span data-stu-id="70bf6-119">also provides templates for XMLA queries.</span></span>  
  
 <span data-ttu-id="70bf6-120">Hay cierta superposición entre los tipos de consultas que se pueden realizar mediante XMLA y DMX.</span><span class="sxs-lookup"><span data-stu-id="70bf6-120">There is some overlap between the types of queries that you can perform by using XMLA and DMX.</span></span> <span data-ttu-id="70bf6-121">Por ejemplo, puede crear algunas consultas de contenido de modelo con conjuntos de filas de esquema de minería de datos o DMX, pero los conjuntos de filas de esquema a veces contienen información que no se expone en las consultas de contenido DMX.</span><span class="sxs-lookup"><span data-stu-id="70bf6-121">For example, you can create some model content queries by using either DMX or the data mining schema rowsets, but the schema rowsets sometimes contain information that is not exposed in DMX content queries.</span></span>  
  
 <span data-ttu-id="70bf6-122">También hay algunas diferencias clave en la manera en que las operaciones se tratan en DMX y en XMLA.</span><span class="sxs-lookup"><span data-stu-id="70bf6-122">There are also some key differences in the way that operations are handled in DMX and in XMLA.</span></span> <span data-ttu-id="70bf6-123">Por ejemplo, puede usar XMLA para realizar operaciones administrativas como la copia de seguridad de una base de datos completa de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]. Pero, si quiere realizar la copia de seguridad de un único modelo de minería de datos, DMX proporciona un sencillo comando, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), que es más adecuado para ese fin.</span><span class="sxs-lookup"><span data-stu-id="70bf6-123">For example, you can use XMLA to perform administrative operations such as backup of an entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, but if you want to back up a single mining model, DMX provides a simple command, [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx), that is better suited to that purpose.</span></span>  
  
##  <a name="build-and-run-a-dmx-query"></a><a name="BKMK_Building_Queries"></a><span data-ttu-id="70bf6-124">Compilar y ejecutar una consulta DMX</span><span class="sxs-lookup"><span data-stu-id="70bf6-124">Build and Run a DMX Query</span></span>  
  
#### <a name="open-a-new-dmx-query-window"></a><span data-ttu-id="70bf6-125">Abrir una nueva ventana de consulta DMX</span><span class="sxs-lookup"><span data-stu-id="70bf6-125">Open a new DMX Query window</span></span>  
  
1.  <span data-ttu-id="70bf6-126">Haga clic en **Nueva consulta** en [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]y, a continuación, seleccione **Consulta DMX de Analysis Server**.</span><span class="sxs-lookup"><span data-stu-id="70bf6-126">Click **New Query** in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then select **New Analysis Server DMX Query**.</span></span>  
  
2.  <span data-ttu-id="70bf6-127">Cuando aparezca el cuadro de diálogo **Conectar al servidor** , seleccione la instancia de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contiene los modelos de minería de datos con los que desea trabajar.</span><span class="sxs-lookup"><span data-stu-id="70bf6-127">When the **Connect to Server** dialog box appears, select the instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] that contains the mining models you want to work with.</span></span>  
  
#### <a name="open-template-explorer"></a><span data-ttu-id="70bf6-128">Abrir el Explorador de plantillas</span><span class="sxs-lookup"><span data-stu-id="70bf6-128">Open Template Explorer</span></span>  
  
1.  <span data-ttu-id="70bf6-129">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver,** seleccione **Explorador de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="70bf6-129">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, select **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="70bf6-130">Haga clic en **Analysis Server** para ver una vista de árbol de las plantillas que se aplican a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="70bf6-130">Click **Analysis Server** to see a tree view of the templates that apply to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
#### <a name="apply-a-template-to-build-a-query"></a><span data-ttu-id="70bf6-131">Aplicar una plantilla para crear una consulta</span><span class="sxs-lookup"><span data-stu-id="70bf6-131">Apply a template to build a query</span></span>  
  
-   <span data-ttu-id="70bf6-132">Haga clic con el botón derecho en el tipo adecuado de consulta y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="70bf6-132">Right-click the appropriate query type and select **Open**.</span></span>  
  
-   <span data-ttu-id="70bf6-133">O bien, arrastre la plantilla en el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="70bf6-133">Or, drag the template into the query editor.</span></span>  
  
-   <span data-ttu-id="70bf6-134">También puede completar los parámetros de la consulta con la opción **Especificar valores para parámetros**, en el menú **Consulta** .</span><span class="sxs-lookup"><span data-stu-id="70bf6-134">You can also fill in the parameters for the query by using the option, **Specify Values for Parameters**, from the **Query** menu.</span></span>  
  
 <span data-ttu-id="70bf6-135">Para obtener ejemplos sobre cómo utilizar tipos específicos de consultas a partir de plantillas, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="70bf6-135">For examples of how to create specific types of queries from templates, see the following topics:</span></span>  
  
 [<span data-ttu-id="70bf6-136">Crear una consulta de predicción singleton desde una plantilla</span><span class="sxs-lookup"><span data-stu-id="70bf6-136">Create a Singleton Prediction Query from a Template</span></span>](create-a-singleton-prediction-query-from-a-template.md)  
  
 [<span data-ttu-id="70bf6-137">Crear una consulta de contenido en un modelo de minería de datos</span><span class="sxs-lookup"><span data-stu-id="70bf6-137">Create a Content Query on a Mining Model</span></span>](create-a-content-query-on-a-mining-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="70bf6-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="70bf6-138">See Also</span></span>  
 <span data-ttu-id="70bf6-139">[Interfaces de consulta de minería de datos](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="70bf6-139">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="70bf6-140">Referencia de Extensiones de minería de datos &#40;DMX&#41;</span><span class="sxs-lookup"><span data-stu-id="70bf6-140">Data Mining Extensions &#40;DMX&#41; Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-reference)  
  
  
