---
title: Anotaciones de CSDL para Business Intelligence (CSDLBI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: bf6f372a-bc67-45ea-a771-b2dc5b0527e5
author: minewiskan
ms.author: owend
ms.openlocfilehash: b3414b0d8b2614e83f62e85c4f750ee0e8c7397d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671238"
---
# <a name="csdl-annotations-for-business-intelligence-csdlbi"></a><span data-ttu-id="0d498-102">Anotaciones de CSDL para Business Intelligence (CSDLBI)</span><span class="sxs-lookup"><span data-stu-id="0d498-102">CSDL Annotations for Business Intelligence (CSDLBI)</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="0d498-103">admite la presentación de la definición de un modelo tabular en un formato XML denominado Lenguaje de definición de esquemas conceptuales con anotaciones Business Intelligence (CSDLBI).</span><span class="sxs-lookup"><span data-stu-id="0d498-103">supports the presentation of the definition of a tabular model in an XML format called Conceptual Schema Definition Language with Business Intelligence annotations (CSDLBI).</span></span>  
  
 <span data-ttu-id="0d498-104">En este tema se proporciona información general sobre CSDLBI y su uso con los modelos de datos de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d498-104">This topic provides an overview of CSDLBI and how it is used with [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data models.</span></span>  
  
## <a name="understanding-the-role-of-csdl"></a><span data-ttu-id="0d498-105">Descripción del propósito de CSDL</span><span class="sxs-lookup"><span data-stu-id="0d498-105">Understanding the Role of CSDL</span></span>  
 <span data-ttu-id="0d498-106">El Lenguaje de definición de esquemas conceptuales (CSDL) es un lenguaje basado en XML que describe las entidades, las relaciones y las funciones.</span><span class="sxs-lookup"><span data-stu-id="0d498-106">The Conceptual Schema Data Language (CSDL) is an XML-based language that describes entities, relationships, and functions.</span></span> <span data-ttu-id="0d498-107">CSDL forma parte de Entity Data Framework.</span><span class="sxs-lookup"><span data-stu-id="0d498-107">CSDL is defined as part of the Entity Data Framework.</span></span> <span data-ttu-id="0d498-108">Las anotaciones BI son una extensión diseñada para admitir el modelado de datos mediante [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d498-108">The BI annotations are an extension designed to support data modeling using [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0d498-109">Aunque CSDL es compatible con Entity Data Framework, no es necesario comprender el modelo entidad-relación ni tener ninguna herramienta especial para generar un modelo tabular o un informe basado en un modelo.</span><span class="sxs-lookup"><span data-stu-id="0d498-109">Although CSDL is compliant with the Entity Data Framework, you do not need to understand the entity-relationship model or have any special tools to build a tabular model or a report based on a model.</span></span> <span data-ttu-id="0d498-110">Es posible generar modelos mediante herramientas cliente como [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o una API como AMO, e implementarlos en un servidor.</span><span class="sxs-lookup"><span data-stu-id="0d498-110">You build models by using client tools such as [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or an API such as AMO, and deploy the model to a server.</span></span> <span data-ttu-id="0d498-111">Los clientes se conectan con el modelo mediante un archivo de definición de modelo, que normalmente se publica en una biblioteca de SharePoint donde pueden utilizarlo los diseñadores de informes y los consumidores de informes.</span><span class="sxs-lookup"><span data-stu-id="0d498-111">Clients connect to the model by using a model definition file, typically published to a SharePoint library where it can be used by report designers and report consumers.</span></span> <span data-ttu-id="0d498-112">Para obtener más información, vea estos vínculos:</span><span class="sxs-lookup"><span data-stu-id="0d498-112">For more information, see these links:</span></span>  
  
-   [<span data-ttu-id="0d498-113">Soluciones de modelos tabulares &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="0d498-113">Tabular Model Solutions &#40;SSAS Tabular&#41;</span></span>](../tabular-model-solutions-ssas-tabular.md)  
  
-   [<span data-ttu-id="0d498-114">Implementación de soluciones de modelos tabulares &#40;SSAS tabular&#41;</span><span class="sxs-lookup"><span data-stu-id="0d498-114">Tabular Model Solution Deployment &#40;SSAS Tabular&#41;</span></span>](../tabular-models/tabular-model-solution-deployment-ssas-tabular.md)  
  
-   [<span data-ttu-id="0d498-115">Conexión de modelo semántico de BI PowerPivot &#40;. Bism&#41;</span><span class="sxs-lookup"><span data-stu-id="0d498-115">PowerPivot BI Semantic Model Connection &#40;.bism&#41;</span></span>](../power-pivot-sharepoint/power-pivot-bi-semantic-model-connection-bism.md)  
  
 <span data-ttu-id="0d498-116">El esquema CSDLBI lo genera el servidor de Analysis Services en respuesta a una solicitud de una definición de modelo realizada por un cliente como [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d498-116">The CSDLBI schema is generated by the Analysis Services server in response to a request for a model definition from a client such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="0d498-117">La aplicación cliente envía una consulta XML al servidor de Analysis Services que hospeda los datos del modelo.</span><span class="sxs-lookup"><span data-stu-id="0d498-117">The client application sends an XML query to the Analysis Services server that hosts the model data.</span></span> <span data-ttu-id="0d498-118">En respuesta, el servidor envía un mensaje XML que contiene una definición de las entidades del modelo, utilizando las anotaciones CSDLBI.</span><span class="sxs-lookup"><span data-stu-id="0d498-118">In response, the server sends an XML message containing a definition of the entities in the model, using the CSDLBI annotations.</span></span> <span data-ttu-id="0d498-119">El cliente de informes usa la información para mostrar los campos, las agregaciones y las medidas disponibles en el modelo.</span><span class="sxs-lookup"><span data-stu-id="0d498-119">The reporting client then uses the information to present the fields, aggregations, and measures that are available in the model.</span></span> <span data-ttu-id="0d498-120">Las anotaciones CSDLBI también proporcionan información sobre cómo agrupar, ordenar y dar formato a los datos.</span><span class="sxs-lookup"><span data-stu-id="0d498-120">The CSDLBI annotations also provide information about how to group, sort, and format the data.</span></span>  
  
 <span data-ttu-id="0d498-121">Para obtener información general sobre CSDLBI, vea [conceptos de CSDLBI](/analysis-services/csdlbi/csdlbi-concepts).</span><span class="sxs-lookup"><span data-stu-id="0d498-121">For general information about CSDLBI, see [CSDLBI Concepts](/analysis-services/csdlbi/csdlbi-concepts).</span></span>  
  
### <a name="working-with-csdl"></a><span data-ttu-id="0d498-122">Trabajar con CSDL</span><span class="sxs-lookup"><span data-stu-id="0d498-122">Working with CSDL</span></span>  
 <span data-ttu-id="0d498-123">El conjunto de anotaciones CSDLBI que representa cualquier modelo tabular determinado es un documento XML que contiene una colección de entidades, tanto simples como complejas.</span><span class="sxs-lookup"><span data-stu-id="0d498-123">The set of CSDLBI annotations that represents any particular tabular model is an XML document containing a collection of entities, both simple and complex.</span></span> <span data-ttu-id="0d498-124">Las entidades definen las tablas (o dimensiones), las columnas (atributos), las asociaciones (relaciones) y las fórmulas incluidas en las columnas calculadas, medidas o KPI.</span><span class="sxs-lookup"><span data-stu-id="0d498-124">The entities define tables (or dimensions), columns (attributes), associations (relationships), and formulas included in calculated columns, measure, or KPIs.</span></span>  
  
 <span data-ttu-id="0d498-125">No puede modificar estos objetos directamente, sino que debe utilizar las herramientas del cliente y las interfaces de programación de aplicaciones (API) proporcionadas para trabajar con modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="0d498-125">You cannot modify these objects directly, but must use the client tools and application programming interfaces (APIs) provided for working with tabular models.</span></span>  
  
 <span data-ttu-id="0d498-126">Puede obtener el CSDL para un modelo enviando una solicitud DISCOVER al servidor que hospeda el modelo.</span><span class="sxs-lookup"><span data-stu-id="0d498-126">You can obtain the CSDL for a model by sending a DISCOVER request to the server that hosts the model.</span></span> <span data-ttu-id="0d498-127">La solicitud se debe calificar especificando el servidor y el modelo y, opcionalmente, una vista o una perspectiva.</span><span class="sxs-lookup"><span data-stu-id="0d498-127">The request must be qualified by specifying the server and the model, and, optionally, a view or perspective.</span></span> <span data-ttu-id="0d498-128">El mensaje devuelto es una cadena XML.</span><span class="sxs-lookup"><span data-stu-id="0d498-128">The returned message is an XML string.</span></span> <span data-ttu-id="0d498-129">Algunos elementos dependen del lenguaje y pueden devolver valores diferentes en función del lenguaje de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="0d498-129">Certain elements are language-dependent and may return different values depending on the language of the current connection.</span></span> <span data-ttu-id="0d498-130">Para obtener más información, vea [DISCOVER_CSDL_METADATA conjunto de filas](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/discover-csdl-metadata-rowset).</span><span class="sxs-lookup"><span data-stu-id="0d498-130">For more information, see [DISCOVER_CSDL_METADATA Rowset](https://docs.microsoft.com/bi-reference/schema-rowsets/xml/discover-csdl-metadata-rowset).</span></span>  
  
### <a name="csdlbi-versions"></a><span data-ttu-id="0d498-131">Versiones de CSDLBI</span><span class="sxs-lookup"><span data-stu-id="0d498-131">CSDLBI Versions</span></span>  
 <span data-ttu-id="0d498-132">La especificación CSDL original (de Entity Data Framework) es suficiente para la mayor parte de las entidades y propiedades necesarias para el modelado.</span><span class="sxs-lookup"><span data-stu-id="0d498-132">The original CSDL specification (from the Entity Data Framework) provides for most of the entities and properties that are needed to support modeling.</span></span> <span data-ttu-id="0d498-133">Las anotaciones BI admiten requisitos especiales de modelos tabulares, propiedades de informes requeridas por clientes como [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] y metadatos adicionales requeridos por modelos multidimensionales.</span><span class="sxs-lookup"><span data-stu-id="0d498-133">The BI annotations support special requirements of tabular models, reporting properties required for clients such as [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)], and additional metadata required for multidimensional models.</span></span> <span data-ttu-id="0d498-134">En esta sección se describen las actualizaciones de cada versión.</span><span class="sxs-lookup"><span data-stu-id="0d498-134">This section describes the updates in each version.</span></span>  
  
 <span data-ttu-id="0d498-135">**CSDLBI 1.0**</span><span class="sxs-lookup"><span data-stu-id="0d498-135">**CSDLBI 1.0**</span></span>  
  
 <span data-ttu-id="0d498-136">El conjunto inicial de adiciones al esquema CSDL para admitir los modelos tabulares de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contenía anotaciones que permitían el uso del modelado de datos, los cálculos personalizados y las presentaciones mejoradas:</span><span class="sxs-lookup"><span data-stu-id="0d498-136">The initial set of additions to the CSDL schema to support [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] tabular models contained annotations in support of data modeling, custom calculations, and enhanced presentation:</span></span>  
  
-   <span data-ttu-id="0d498-137">Nuevos elementos y propiedades para admitir modelos tabulares.</span><span class="sxs-lookup"><span data-stu-id="0d498-137">New elements and properties to support tabular models.</span></span> <span data-ttu-id="0d498-138">Por ejemplo, se agregó una propiedad para especificar el tipo de consulta de base de datos utilizada para rellenar el modelo.</span><span class="sxs-lookup"><span data-stu-id="0d498-138">For example, a property was added to specify the type of database query used to populate the model.</span></span>  
  
-   <span data-ttu-id="0d498-139">Nuevas propiedades y extensiones para las entidades existentes.</span><span class="sxs-lookup"><span data-stu-id="0d498-139">New properties and extensions to existing entities.</span></span>  <span data-ttu-id="0d498-140">Por ejemplo, el elemento Association se extendió para admitir las relaciones.</span><span class="sxs-lookup"><span data-stu-id="0d498-140">For example, the Association element was extended to support relationships.</span></span>  
  
-   <span data-ttu-id="0d498-141">Propiedades de visualización y navegación.</span><span class="sxs-lookup"><span data-stu-id="0d498-141">Visualization and navigation properties.</span></span> <span data-ttu-id="0d498-142">Por ejemplo, se agregaron propiedades para admitir campos de ordenación personalizados e imágenes predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="0d498-142">For example, properties were added to support custom sorting fields, default images, and</span></span>  
  
 <span data-ttu-id="0d498-143">**CSDLBI 1.1**</span><span class="sxs-lookup"><span data-stu-id="0d498-143">**CSDLBI 1.1**</span></span>  
  
 <span data-ttu-id="0d498-144">Esta versión del esquema CSDLBI incluye adiciones para admitir el uso de bases de datos multidimensionales (como los cubos OLAP).</span><span class="sxs-lookup"><span data-stu-id="0d498-144">This version of the CSDLBI schema includes additions in support of multidimensional databases (such as OLAP cubes).</span></span> <span data-ttu-id="0d498-145">Los nuevos elementos y propiedades son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0d498-145">The new elements and properties are as follows:</span></span>  
  
-   <span data-ttu-id="0d498-146">Compatibilidad con las dimensiones como entidades.</span><span class="sxs-lookup"><span data-stu-id="0d498-146">Support for dimensions as entities.</span></span>  
  
-   <span data-ttu-id="0d498-147">Compatibilidad con las jerarquías.</span><span class="sxs-lookup"><span data-stu-id="0d498-147">Support for hierarchies.</span></span>  
  
-   <span data-ttu-id="0d498-148">Expone particiones ROLAP.</span><span class="sxs-lookup"><span data-stu-id="0d498-148">Exposes ROLAP partitions.</span></span>  
  
-   <span data-ttu-id="0d498-149">Compatibilidad con las traducciones.</span><span class="sxs-lookup"><span data-stu-id="0d498-149">Support for translations.</span></span>  
  
-   <span data-ttu-id="0d498-150">Compatibilidad con las perspectivas.</span><span class="sxs-lookup"><span data-stu-id="0d498-150">Support for perspectives.</span></span>  
  
 <span data-ttu-id="0d498-151">Para obtener información detallada sobre los elementos individuales de las anotaciones CSDLBI, vea [referencia técnica para anotaciones de BI en CSDL](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl).</span><span class="sxs-lookup"><span data-stu-id="0d498-151">For detailed information about individual elements in the CSDLBI annotations, see [Technical Reference for BI Annotations to CSDL](/analysis-services/csdlbi/technical-reference-for-bi-annotations-to-csdl).</span></span> <span data-ttu-id="0d498-152">Para obtener información sobre la especificación de CSDL principal, vea la [especificación CSDL V3](https://docs.microsoft.com/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span><span class="sxs-lookup"><span data-stu-id="0d498-152">For information about the core CSDL specification, see the [CSDL v3 Specification](https://docs.microsoft.com/ef/ef6/modeling/designer/advanced/edmx/csdl-spec).</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="0d498-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d498-153">See Also</span></span>  
 <span data-ttu-id="0d498-154">[Descripción del modelo de objetos tabulares](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md) </span><span class="sxs-lookup"><span data-stu-id="0d498-154">[Understanding the Tabular Object Model](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md) </span></span>  
 <span data-ttu-id="0d498-155">[Conceptos de CSDLBI](/analysis-services/csdlbi/csdlbi-concepts) </span><span class="sxs-lookup"><span data-stu-id="0d498-155">[CSDLBI Concepts](/analysis-services/csdlbi/csdlbi-concepts) </span></span>  
 [<span data-ttu-id="0d498-156">Descripción del modelo de objetos tabulares</span><span class="sxs-lookup"><span data-stu-id="0d498-156">Understanding the Tabular Object Model</span></span>](representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
  