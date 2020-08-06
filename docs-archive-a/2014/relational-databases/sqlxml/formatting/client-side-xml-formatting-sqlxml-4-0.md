---
title: Formato XML del lado cliente (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- FOR XML clause, formatting
- middle tier XML formatting [SQLXML]
- client-side XML formatting
- client-side-xml attribute
ms.assetid: 9630a21d-a93b-4d3b-8a25-c4b32399f993
author: rothja
ms.author: jroth
ms.openlocfilehash: bf4a680d79a25d24ebdf779b41fd3be5a5d6a605
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674704"
---
# <a name="client-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="9ae68-102">Aplicación de formato XML en el cliente (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="9ae68-102">Client-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="9ae68-103">En este tema se proporciona información acerca de la aplicación de formato XML del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="9ae68-103">This topic provides information about client-side XML formatting.</span></span> <span data-ttu-id="9ae68-104">La aplicación de formato en el cliente se refiere a dar formato al XML en nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="9ae68-104">Client-side formatting refers to the formatting of XML on the middle tier.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ae68-105">En este tema se proporciona información adicional acerca de la forma de usar la cláusula FOR XML en el cliente y se da por sentado que está familiarizado con la cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="9ae68-105">This topic provides additional information about using the FOR XML clause on the client side, and assumes you are already familiar with the FOR XML clause.</span></span> <span data-ttu-id="9ae68-106">Para obtener más información acerca de FOR XML, vea [generar XML mediante for XML](../../xml/for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9ae68-106">For more information about FOR XML, see [Constructing XML Using FOR XML](../../xml/for-xml-sql-server.md).</span></span>  
  
 <span data-ttu-id="9ae68-107">**Importante** Para usar la funcionalidad FOR XML del lado cliente con el nuevo `xml` tipo de datos, los clientes deben usar siempre el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proveedor de datos de Native Client (SQLNCLI11) en lugar del proveedor SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="9ae68-107">**Important** To use client-side FOR XML functionality with the new `xml` data type, clients should always use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) data provider instead of the SQLOLEDB provider.</span></span> <span data-ttu-id="9ae68-108">SQLNCLI11 es la versión más reciente del proveedor de SQL Server y entiende a la perfección los tipos de datos incluidos en [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ae68-108">SQLNCLI11 is the latest version of the SQL Server provider and fully understands data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="9ae68-109">El uso de FOR XML en el cliente con el proveedor SQLOLEDB hará que los tipos de datos `xml` se consideren como cadenas.</span><span class="sxs-lookup"><span data-stu-id="9ae68-109">The behavior for client side FOR XML with the SQLOLEDB provider will treat `xml` data types as strings.</span></span>  
  
## <a name="formatting-xml-documents-on-the-client-side"></a><span data-ttu-id="9ae68-110">Aplicar formato a documentos XML en el cliente</span><span class="sxs-lookup"><span data-stu-id="9ae68-110">Formatting XML Documents on the Client Side</span></span>  
 <span data-ttu-id="9ae68-111">Cuando una aplicación cliente ejecuta la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="9ae68-111">When a client application executes the following query:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
FOR XML RAW  
```  
  
 <span data-ttu-id="9ae68-112">...solo esta parte de la consulta se envía al servidor:</span><span class="sxs-lookup"><span data-stu-id="9ae68-112">...only this part of the query is sent to the server:</span></span>  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
```  
  
 <span data-ttu-id="9ae68-113">El servidor ejecuta la consulta y devuelve un conjunto de filas (que contiene FirstName y LastNamecolumns) al cliente.</span><span class="sxs-lookup"><span data-stu-id="9ae68-113">The server executes the query and returns a rowset (which contains FirstName and LastNamecolumns) to the client.</span></span> <span data-ttu-id="9ae68-114">A continuación, el nivel intermedio aplica la transformación FOR XML al conjunto de filas y devuelve el formato XML al cliente.</span><span class="sxs-lookup"><span data-stu-id="9ae68-114">The middle tier then applies the FOR XML transformation to the rowset and returns XML formatting to the client.</span></span>  
  
 <span data-ttu-id="9ae68-115">Del mismo modo, al ejecutar una consulta XPath, el servidor devuelve el conjunto de filas al cliente y la transformación FOR XML EXPLICIT se aplica al conjunto de filas en el cliente, de forma que se genera el formato XML deseado.</span><span class="sxs-lookup"><span data-stu-id="9ae68-115">Similarly, when you execute an XPath query, the server returns the rowset to the client and the FOR XML EXPLICIT transformation is applied to the rowset on the client, generating the desired XML formatting.</span></span>  
  
 <span data-ttu-id="9ae68-116">En la tabla siguiente se muestran los modos que pueden especificarse con FOR XML del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="9ae68-116">The following table shows the modes you can specify with client-side FOR XML.</span></span>  
  
|<span data-ttu-id="9ae68-117">Modo FOR XML del lado cliente</span><span class="sxs-lookup"><span data-stu-id="9ae68-117">Client-side FOR XML mode</span></span>|<span data-ttu-id="9ae68-118">Comentario</span><span class="sxs-lookup"><span data-stu-id="9ae68-118">Comment</span></span>|  
|-------------------------------|-------------|  
|<span data-ttu-id="9ae68-119">RAW</span><span class="sxs-lookup"><span data-stu-id="9ae68-119">RAW</span></span>|<span data-ttu-id="9ae68-120">Genera resultados idénticos cuando se especifica en FOR XML del lado cliente o del lado servidor.</span><span class="sxs-lookup"><span data-stu-id="9ae68-120">Produces identical results when specified in client-side or server-side FOR XML.</span></span>|  
|<span data-ttu-id="9ae68-121">NESTED</span><span class="sxs-lookup"><span data-stu-id="9ae68-121">NESTED</span></span>|<span data-ttu-id="9ae68-122">Es similar al modo FOR XML AUTO en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9ae68-122">Is similar to FOR XML AUTO mode on the server-side.</span></span>|  
|<span data-ttu-id="9ae68-123">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="9ae68-123">EXPLICIT</span></span>|<span data-ttu-id="9ae68-124">Es similar al modo FOR XML EXPLICIT en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9ae68-124">Is similar to server-side FOR XML EXPLICIT mode.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="9ae68-125">Si especifica el modo AUTO y solicita la aplicación de formato XML del lado cliente, se envía la consulta completa al servidor, es decir, el formato XML se aplica en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9ae68-125">If you specify AUTO mode and request client-side XML formatting, the entire query is sent to the server; that is, XML formatting occurs on the server.</span></span> <span data-ttu-id="9ae68-126">Esto se hace así por comodidad, pero observe que el modo NESTED devuelve los nombres de tabla base como nombres de elemento en el documento XML que se genera.</span><span class="sxs-lookup"><span data-stu-id="9ae68-126">This is done for convenience, but note that the NESTED mode returns base table names as element names in the XML document that is generated.</span></span> <span data-ttu-id="9ae68-127">Algunas de las aplicaciones que escriba podrían requerir nombres de tabla base.</span><span class="sxs-lookup"><span data-stu-id="9ae68-127">Some of the applications you write might require base table names.</span></span> <span data-ttu-id="9ae68-128">Por ejemplo, podría ejecutar un procedimiento almacenado y cargar los datos resultantes en un conjunto de datos (en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework) y, más tarde, generar un DiffGram para actualizar los datos de las tablas.</span><span class="sxs-lookup"><span data-stu-id="9ae68-128">For example, you might execute a stored procedure and load the resulting data in a Dataset (in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework), and then later generate a DiffGram to update data in the tables.</span></span> <span data-ttu-id="9ae68-129">En ese caso, necesitaría la información de tabla base y tendría que usar el modo NESTED.</span><span class="sxs-lookup"><span data-stu-id="9ae68-129">In such a case, you would need the base table information and you would have to use the NESTED mode.</span></span>  
  
## <a name="benefits-of-client-side-xml-formatting"></a><span data-ttu-id="9ae68-130">Ventajas de la aplicación de formato XML en el cliente</span><span class="sxs-lookup"><span data-stu-id="9ae68-130">Benefits of Client-side XML formatting</span></span>  
 <span data-ttu-id="9ae68-131">A continuación, se muestran algunas de las ventajas de la aplicación de formato XML en el cliente.</span><span class="sxs-lookup"><span data-stu-id="9ae68-131">The following are some benefits of formatting XML on the client.</span></span>  
  
### <a name="if-you-have-stored-procedures-on-the-server-that-return-a-single-rowset-you-can-request-client-side-for-xml-transformation-to-generate-an-xml"></a><span data-ttu-id="9ae68-132">Si tiene procedimientos almacenados en el servidor que devuelven un único conjunto de filas, puede solicitar la transformación FOR XML del lado cliente para generar XML.</span><span class="sxs-lookup"><span data-stu-id="9ae68-132">If you have stored procedures on the server that return a single rowset, you can request client-side FOR XML transformation to generate an XML.</span></span>  
 <span data-ttu-id="9ae68-133">Por ejemplo, fíjese en el siguiente procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="9ae68-133">For example, consider the following stored procedure.</span></span> <span data-ttu-id="9ae68-134">Este procedimiento devuelve el nombre y los apellidos de los empleados de la tabla Person.Contact de la base de datos AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="9ae68-134">This procedure returns the first and last names of employees from the Person.Contact table in the AdventureWorks database:</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects  
   WHERE name = 'GetContacts' AND type = 'P')  
   DROP PROCEDURE GetContacts  
GO  
CREATE PROCEDURE GetContacts  
AS  
    SELECT   FirstName, LastName  
    FROM     Person.Contact  
```  
  
 <span data-ttu-id="9ae68-135">La siguiente plantilla XML de ejemplo ejecuta el procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="9ae68-135">The following sample XML template executes the stored procedure.</span></span> <span data-ttu-id="9ae68-136">La cláusula FOR XML se especifica después del nombre del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="9ae68-136">The FOR XML clause is specified after the stored procedure name.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    EXEC GetContacts FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="9ae68-137">Dado que el atributo **Client-Side-XML** se establece en 1 (true) en la plantilla, el procedimiento almacenado se ejecuta en el servidor y el conjunto de filas de dos columnas que devuelve el servidor se transforma en XML en el nivel intermedio y se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="9ae68-137">Because the **client-side-xml** attribute is set to 1 (true) in the template, the stored procedure is executed on the server and the two-column rowset that is returned by the server is transformed into XML on the middle tier and returned to the client.</span></span> <span data-ttu-id="9ae68-138">(Aquí solamente se muestra un resultado parcial.)</span><span class="sxs-lookup"><span data-stu-id="9ae68-138">(Only a partial result is shown here.)</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact FirstName="Catherine" LastName="Abel" />  
</ROOT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="9ae68-139">Si usa el proveedor SQLXMLOLEDB o clases administradas SQLXML, puede usar la propiedad `ClientSideXml` para solicitar la aplicación de formato XML del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="9ae68-139">When you are using the SQLXMLOLEDB Provider or SQLXML Managed Classes, you can use the `ClientSideXml` property to request client-side XML formatting.</span></span>  
  
### <a name="the-workload-is-more-balanced"></a><span data-ttu-id="9ae68-140">La carga de trabajo está más equilibrada.</span><span class="sxs-lookup"><span data-stu-id="9ae68-140">The workload is more balanced.</span></span>  
 <span data-ttu-id="9ae68-141">Dado que el cliente aplica el formato XML, la carga de trabajo se equilibra entre el servidor y cliente, dejando libre al servidor para que realice otras tareas.</span><span class="sxs-lookup"><span data-stu-id="9ae68-141">Because the client does the XML formatting, the workload is balanced between the server and client, freeing the server to do other things.</span></span>  
  
## <a name="supporting-client-side-xml-formatting"></a><span data-ttu-id="9ae68-142">Compatibilidad con el formato XML en el cliente</span><span class="sxs-lookup"><span data-stu-id="9ae68-142">Supporting Client-side XML Formatting</span></span>  
 <span data-ttu-id="9ae68-143">Para admitir la funcionalidad de formato XML del lado cliente, SQLXML proporciona:</span><span class="sxs-lookup"><span data-stu-id="9ae68-143">To support the client-side XML formatting functionality, SQLXML provides:</span></span>  
  
-   <span data-ttu-id="9ae68-144">proveedor SQLXMLOLEDB</span><span class="sxs-lookup"><span data-stu-id="9ae68-144">SQLXMLOLEDB Provider</span></span>  
  
-   <span data-ttu-id="9ae68-145">clases administradas de SQLXML</span><span class="sxs-lookup"><span data-stu-id="9ae68-145">SQLXML Managed Classes</span></span>  
  
-   <span data-ttu-id="9ae68-146">Compatibilidad mejorada con plantillas XML</span><span class="sxs-lookup"><span data-stu-id="9ae68-146">Enhanced XML template support</span></span>  
  
-   <span data-ttu-id="9ae68-147">Propiedad SqlXmlCommand. Clientsidexml,</span><span class="sxs-lookup"><span data-stu-id="9ae68-147">SqlXmlCommand.ClientSideXml property</span></span>  
  
     <span data-ttu-id="9ae68-148">Puede especificar el formato del lado cliente estableciendo esta propiedad de las clases administradas SQLXML en True.</span><span class="sxs-lookup"><span data-stu-id="9ae68-148">You can specify client-side formatting by setting this property of the SQLXML managed classes to true.</span></span>  
  
## <a name="enhanced-xml-template-support"></a><span data-ttu-id="9ae68-149">Compatibilidad mejorada con plantillas XML</span><span class="sxs-lookup"><span data-stu-id="9ae68-149">Enhanced XML Template Support</span></span>  
 <span data-ttu-id="9ae68-150">A partir de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] , la plantilla XML de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se ha mejorado con la adición del atributo **Client-Side-XML** .</span><span class="sxs-lookup"><span data-stu-id="9ae68-150">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], the XML template in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been enhanced with the addition of the **client-side-xml** attribute.</span></span> <span data-ttu-id="9ae68-151">Si este atributo está establecido en True, se aplica formato al XML en el cliente.</span><span class="sxs-lookup"><span data-stu-id="9ae68-151">If this attribute is set to true, XML is formatted on the client.</span></span> <span data-ttu-id="9ae68-152">Tenga en cuenta que este atributo de plantilla es idéntico en la funcionalidad de la propiedad Clientsidexml, específica del proveedor de SQLXMLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="9ae68-152">Note that this template attribute is identical in functionality to the SQLXMLOLEDB Provider-specific ClientSideXML property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ae68-153">Si ejecuta una plantilla XML en una aplicación ADO que usa el proveedor SQLXMLOLEDB y especifica el atributo **Client-Side-XML** en la plantilla y la propiedad Provider clientsidexml,, el valor especificado en la plantilla tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="9ae68-153">If you execute an XML template in an ADO application that is using the SQLXMLOLEDB Provider, and you specify both the **client-side-xml** attribute in the template and the provider ClientSideXML property, the value specified in the template takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ae68-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ae68-154">See Also</span></span>  
 <span data-ttu-id="9ae68-155">[Arquitectura del formato XML del lado cliente y del lado servidor &#40;SQLXML 4,0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="9ae68-155">[Architecture of Client-side and Server-side XML Formatting &#40;SQLXML 4.0&#41;](server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="9ae68-156">[SQL Server &#40;FOR XML&#41;](../../xml/for-xml-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9ae68-156">[FOR XML &#40;SQL Server&#41;](../../xml/for-xml-sql-server.md) </span></span>  
 <span data-ttu-id="9ae68-157">[Consideraciones de seguridad de FOR XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="9ae68-157">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="9ae68-158">[Compatibilidad con tipos de datos XML en SQLXML 4,0](../xml-data-type-support-in-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="9ae68-158">[xml Data Type Support in SQLXML 4.0](../xml-data-type-support-in-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="9ae68-159">[Clases administradas de SQLXML](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="9ae68-159">[SQLXML Managed Classes](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 <span data-ttu-id="9ae68-160">[Formato XML del lado cliente y de servidor &#40;SQLXML 4,0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="9ae68-160">[Client-side vs. Server-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-vs-server-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="9ae68-161">[Objeto SqlXmlCommand &#40;clases administradas de SQLXML&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span><span class="sxs-lookup"><span data-stu-id="9ae68-161">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/net-framework-classes/sqlxml-managed-classes-sqlxmlcommand-object.md) </span></span>  
 [<span data-ttu-id="9ae68-162">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9ae68-162">XML Data &#40;SQL Server&#41;</span></span>](../../xml/xml-data-sql-server.md)  
  
  
