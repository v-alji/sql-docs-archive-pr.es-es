---
title: Sintaxis de ruta de acceso de elemento para datos de informe XML (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ElementPath syntax
- XML [Reporting Services], data retrieval
ms.assetid: 07bd7a4e-fd7a-4a72-9344-3258f7c286d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b7d66b39761dc278abff25a3b22ccd18ca74272b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751778"
---
# <a name="element-path-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="59adf-102">Sintaxis de ruta de acceso de elemento para datos de informe XML (SSRS)</span><span class="sxs-lookup"><span data-stu-id="59adf-102">Element Path Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="59adf-103">En el Diseñador de informes, se define una ruta de acceso de elemento que distingue mayúsculas de minúsculas para especificar los datos que se van a utilizar en un informe desde un origen de datos XML.</span><span class="sxs-lookup"><span data-stu-id="59adf-103">In Report Designer, you specify the data to use for a report from an XML data source by defining a case-sensitive element path.</span></span> <span data-ttu-id="59adf-104">Una ruta de acceso de elemento indica cómo se deben recorrer los nodos jerárquicos XML y sus atributos en el origen de datos XML.</span><span class="sxs-lookup"><span data-stu-id="59adf-104">An element path indicates how to traverse the XML hierarchical nodes and their attributes in the XML data source.</span></span> <span data-ttu-id="59adf-105">Para utilizar la ruta de acceso de elemento predeterminada, mantenga vacía la consulta del conjunto de datos o el elemento XML `ElementPath` del elemento XML `Query`.</span><span class="sxs-lookup"><span data-stu-id="59adf-105">To use the default element path, leave the dataset query or the XML `ElementPath` of the XML `Query` empty.</span></span> <span data-ttu-id="59adf-106">Cuando se recuperan datos del origen de datos XML, los nodos de elemento que tienen valores de texto y atributos de nodo de elemento se convierten en columnas en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="59adf-106">When data is retrieved from the XML data source, element nodes that have text values and element node attributes become columns in the result set.</span></span> <span data-ttu-id="59adf-107">Los valores de los nodos y atributos pasan a ser datos de fila al ejecutar la consulta.</span><span class="sxs-lookup"><span data-stu-id="59adf-107">The values of the nodes and attributes become the row data when you run the query.</span></span> <span data-ttu-id="59adf-108">Las columnas aparecen como la colección de campos del conjunto de datos en el panel Datos de informe.</span><span class="sxs-lookup"><span data-stu-id="59adf-108">The columns appear as the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="59adf-109">En este tema se describe la sintaxis de la ruta de acceso de elemento.</span><span class="sxs-lookup"><span data-stu-id="59adf-109">This topic describes the element path syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59adf-110">La sintaxis de ruta de acceso de elemento es independiente del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="59adf-110">Element path syntax is namespace-independent.</span></span> <span data-ttu-id="59adf-111">Para utilizar espacios de nombres en una ruta de acceso de elemento, use la sintaxis de consulta XML que incluye un `ElementPath` elemento XML descrito en [Sintaxis de consulta XML para datos de informe XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="59adf-111">To use namespaces in an element path, use the XML query syntax that includes an XML `ElementPath` element described in [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="59adf-112">En la tabla siguiente se describen las convenciones que se aplican para definir una ruta de acceso de elemento.</span><span class="sxs-lookup"><span data-stu-id="59adf-112">The following table describes conventions used to define an element path.</span></span>  
  
|<span data-ttu-id="59adf-113">Convención</span><span class="sxs-lookup"><span data-stu-id="59adf-113">Convention</span></span>|<span data-ttu-id="59adf-114">Se usa para</span><span class="sxs-lookup"><span data-stu-id="59adf-114">Used for</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="59adf-115">**Negrita**</span><span class="sxs-lookup"><span data-stu-id="59adf-115">**bold**</span></span>|<span data-ttu-id="59adf-116">Texto que debe escribirse exactamente como se muestra.</span><span class="sxs-lookup"><span data-stu-id="59adf-116">Text that must be typed exactly as shown.</span></span>|  
|<span data-ttu-id="59adf-117">&#124; (barra vertical)</span><span class="sxs-lookup"><span data-stu-id="59adf-117">&#124; (vertical bar)</span></span>|<span data-ttu-id="59adf-118">Separa los elementos de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="59adf-118">Separates syntax items.</span></span> <span data-ttu-id="59adf-119">Solo se puede elegir uno de los elementos.</span><span class="sxs-lookup"><span data-stu-id="59adf-119">You can choose only one of the items.</span></span>|  
|`[ ] (brackets)`|<span data-ttu-id="59adf-120">Elementos opcionales de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="59adf-120">Optional syntax items.</span></span> <span data-ttu-id="59adf-121">No escriba los corchetes.</span><span class="sxs-lookup"><span data-stu-id="59adf-121">Do not type the brackets.</span></span>|  
|<span data-ttu-id="59adf-122">**{}** (llaves)</span><span class="sxs-lookup"><span data-stu-id="59adf-122">**{ }** (braces)</span></span>|<span data-ttu-id="59adf-123">Delimita los parámetros de los elementos de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="59adf-123">Delimits parameters of syntax items.</span></span>|  
|<span data-ttu-id="59adf-124">[ **,** …*n*]</span><span class="sxs-lookup"><span data-stu-id="59adf-124">[**,**...*n*]</span></span>|<span data-ttu-id="59adf-125">Indica que el elemento anterior puede repetirse *n* veces.</span><span class="sxs-lookup"><span data-stu-id="59adf-125">Indicates the preceding item can be repeated *n* number of times.</span></span> <span data-ttu-id="59adf-126">Los elementos se separan por comas.</span><span class="sxs-lookup"><span data-stu-id="59adf-126">The occurrences are separated by commas.</span></span>|  
  
## <a name="syntax"></a><span data-ttu-id="59adf-127">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59adf-127">Syntax</span></span>  
  
```  
  
Element path ::=  
    ElementNode[/Element path]  
ElementNode ::=  
    XMLName[(Encoding)][{[FieldList]}]  
XMLName ::=  
    [NamespacePrefix:]XMLLocalName  
Encoding ::=  
        HTMLEncoded | Base64Encoded  
FieldList ::=  
    Field[,FieldList]  
Field ::=  
    Attribute | Value | Element | ElementNode  
Attribute ::=  
        @XMLName[(Type)]  
Value ::=  
        @[(Type)]  
Element ::=  
    XMLName[(Type)]  
Type ::=  
        String | Integer | Boolean | Float | Decimal | Date | XML   
NamespacePrefix ::=  
    Identifier that specifies the namespace.  
XMLLocalName :: =  
    Identifier in the XML tag.   
```  
  
## <a name="remarks"></a><span data-ttu-id="59adf-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="59adf-128">Remarks</span></span>  
 <span data-ttu-id="59adf-129">En la tabla siguiente se resumen los términos de ruta de acceso de elemento.</span><span class="sxs-lookup"><span data-stu-id="59adf-129">The following table summarizes element path terms.</span></span> <span data-ttu-id="59adf-130">Los ejemplos de la tabla hacen referencia al documento XML de ejemplo Customers.xml, que se incluye en la sección Ejemplos de este tema.</span><span class="sxs-lookup"><span data-stu-id="59adf-130">Examples in the table refer to the example XML document Customers.xml, which is included in the Examples section of this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59adf-131">En las etiquetas XML se distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="59adf-131">XML tags are case-sensitive.</span></span> <span data-ttu-id="59adf-132">Cuando se especifica ElementNode en la ruta de acceso de elemento, debe haber una correspondencia exacta con las etiquetas XML del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="59adf-132">When you specify an ElementNode in the element path, you must exactly match the XML tags in the data source.</span></span>  
  
|<span data-ttu-id="59adf-133">Término</span><span class="sxs-lookup"><span data-stu-id="59adf-133">Term</span></span>|<span data-ttu-id="59adf-134">Definición</span><span class="sxs-lookup"><span data-stu-id="59adf-134">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="59adf-135">Ruta de acceso de elemento</span><span class="sxs-lookup"><span data-stu-id="59adf-135">Element path</span></span>|<span data-ttu-id="59adf-136">Define la secuencia de nodos que deben recorrerse en el documento XML para recuperar los datos de campo de un conjunto de datos con un origen de datos XML.</span><span class="sxs-lookup"><span data-stu-id="59adf-136">Defines the sequence of nodes to traverse within the XML document in order to retrieve field data for a dataset with an XML data source.</span></span>|  
|`ElementNode`|<span data-ttu-id="59adf-137">Nodo XML en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="59adf-137">The XML node in the XML document.</span></span> <span data-ttu-id="59adf-138">Los nodos se designan mediante etiquetas y existen en una relación jerárquica con otros nodos.</span><span class="sxs-lookup"><span data-stu-id="59adf-138">Nodes are designated by tags and exist in a hierarchical relationship with other nodes.</span></span> <span data-ttu-id="59adf-139">Por ejemplo, \<Customers> es el nodo de elemento raíz.</span><span class="sxs-lookup"><span data-stu-id="59adf-139">For example, \<Customers> is the root element node.</span></span> <span data-ttu-id="59adf-140">\<Customer>es un subelemento de \<Customers> .</span><span class="sxs-lookup"><span data-stu-id="59adf-140">\<Customer> is a subelement of \<Customers>.</span></span>|  
|`XMLName`|<span data-ttu-id="59adf-141">El nombre del nodo.</span><span class="sxs-lookup"><span data-stu-id="59adf-141">The name of the node.</span></span> <span data-ttu-id="59adf-142">Por ejemplo, el nombre del nodo Customers es Customers.</span><span class="sxs-lookup"><span data-stu-id="59adf-142">For example, the name of the Customers node is Customers.</span></span> <span data-ttu-id="59adf-143">`XMLName` puede incluir delante un identificador de espacio de nombres para asignar un nombre único a cada nodo.</span><span class="sxs-lookup"><span data-stu-id="59adf-143">An `XMLName` can be prefixed with a namespace identifier to uniquely name every node.</span></span>|  
|`Encoding`|<span data-ttu-id="59adf-144">Indica que `Value` para este elemento es XML codificado y debe descodificarse e incluirse como un subelemento de este elemento.</span><span class="sxs-lookup"><span data-stu-id="59adf-144">Indicates that the `Value` for this element is encoded XML and needs to be decoded and included as a subelement of this element.</span></span>|  
|`FieldList`|<span data-ttu-id="59adf-145">Define el conjunto de elementos y atributos que se van a utilizar para recuperar datos.</span><span class="sxs-lookup"><span data-stu-id="59adf-145">Defines the set of elements and attributes to use to retrieve data.</span></span><br /><br /> <span data-ttu-id="59adf-146">Si no se especifica, se usan como campos todos los atributos y subelementos.</span><span class="sxs-lookup"><span data-stu-id="59adf-146">If not specified, all attributes and subelements are used as fields.</span></span> <span data-ttu-id="59adf-147">Si se especifica la lista de campos vacía ( **{}** ), no se usa ningún campo de este nodo.</span><span class="sxs-lookup"><span data-stu-id="59adf-147">If the empty field list is specified (**{}**), no fields from this node are used.</span></span><br /><br /> <span data-ttu-id="59adf-148">`FieldList` no puede contener a la vez `Value` y `Element` o `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="59adf-148">A `FieldList` may not contain both a `Value` and an `Element` or `ElementNode`.</span></span>|  
|`Field`|<span data-ttu-id="59adf-149">Especifica los datos que se recuperan como campo de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="59adf-149">Specifies the data that is retrieved as a dataset field.</span></span>|  
|`Attribute`|<span data-ttu-id="59adf-150">Par de nombre y valor de `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="59adf-150">A name-value pair within the `ElementNode`.</span></span> <span data-ttu-id="59adf-151">Por ejemplo, en el nodo de elemento \<Customer ID="1"> , `ID` es un atributo y `@ID(Integer)` devuelve "1" como un tipo entero en el campo de datos correspondiente `ID` .</span><span class="sxs-lookup"><span data-stu-id="59adf-151">For example, in the element node \<Customer ID="1">, `ID` is an attribute and `@ID(Integer)` returns "1" as an integer type in the corresponding data field `ID`.</span></span>|  
|`Value`|<span data-ttu-id="59adf-152">Valor del elemento.</span><span class="sxs-lookup"><span data-stu-id="59adf-152">The value of the element.</span></span> <span data-ttu-id="59adf-153">`Value` solo se puede usar en el último `ElementNode` de la ruta de acceso del elemento.</span><span class="sxs-lookup"><span data-stu-id="59adf-153">`Value` can only be used on the last `ElementNode` in the element path.</span></span> <span data-ttu-id="59adf-154">Por ejemplo, dado \<Return> que es un nodo hoja, si se incluye al final de una ruta de acceso de elemento, el valor de `Return {@}` es `Chair` .</span><span class="sxs-lookup"><span data-stu-id="59adf-154">For example, because \<Return> is a leaf node, if you include it at the end of an element path, the value of `Return {@}` is `Chair`.</span></span>|  
|`Element`|<span data-ttu-id="59adf-155">Valor del subelemento con nombre.</span><span class="sxs-lookup"><span data-stu-id="59adf-155">The value of the named subelement.</span></span> <span data-ttu-id="59adf-156">Por ejemplo, Customers {}/Customer {}/LastName recupera valores únicamente para el elemento LastName.</span><span class="sxs-lookup"><span data-stu-id="59adf-156">For example, Customers {}/Customer {}/LastName retrieves values for only the LastName element.</span></span>|  
|`Type`|<span data-ttu-id="59adf-157">Tipo de datos opcional que se usa para el campo creado a partir de este elemento.</span><span class="sxs-lookup"><span data-stu-id="59adf-157">The optional data type to use for the field created from this element.</span></span>|  
|`NamespacePrefix`|<span data-ttu-id="59adf-158">`NamespacePrefix` se define en el elemento XML Query.</span><span class="sxs-lookup"><span data-stu-id="59adf-158">`NamespacePrefix` is defined in the XML Query element.</span></span> <span data-ttu-id="59adf-159">Si no existe ningún elemento XML Query, se pasan por alto los espacios de nombres del elemento XML `ElementPath`.</span><span class="sxs-lookup"><span data-stu-id="59adf-159">If no XML Query element exists, namespaces in the XML `ElementPath` are ignored.</span></span> <span data-ttu-id="59adf-160">Si hay un elemento XML Query, el elemento XML `ElementPath` tiene un atributo `IgnoreNamespaces` opcional.</span><span class="sxs-lookup"><span data-stu-id="59adf-160">If there is an XML Query element, the XML `ElementPath` has an optional attribute `IgnoreNamespaces`.</span></span> <span data-ttu-id="59adf-161">Si IgnoreNamespaces es `true` , se omiten los espacios de nombres en XML `ElementPath` y el documento XML.</span><span class="sxs-lookup"><span data-stu-id="59adf-161">If IgnoreNamespaces is `true`, namespaces in the XML `ElementPath` and the XML document are ignored.</span></span> <span data-ttu-id="59adf-162">Para más información, vea [Sintaxis de consulta XML para los datos de informe XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="59adf-162">For more information, see [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>|  
  
## <a name="example---no-namespaces"></a><span data-ttu-id="59adf-163">Ejemplo: sin espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="59adf-163">Example - No Namespaces</span></span>  
 <span data-ttu-id="59adf-164">En los ejemplos siguientes se usa el documento XML Customers.xml.</span><span class="sxs-lookup"><span data-stu-id="59adf-164">The following examples use the XML document Customers.xml.</span></span> <span data-ttu-id="59adf-165">En esta tabla se muestran ejemplos de sintaxis de ruta de acceso de elemento y los resultados que se obtienen al utilizar la ruta de acceso de elemento en una consulta que define un conjunto de datos, basándose en el documento XML como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="59adf-165">This table shows examples of element path syntax and the results of using the element path in a query that defines a dataset, based on the XML document as a data source.</span></span>  
  
 <span data-ttu-id="59adf-166">Tenga en cuenta que cuando la ruta de acceso del elemento está vacía, la consulta utiliza la ruta de acceso del elemento predeterminada: la primera ruta de acceso a una colección de nodos hoja.</span><span class="sxs-lookup"><span data-stu-id="59adf-166">Note that when the element path is empty, the query uses the default element path: the first path to a leaf node collection.</span></span> <span data-ttu-id="59adf-167">En el primer ejemplo, dejar la ruta de acceso de elemento vacía equivale a especificar la ruta de acceso de elemento /Customers/Customer/Orders/Order.</span><span class="sxs-lookup"><span data-stu-id="59adf-167">In the first example, leaving the element path empty is equivalent to specifying the element path /Customers/Customer/Orders/Order.</span></span> <span data-ttu-id="59adf-168">Todos los valores de nodo y atributos de la ruta se devuelven en el conjunto de resultados, y los nombres de nodo y nombres de atributo aparecen como campos de conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="59adf-168">All node value and attributes along the path are returned in the result set, and the node names and attributes names appear as dataset fields.</span></span>  
  
-   <span data-ttu-id="59adf-169">*Vacío*</span><span class="sxs-lookup"><span data-stu-id="59adf-169">*Empty*</span></span>  
  
    |<span data-ttu-id="59adf-170">Pedido de</span><span class="sxs-lookup"><span data-stu-id="59adf-170">Order</span></span>|<span data-ttu-id="59adf-171">Cantidad</span><span class="sxs-lookup"><span data-stu-id="59adf-171">Qty</span></span>|<span data-ttu-id="59adf-172">ID</span><span class="sxs-lookup"><span data-stu-id="59adf-172">ID</span></span>|<span data-ttu-id="59adf-173">Nombre</span><span class="sxs-lookup"><span data-stu-id="59adf-173">FirstName</span></span>|<span data-ttu-id="59adf-174">Apellidos</span><span class="sxs-lookup"><span data-stu-id="59adf-174">LastName</span></span>|<span data-ttu-id="59adf-175">Customer.ID</span><span class="sxs-lookup"><span data-stu-id="59adf-175">Customer.ID</span></span>|<span data-ttu-id="59adf-176">xmlns</span><span class="sxs-lookup"><span data-stu-id="59adf-176">xmlns</span></span>|  
    |-----------|---------|--------|---------------|--------------|-----------------|-----------|  
    |<span data-ttu-id="59adf-177">Chair</span><span class="sxs-lookup"><span data-stu-id="59adf-177">Chair</span></span>|<span data-ttu-id="59adf-178">6</span><span class="sxs-lookup"><span data-stu-id="59adf-178">6</span></span>|<span data-ttu-id="59adf-179">1</span><span class="sxs-lookup"><span data-stu-id="59adf-179">1</span></span>|<span data-ttu-id="59adf-180">Bobby</span><span class="sxs-lookup"><span data-stu-id="59adf-180">Bobby</span></span>|<span data-ttu-id="59adf-181">Moore</span><span class="sxs-lookup"><span data-stu-id="59adf-181">Moore</span></span>|<span data-ttu-id="59adf-182">11</span><span class="sxs-lookup"><span data-stu-id="59adf-182">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="59adf-183">Tabla</span><span class="sxs-lookup"><span data-stu-id="59adf-183">Table</span></span>|<span data-ttu-id="59adf-184">1</span><span class="sxs-lookup"><span data-stu-id="59adf-184">1</span></span>|<span data-ttu-id="59adf-185">2</span><span class="sxs-lookup"><span data-stu-id="59adf-185">2</span></span>|<span data-ttu-id="59adf-186">Bobby</span><span class="sxs-lookup"><span data-stu-id="59adf-186">Bobby</span></span>|<span data-ttu-id="59adf-187">Moore</span><span class="sxs-lookup"><span data-stu-id="59adf-187">Moore</span></span>|<span data-ttu-id="59adf-188">11</span><span class="sxs-lookup"><span data-stu-id="59adf-188">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="59adf-189">Sofa</span><span class="sxs-lookup"><span data-stu-id="59adf-189">Sofa</span></span>|<span data-ttu-id="59adf-190">2</span><span class="sxs-lookup"><span data-stu-id="59adf-190">2</span></span>|<span data-ttu-id="59adf-191">8</span><span class="sxs-lookup"><span data-stu-id="59adf-191">8</span></span>|<span data-ttu-id="59adf-192">Crystal</span><span class="sxs-lookup"><span data-stu-id="59adf-192">Crystal</span></span>|<span data-ttu-id="59adf-193">Hu</span><span class="sxs-lookup"><span data-stu-id="59adf-193">Hu</span></span>|<span data-ttu-id="59adf-194">20</span><span class="sxs-lookup"><span data-stu-id="59adf-194">20</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="59adf-195">EndTables</span><span class="sxs-lookup"><span data-stu-id="59adf-195">EndTables</span></span>|<span data-ttu-id="59adf-196">2</span><span class="sxs-lookup"><span data-stu-id="59adf-196">2</span></span>|<span data-ttu-id="59adf-197">15</span><span class="sxs-lookup"><span data-stu-id="59adf-197">15</span></span>|<span data-ttu-id="59adf-198">Wyatt</span><span class="sxs-lookup"><span data-stu-id="59adf-198">Wyatt</span></span>|<span data-ttu-id="59adf-199">Diaz</span><span class="sxs-lookup"><span data-stu-id="59adf-199">Diaz</span></span>|<span data-ttu-id="59adf-200">33</span><span class="sxs-lookup"><span data-stu-id="59adf-200">33</span></span>|http://www.adventure-works.com|  
  
-   `Customers {}/Customer`  
  
    |<span data-ttu-id="59adf-201">Nombre</span><span class="sxs-lookup"><span data-stu-id="59adf-201">FirstName</span></span>|<span data-ttu-id="59adf-202">Apellidos</span><span class="sxs-lookup"><span data-stu-id="59adf-202">LastName</span></span>|<span data-ttu-id="59adf-203">ID</span><span class="sxs-lookup"><span data-stu-id="59adf-203">ID</span></span>|  
    |---------------|--------------|--------|  
    |<span data-ttu-id="59adf-204">Bobby</span><span class="sxs-lookup"><span data-stu-id="59adf-204">Bobby</span></span>|<span data-ttu-id="59adf-205">Moore</span><span class="sxs-lookup"><span data-stu-id="59adf-205">Moore</span></span>|<span data-ttu-id="59adf-206">11</span><span class="sxs-lookup"><span data-stu-id="59adf-206">11</span></span>|  
    |<span data-ttu-id="59adf-207">Crystal</span><span class="sxs-lookup"><span data-stu-id="59adf-207">Crystal</span></span>|<span data-ttu-id="59adf-208">Hu</span><span class="sxs-lookup"><span data-stu-id="59adf-208">Hu</span></span>|<span data-ttu-id="59adf-209">20</span><span class="sxs-lookup"><span data-stu-id="59adf-209">20</span></span>|  
    |<span data-ttu-id="59adf-210">Wyatt</span><span class="sxs-lookup"><span data-stu-id="59adf-210">Wyatt</span></span>|<span data-ttu-id="59adf-211">Diaz</span><span class="sxs-lookup"><span data-stu-id="59adf-211">Diaz</span></span>|<span data-ttu-id="59adf-212">33</span><span class="sxs-lookup"><span data-stu-id="59adf-212">33</span></span>|  
  
-   `Customers {}/Customer {}/LastName`  
  
    |<span data-ttu-id="59adf-213">Apellidos</span><span class="sxs-lookup"><span data-stu-id="59adf-213">LastName</span></span>|  
    |--------------|  
    |<span data-ttu-id="59adf-214">Moore</span><span class="sxs-lookup"><span data-stu-id="59adf-214">Moore</span></span>|  
    |<span data-ttu-id="59adf-215">Hu</span><span class="sxs-lookup"><span data-stu-id="59adf-215">Hu</span></span>|  
    |<span data-ttu-id="59adf-216">Diaz</span><span class="sxs-lookup"><span data-stu-id="59adf-216">Diaz</span></span>|  
  
-   `Customers {}/Customer {}/Orders/Order {@,@Qty}`  
  
    |<span data-ttu-id="59adf-217">Pedido de</span><span class="sxs-lookup"><span data-stu-id="59adf-217">Order</span></span>|<span data-ttu-id="59adf-218">Cantidad</span><span class="sxs-lookup"><span data-stu-id="59adf-218">Qty</span></span>|  
    |-----------|---------|  
    |<span data-ttu-id="59adf-219">Chair</span><span class="sxs-lookup"><span data-stu-id="59adf-219">Chair</span></span>|<span data-ttu-id="59adf-220">6</span><span class="sxs-lookup"><span data-stu-id="59adf-220">6</span></span>|  
    |<span data-ttu-id="59adf-221">Tabla</span><span class="sxs-lookup"><span data-stu-id="59adf-221">Table</span></span>|<span data-ttu-id="59adf-222">1</span><span class="sxs-lookup"><span data-stu-id="59adf-222">1</span></span>|  
    |<span data-ttu-id="59adf-223">Sofa</span><span class="sxs-lookup"><span data-stu-id="59adf-223">Sofa</span></span>|<span data-ttu-id="59adf-224">2</span><span class="sxs-lookup"><span data-stu-id="59adf-224">2</span></span>|  
    |<span data-ttu-id="59adf-225">EndTables</span><span class="sxs-lookup"><span data-stu-id="59adf-225">EndTables</span></span>|<span data-ttu-id="59adf-226">2</span><span class="sxs-lookup"><span data-stu-id="59adf-226">2</span></span>|  
  
-   `Customers {}/Customer/Orders/Order{ @ID(Integer)}`  
  
    |<span data-ttu-id="59adf-227">Order.ID</span><span class="sxs-lookup"><span data-stu-id="59adf-227">Order.ID</span></span>|<span data-ttu-id="59adf-228">Nombre</span><span class="sxs-lookup"><span data-stu-id="59adf-228">FirstName</span></span>|<span data-ttu-id="59adf-229">Apellidos</span><span class="sxs-lookup"><span data-stu-id="59adf-229">LastName</span></span>|<span data-ttu-id="59adf-230">ID</span><span class="sxs-lookup"><span data-stu-id="59adf-230">ID</span></span>|  
    |--------------|---------------|--------------|--------|  
    |<span data-ttu-id="59adf-231">1</span><span class="sxs-lookup"><span data-stu-id="59adf-231">1</span></span>|<span data-ttu-id="59adf-232">Bobby</span><span class="sxs-lookup"><span data-stu-id="59adf-232">Bobby</span></span>|<span data-ttu-id="59adf-233">Moore</span><span class="sxs-lookup"><span data-stu-id="59adf-233">Moore</span></span>|<span data-ttu-id="59adf-234">11</span><span class="sxs-lookup"><span data-stu-id="59adf-234">11</span></span>|  
    |<span data-ttu-id="59adf-235">2</span><span class="sxs-lookup"><span data-stu-id="59adf-235">2</span></span>|<span data-ttu-id="59adf-236">Bobby</span><span class="sxs-lookup"><span data-stu-id="59adf-236">Bobby</span></span>|<span data-ttu-id="59adf-237">Moore</span><span class="sxs-lookup"><span data-stu-id="59adf-237">Moore</span></span>|<span data-ttu-id="59adf-238">11</span><span class="sxs-lookup"><span data-stu-id="59adf-238">11</span></span>|  
    |<span data-ttu-id="59adf-239">8</span><span class="sxs-lookup"><span data-stu-id="59adf-239">8</span></span>|<span data-ttu-id="59adf-240">Crystal</span><span class="sxs-lookup"><span data-stu-id="59adf-240">Crystal</span></span>|<span data-ttu-id="59adf-241">Hu</span><span class="sxs-lookup"><span data-stu-id="59adf-241">Hu</span></span>|<span data-ttu-id="59adf-242">20</span><span class="sxs-lookup"><span data-stu-id="59adf-242">20</span></span>|  
    |<span data-ttu-id="59adf-243">15</span><span class="sxs-lookup"><span data-stu-id="59adf-243">15</span></span>|<span data-ttu-id="59adf-244">Wyatt</span><span class="sxs-lookup"><span data-stu-id="59adf-244">Wyatt</span></span>|<span data-ttu-id="59adf-245">Diaz</span><span class="sxs-lookup"><span data-stu-id="59adf-245">Diaz</span></span>|<span data-ttu-id="59adf-246">33</span><span class="sxs-lookup"><span data-stu-id="59adf-246">33</span></span>|  
  
#### <a name="xml-document-customersxml"></a><span data-ttu-id="59adf-247">Documento XML: Customers.xml</span><span class="sxs-lookup"><span data-stu-id="59adf-247">XML document: Customers.xml</span></span>  
 <span data-ttu-id="59adf-248">Para probar los ejemplos de ruta de acceso de elemento de la sección anterior, puede copiar este XML, guardarlo en una dirección URL a la que tenga acceso el Diseñador de informes y, a continuación, usar el documento XML como origen de datos XML: por ejemplo, `http://localhost/Customers.xml`.</span><span class="sxs-lookup"><span data-stu-id="59adf-248">To try out the element path examples in the previous section, you can copy this XML and save it to a URL that is accessible by Report Designer, and then use the XML document as an XML data source: for example, `http://localhost/Customers.xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<Customers xmlns="http://www.adventure-works.com">  
   <Customer ID="11">  
      <FirstName>Bobby</FirstName>  
      <LastName>Moore</LastName>  
      <Orders>  
         <Order ID="1" Qty="6">Chair</Order>  
         <Order ID="2" Qty="1">Table</Order>  
      </Orders>  
      <Returns>  
         <Return ID="1" Qty="2">Chair</Return>  
      </Returns>  
   </Customer>  
   <Customer ID="20">  
      <FirstName>Crystal</FirstName>  
      <LastName>Hu</LastName>  
      <Orders>  
         <Order ID="8" Qty="2">Sofa</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
   <Customer ID="33">  
      <FirstName>Wyatt</FirstName>  
      <LastName>Diaz</LastName>  
      <Orders>  
         <Order ID="15" Qty="2">EndTables</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
</Customers>  
```  
  
 <span data-ttu-id="59adf-249">O bien, puede crear un origen de datos XML que no tenga ninguna cadena de conexión e incrustar Customers.XML en la consulta mediante el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="59adf-249">Alternatively, you can create an XML data source that has no connection string and embed Customers.XML in the query, using the following procedure:</span></span>  
  
###### <a name="to-embed-customersxml-in-a-query"></a><span data-ttu-id="59adf-250">Para incrustar Customers.XML en una consulta</span><span class="sxs-lookup"><span data-stu-id="59adf-250">To embed Customers.XML in a query</span></span>  
  
1.  <span data-ttu-id="59adf-251">Cree un origen de datos XML con una cadena de conexión en blanco.</span><span class="sxs-lookup"><span data-stu-id="59adf-251">Create an XML data source with a blank connection string.</span></span>  
  
2.  <span data-ttu-id="59adf-252">Cree un nuevo conjunto de datos para el origen de datos XML.</span><span class="sxs-lookup"><span data-stu-id="59adf-252">Create a new dataset for the XML data source.</span></span>  
  
3.  <span data-ttu-id="59adf-253">En el cuadro de diálogo **Propiedades del conjunto de datos** , haga clic en **Diseñador de consultas**.</span><span class="sxs-lookup"><span data-stu-id="59adf-253">In the **Dataset Properties** dialog box, click **Query Designer**.</span></span> <span data-ttu-id="59adf-254">Se abre el cuadro de diálogo del diseñador de consultas basado en texto.</span><span class="sxs-lookup"><span data-stu-id="59adf-254">The text-based query designer dialog box opens.</span></span>  
  
4.  <span data-ttu-id="59adf-255">Escriba las dos líneas siguientes en el panel de consulta:</span><span class="sxs-lookup"><span data-stu-id="59adf-255">In the query pane, enter the following two lines:</span></span>  
  
     `<Query>`  
  
     `<XmlData>`  
  
5.  <span data-ttu-id="59adf-256">Copie Customers.XML y pegue el texto en el panel de consulta después de `<XmlData>`.</span><span class="sxs-lookup"><span data-stu-id="59adf-256">Copy Customers.XML and paste the text in the query pane after `<XmlData>`.</span></span>  
  
6.  <span data-ttu-id="59adf-257">En el panel de consulta, elimine la primera línea que copió de Customers.XML: `<?xml version="1.0"?>`</span><span class="sxs-lookup"><span data-stu-id="59adf-257">In the query pane, delete the first line that you copied from Customers.XML: `<?xml version="1.0"?>`</span></span>  
  
7.  <span data-ttu-id="59adf-258">Al final de la consulta, agregue las dos líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="59adf-258">At the end of the query, add the following two lines:</span></span>  
  
     `<XmlData>`  
  
     `<Query>`  
  
8.  <span data-ttu-id="59adf-259">Haga clic en **Ejecutar consulta** (!).</span><span class="sxs-lookup"><span data-stu-id="59adf-259">Click **Run Query** (!).</span></span>  
  
     <span data-ttu-id="59adf-260">El conjunto de resultados muestra 4 líneas de datos con las columnas siguientes: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span><span class="sxs-lookup"><span data-stu-id="59adf-260">The result set displays 4 lines of data with the following columns: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="59adf-261">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59adf-261">See Also</span></span>  
 <span data-ttu-id="59adf-262">[Tipo de conexión XML &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="59adf-262">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 <span data-ttu-id="59adf-263">[Reporting Services tutoriales &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="59adf-263">[Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span></span>  
 [<span data-ttu-id="59adf-264">Agregar, editar y actualizar campos en el panel Datos de informe &#40;Generador de informes y SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="59adf-264">Add, Edit, Refresh Fields in the Report Data Pane &#40;Report Builder and SSRS&#41;</span></span>](add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md)  
  
  
