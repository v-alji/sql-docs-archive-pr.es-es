---
title: Sintaxis de consulta XML para los datos de informe XML (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- namespaces [Reporting Services]
- data processing extensions [Reporting Services], data sources
- xmldp [Reporting Services]
- XML [Reporting Services], data retrieval
ms.assetid: d203886f-faa1-4a02-88f5-dd4c217181ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 62dde2b3ab18b5edb5c3786d39173fea3a0854ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662571"
---
# <a name="xml-query-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="30031-102">Sintaxis de consulta XML para los datos de informe XML (SSRS)</span><span class="sxs-lookup"><span data-stu-id="30031-102">XML Query Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="30031-103">En [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], se pueden crear conjuntos de datos para orígenes de datos XML.</span><span class="sxs-lookup"><span data-stu-id="30031-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can create datasets for XML data sources.</span></span> <span data-ttu-id="30031-104">Después de definir un origen de datos, se crea una consulta para el conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="30031-104">After you define a data source, you create a query for the dataset.</span></span> <span data-ttu-id="30031-105">En función del tipo de datos XML a los que señala el origen de datos, la consulta del conjunto de datos se crea incluyendo un elemento XML `Query` o una ruta de acceso de elemento.</span><span class="sxs-lookup"><span data-stu-id="30031-105">Depending on the type of XML data pointed to by the data source, you create the dataset query by including an XML `Query` or an element path.</span></span> <span data-ttu-id="30031-106">Un XML `Query` se inicia con una **\<Query>** etiqueta e incluye espacios de nombres y elementos XML que varían en función del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="30031-106">An XML `Query` starts with a **\<Query>** tag and includes namespaces and XML elements that vary depending on the data source.</span></span> <span data-ttu-id="30031-107">Una ruta de acceso de elemento es independiente del espacio de nombres y especifica qué nodos y atributos de nodo se utilizan de los datos XML subyacentes con una sintaxis del tipo de XPath.</span><span class="sxs-lookup"><span data-stu-id="30031-107">An element path is namespace-independent and specifies which nodes and node attributes to use from the underlying XML data with an XPath-like syntax.</span></span> <span data-ttu-id="30031-108">Para más información sobre las rutas de acceso de elemento, vea [Sintaxis de ruta de acceso de elemento para datos de informe XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="30031-108">For more information about element paths, see [Element Path Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="30031-109">Se pueden crear orígenes de datos XML para los siguientes tipos de datos XML:</span><span class="sxs-lookup"><span data-stu-id="30031-109">You can create an XML data source for the following types of XML data:</span></span>  
  
-   <span data-ttu-id="30031-110">Documentos XML a los que señala una dirección URL mediante el protocolo HTTP</span><span class="sxs-lookup"><span data-stu-id="30031-110">Xml documents pointed to by a URL using http protocol</span></span>  
  
-   <span data-ttu-id="30031-111">Extremos de servicios web que devuelven datos XML</span><span class="sxs-lookup"><span data-stu-id="30031-111">Web service endpoints that return XML data</span></span>  
  
-   <span data-ttu-id="30031-112">Datos XML incrustados</span><span class="sxs-lookup"><span data-stu-id="30031-112">Embedded XML data</span></span>  
  
 <span data-ttu-id="30031-113">La forma en que se especifica un elemento XML `Query` o una ruta de acceso de elemento depende del tipo de los datos XML.</span><span class="sxs-lookup"><span data-stu-id="30031-113">How you specify an XML `Query` or an element path depends on the type of XML data.</span></span>  
  
 <span data-ttu-id="30031-114">En el caso de los documentos XML, el elemento XML `Query` es opcional.</span><span class="sxs-lookup"><span data-stu-id="30031-114">For an XML document, the XML `Query` is optional.</span></span> <span data-ttu-id="30031-115">Si se incluye, puede contener un elemento XML `ElementPath`.</span><span class="sxs-lookup"><span data-stu-id="30031-115">If it is included, it can contain an optional XML `ElementPath`.</span></span> <span data-ttu-id="30031-116">El valor del elemento XML `ElementPath` utiliza la sintaxis de la ruta de acceso de elemento.</span><span class="sxs-lookup"><span data-stu-id="30031-116">The value of the XML `ElementPath` uses the element path syntax.</span></span> <span data-ttu-id="30031-117">Los elementos XML `Query` y `ElementPath` se incluyen para procesar los espacios de nombres correctamente cuando lo requieran los datos XML del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="30031-117">You include the XML `Query` and XML `ElementPath` to process namespaces correctly when it is needed by the XML data from the data source.</span></span>  
  
 <span data-ttu-id="30031-118">Para un extremo de servicios web al que señala una dirección URL de cadena de conexión, el elemento XML `Query` define el método del servicio web, la acción SOAP o ambos.</span><span class="sxs-lookup"><span data-stu-id="30031-118">For a Web service endpoint pointed to by a connection string URL, the XML `Query` defines either the Web service method, the SOAP action, or both.</span></span> <span data-ttu-id="30031-119">El proveedor de datos XML crea una solicitud de servicio web que recupera los datos XML que se utilizarán para el informe.</span><span class="sxs-lookup"><span data-stu-id="30031-119">The XML data provider creates a Web service request that retrieves XML data to use for the report.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="30031-120">Cuando un espacio de nombres de servicio web incluye un carácter de barra diagonal (`/)`, deben incluirse tanto el método del servicio web como la acción SOAP, de manera que la extensión de procesamiento de datos XML pueda derivar el espacio de nombres correctamente.</span><span class="sxs-lookup"><span data-stu-id="30031-120">When a Web service namespace includes a forward slash (`/)` character, include both the Web service method and the SOAP action so that the XML data processing extension can derive the namespace correctly.</span></span>  
  
 <span data-ttu-id="30031-121">En el caso de los documentos XML incrustados, el elemento XML `Query` define los datos XML incrustados que se van a utilizar, incluye espacios de nombres opcionales y contiene un elemento XML `ElementPath` opcional.</span><span class="sxs-lookup"><span data-stu-id="30031-121">For an embedded XML document, the XML `Query` defines the embedded XML data to use, includes optional namespaces, and contains an optional XML `ElementPath`..</span></span>  
  
## <a name="specifying-query-parameters-for-xml-data"></a><span data-ttu-id="30031-122">Especificar parámetros de consulta para datos XML</span><span class="sxs-lookup"><span data-stu-id="30031-122">Specifying Query Parameters for XML Data</span></span>  
 <span data-ttu-id="30031-123">Puede especificar parámetros de consulta para documentos XML.</span><span class="sxs-lookup"><span data-stu-id="30031-123">You can specify query parameters for XML documents.</span></span>  
  
-   <span data-ttu-id="30031-124">Para solicitudes de dirección URL, los parámetros de consulta se incluyen como parámetros de dirección URL estándar.</span><span class="sxs-lookup"><span data-stu-id="30031-124">For URL requests, the query parameters are included as standard URL parameters.</span></span>  
  
-   <span data-ttu-id="30031-125">Para solicitudes de servicio web, los parámetros de consulta se pasan al método del servicio web.</span><span class="sxs-lookup"><span data-stu-id="30031-125">For Web service requests, query parameters are passed to the Web service method.</span></span> <span data-ttu-id="30031-126">Para definir un parámetro de consulta, utilice la página **Parámetros** del cuadro de diálogo **Propiedades del conjunto de datos** .</span><span class="sxs-lookup"><span data-stu-id="30031-126">To define a query parameter, use the **Parameters** page of the **Dataset Properties** dialog box.</span></span> <span data-ttu-id="30031-127">Para obtener más información, vea [Propiedades del conjunto de datos (cuadro de diálogo), Parámetros](dataset-properties-dialog-box-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="30031-127">For more information, see [Dataset Properties Dialog Box, Parameters](dataset-properties-dialog-box-parameters.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="30031-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30031-128">Example</span></span>  
 <span data-ttu-id="30031-129">En los ejemplos de la tabla siguiente se muestra cómo se recuperan los datos desde el servicio web del servidor de informes, un documento XML y datos XML incrustados.</span><span class="sxs-lookup"><span data-stu-id="30031-129">The examples in the following table illustrate how to retrieve data from the Report Server Web service, an XML document, and embedded XML data.</span></span>  
  
|<span data-ttu-id="30031-130">Origen de datos XML</span><span class="sxs-lookup"><span data-stu-id="30031-130">XML data source</span></span>|<span data-ttu-id="30031-131">Ejemplo de consulta</span><span class="sxs-lookup"><span data-stu-id="30031-131">Query example</span></span>|  
|---------------------|-------------------|  
|<span data-ttu-id="30031-132">Datos XML del servicio web obtenidos a través del método ListChildren .</span><span class="sxs-lookup"><span data-stu-id="30031-132">Web service XML data from ListChildren method.</span></span>|`<Query>`<br /><br /> `<Method Name="ListChildren" Namespace="https://schemas.microsoft.com/sqlserver/2005/06/30/reporting/reportingservices" />`<br /><br /> `</Query>`|  
|<span data-ttu-id="30031-133">Datos XML del servicio web obtenidos a través de SoapAction.</span><span class="sxs-lookup"><span data-stu-id="30031-133">Web service XML data from SoapAction.</span></span>|`<Query xmlns=namespace>`<br /><br /> `<SoapAction>http://schemas/microsoft.com/sqlserver/2005/03/23/reporting/reportingservices/ListChildren</SoapAction>`<br /><br /> `</Query>`|  
|<span data-ttu-id="30031-134">Documento XML o datos XML incrustados que usan espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="30031-134">XML Document or embedded XML data that uses namespaces.</span></span><br /><br /> <span data-ttu-id="30031-135">Elemento de consulta que especifica los espacios de nombres de una ruta de acceso de elemento.</span><span class="sxs-lookup"><span data-stu-id="30031-135">Query element specifying namespaces for an element path.</span></span>|`<Query xmlns:es="https://schemas.microsoft.com/StandardSchemas/ExtendedSales">`<br /><br /> `<ElementPath>/Customers/Customer/Orders/Order/es:LineItems/es:LineItem</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="30031-136">Documento XML incrustado.</span><span class="sxs-lookup"><span data-stu-id="30031-136">Embedded XML document.</span></span>|`<Query>`<br /><br /> `<XmlData>`<br /><br /> `<Customers>`<br /><br /> `<Customer ID="1">Bobby</Customer>`<br /><br /> `</Customers>`<br /><br /> `</XmlData>`<br /><br /> `<ElementPath>Customer {@}</ElementPath>`<br /><br /> `</Query>`|  
|<span data-ttu-id="30031-137">Documento XML que usa los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="30031-137">XML document that uses default.</span></span>|<span data-ttu-id="30031-138">*No query*.</span><span class="sxs-lookup"><span data-stu-id="30031-138">*No query*.</span></span><br /><br /> <span data-ttu-id="30031-139">La ruta de acceso de elemento se deriva del propio documento XML y es independiente del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="30031-139">The element path is derived from the XML document itself and is namespace-independent.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="30031-140">El primer ejemplo de servicio web muestra el contenido del servidor de informes que usa el método <xref:ReportService2006.ReportingService2006.ListChildren%2A> .</span><span class="sxs-lookup"><span data-stu-id="30031-140">The first Web service example lists the contents of the report server that uses the <xref:ReportService2006.ReportingService2006.ListChildren%2A> method.</span></span> <span data-ttu-id="30031-141">Para ejecutar esta consulta, es necesario crear un nuevo origen de datos y establecer la cadena de conexión en http://localhost/reportserver/reportservice2006.asmx.</span><span class="sxs-lookup"><span data-stu-id="30031-141">To run this query, you must create a new data source and set the connection string to http://localhost/reportserver/reportservice2006.asmx.</span></span> <span data-ttu-id="30031-142">El método <xref:ReportService2006.ReportingService2006.ListChildren%2A> toma dos parámetros: `Item` y `Recursive`.</span><span class="sxs-lookup"><span data-stu-id="30031-142">The <xref:ReportService2006.ReportingService2006.ListChildren%2A> method takes two parameters: `Item` and `Recursive`.</span></span> <span data-ttu-id="30031-143">Establezca el valor predeterminado de `Item` en `/` y `Recursive` en `1`.</span><span class="sxs-lookup"><span data-stu-id="30031-143">Set the default value for `Item` to `/` and `Recursive` to `1`.</span></span>  
  
## <a name="specifying-namespaces"></a><span data-ttu-id="30031-144">Especificar espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="30031-144">Specifying Namespaces</span></span>  
 <span data-ttu-id="30031-145">Use el elemento XML `Query` para especificar los espacios de nombres que se usan en los datos XML del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="30031-145">Use the XML `Query` element to specify the namespaces that are used in the XML data from the data source.</span></span> <span data-ttu-id="30031-146">En la siguiente consulta XML se utiliza el espacio de nombres `sales`.</span><span class="sxs-lookup"><span data-stu-id="30031-146">The following XML query uses the namespace `sales`.</span></span> <span data-ttu-id="30031-147">Los nodos de elemento XML `ElementPath` para `sales:LineItems` y `sales:LineItem` utilizan el espacio de nombres `sales`.</span><span class="sxs-lookup"><span data-stu-id="30031-147">The XML `ElementPath` nodes for `sales:LineItems` and `sales:LineItem` use the namespace `sales`.</span></span>  
  
```  
<Query xmlns:sales=  
"https://schemas.microsoft.com/StandardSchemas/ExtendedSales">  
   <SoapAction>  
      https://schemas.microsoft.com/SalesWebService/ListOrders   
   </SoapAction>  
   <ElementPath>  
      Customers/Customer/Orders/Order/sales:LineItems/sales:LineItem  
   </ElementPath>  
</Query>  
```  
  
 <span data-ttu-id="30031-148">Para especificar el espacio de nombres del proveedor de datos de manera que el espacio de nombres predeterminado permanezca vacío, utilice `xmldp`.</span><span class="sxs-lookup"><span data-stu-id="30031-148">To specify the data provider namespace so that the default namespace remains empty, use `xmldp`.</span></span> <span data-ttu-id="30031-149">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="30031-149">This is shown in the following example.</span></span>  
  
### <a name="example"></a><span data-ttu-id="30031-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30031-150">Example</span></span>  
 <span data-ttu-id="30031-151">En los ejemplos siguientes se utiliza el documento XML DPNamespace.xml, que se proporciona después de la tabla a modo de ilustración.</span><span class="sxs-lookup"><span data-stu-id="30031-151">The following examples use the XML document DPNamespace.xml, which is provided for illustration after the table.</span></span> <span data-ttu-id="30031-152">En esta tabla se muestran dos ejemplos de sintaxis de ruta de acceso de elemento XML que incluye prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="30031-152">This table shows two examples of XML ElementPath syntax that includes namespace prefixes.</span></span>  
  
|<span data-ttu-id="30031-153">Elemento de consulta XML</span><span class="sxs-lookup"><span data-stu-id="30031-153">XML Query Element</span></span>|<span data-ttu-id="30031-154">Campos resultantes en el conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="30031-154">Resulting fields in the dataset</span></span>|  
|-----------------------|-------------------------------------|  
|\<Query/>|<span data-ttu-id="30031-155">Valor A: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="30031-155">Value A: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="30031-156">Valor B: `https://schemas.microsoft.com/..` .</span><span class="sxs-lookup"><span data-stu-id="30031-156">Value B: `https://schemas.microsoft.com/..`.</span></span><br /><br /> <span data-ttu-id="30031-157">Valor C: `https://schemas.microsoft.com/.` ..</span><span class="sxs-lookup"><span data-stu-id="30031-157">Value C: `https://schemas.microsoft.com/.`..</span></span>|  
|\<xmldp:Query xmlns:xmldp="https://schemas.microsoft.com/sqlserver/2005/02/reporting/XmlDPQuery" xmlns:ns="https://schemas.microsoft.com/..."><br /><br /> <span data-ttu-id="30031-158">\<xmldp:ElementPath>Raíz {} /NS: elemento2/nodo\</xmldp:ElementPath></span><span class="sxs-lookup"><span data-stu-id="30031-158">\<xmldp:ElementPath>Root {}/ns:Element2/Node\</xmldp:ElementPath></span></span><br /><br /> \</xmldp:Query>|<span data-ttu-id="30031-159">Valor D</span><span class="sxs-lookup"><span data-stu-id="30031-159">Value D</span></span><br /><br /> <span data-ttu-id="30031-160">Valor E</span><span class="sxs-lookup"><span data-stu-id="30031-160">Value E</span></span><br /><br /> <span data-ttu-id="30031-161">Valor F</span><span class="sxs-lookup"><span data-stu-id="30031-161">Value F</span></span>|  
  
#### <a name="xml-document-dpnamespacexml"></a><span data-ttu-id="30031-162">Documento XML: DPNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="30031-162">XML document: DPNamespace.xml</span></span>  
 <span data-ttu-id="30031-163">Puede copiar este documento XML y guardarlo en una dirección URL disponible para el Diseñador de informes con objeto de poder usarlo como origen de datos XML, por ejemplo, http://localhost/DPNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="30031-163">You can copy this XML and save it to a URL available for Report Designer to use as an XML data source: for example, http://localhost/DPNamespace.xml.</span></span>  
  
```  
<Root xmlns:ns="https://schemas.microsoft.com/...">  
   <ns:Element1>  
      <Node>Value A</Node>  
      <Node>Value B</Node>  
      <Node>Value C</Node>  
   </ns:Element1>  
   <ns:Element2>  
      <Node>Value D</Node>  
      <Node>Value E</Node>  
      <Node>Value F</Node>  
   </ns:Element2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30031-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="30031-164">See Also</span></span>  
 <span data-ttu-id="30031-165">[Tipo de conexión XML &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="30031-165">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 [<span data-ttu-id="30031-166">Tutoriales de Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="30031-166">Reporting Services Tutorials &#40;SSRS&#41;</span></span>](../reporting-services-tutorials-ssrs.md)  
  
  
