---
title: Generar un esquema XSD insertado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- XMLSCHEMA option
- schemas [SQL Server], XML
- XDR schemas
- FOR XML clause, inline XSD schema generation
- inline XSD schema generation [SQL Server]
- XMLDATA option
ms.assetid: 04b35145-1cca-45f4-9eb7-990abf2e647d
author: rothja
ms.author: jroth
ms.openlocfilehash: 2af748d4fc6ae67f57568be58ec7f59876098f52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751970"
---
# <a name="generate-an-inline-xsd-schema"></a><span data-ttu-id="b157d-102">Generar un esquema XSD insertado</span><span class="sxs-lookup"><span data-stu-id="b157d-102">Generate an Inline XSD Schema</span></span>
  <span data-ttu-id="b157d-103">En una cláusula FOR XML, se puede solicitar que una consulta devuelva un esquema insertado con los resultados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b157d-103">In a FOR XML clause, you can request that your query return an inline schema together with the query results.</span></span> <span data-ttu-id="b157d-104">Si se desea un esquema XDR, se utiliza la palabra clave XMLDATA en la cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="b157d-104">If you want an XDR schema, you use the XMLDATA keyword in the FOR XML clause.</span></span> <span data-ttu-id="b157d-105">Si se desea un esquema XSD, se utiliza la palabra clave XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="b157d-105">If you want an XSD schema, you use the XMLSCHEMA keyword.</span></span>  
  
 <span data-ttu-id="b157d-106">En este tema se describe la palabra clave XMLSCHEMA y se explica la estructura del esquema XSD insertado resultante.</span><span class="sxs-lookup"><span data-stu-id="b157d-106">This topic describes the XMLSCHEMA keyword and explains the structure of the resulting inline XSD schema.</span></span> <span data-ttu-id="b157d-107">A continuación se indican las limitaciones que existen al solicitar esquemas insertados:</span><span class="sxs-lookup"><span data-stu-id="b157d-107">Following are the limitations when you are requesting inline schemas:</span></span>  
  
-   <span data-ttu-id="b157d-108">XMLSCHEMA solo se puede especificar en los modos RAW y AUTO, no en el modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="b157d-108">You can specify XMLSCHEMA only in RAW and AUTO mode, not in EXPLICIT mode.</span></span>  
  
-   <span data-ttu-id="b157d-109">Si una consulta FOR XML anidada especifica la directiva TYPE, el resultado de la consulta es de tipo `xml` se trata como una instancia de datos XML sin tipo.</span><span class="sxs-lookup"><span data-stu-id="b157d-109">If a nested FOR XML query specifies the TYPE directive, the query result is of `xml` type, and this result is treated as an instance of untyped XML data.</span></span> <span data-ttu-id="b157d-110">Para obtener más información, vea [Datos XML &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b157d-110">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="b157d-111">Cuando se especifica XMLSCHEMA en una consulta FOR XML, se reciben un esquema y datos XML, el resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="b157d-111">When you specify XMLSCHEMA in a FOR XML query, you receive both a schema and XML data, the query result.</span></span> <span data-ttu-id="b157d-112">Cada elemento de nivel superior de los datos hace referencia al esquema anterior por medio de una declaración de espacio de nombres predeterminado que, a su vez, hace referencia al espacio de nombres de destino del esquema insertado.</span><span class="sxs-lookup"><span data-stu-id="b157d-112">Each top-level element of the data refers to the previous schema by using a default namespace declaration that, in turn, refers to the target namespace of the inline schema.</span></span>  
  
 <span data-ttu-id="b157d-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b157d-113">For example:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks2012].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<Production.ProductModel xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="1" Name="Classic Vest" />  
```  
  
 <span data-ttu-id="b157d-114">Se obtienen el esquema XML y el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="b157d-114">The result includes XML schema and the XML result.</span></span> <span data-ttu-id="b157d-115">El elemento de nivel superior <`ProductModel`> del resultado hace referencia al esquema a través de la declaración del espacio de nombres predeterminado, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" .</span><span class="sxs-lookup"><span data-stu-id="b157d-115">The <`ProductModel`> top-level element in the result refers to the schema by using the default namespace declaration, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" .</span></span>  
  
 <span data-ttu-id="b157d-116">La parte del resultado que corresponde al esquema puede contener varios documentos de esquema, que describen varios espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="b157d-116">The schema part of the result may contain multiple schema documents that describe multiple namespaces.</span></span> <span data-ttu-id="b157d-117">Como mínimo se devuelven los dos documentos de esquema siguientes:</span><span class="sxs-lookup"><span data-stu-id="b157d-117">At a minimum, the following two schema documents are returned:</span></span>  
  
-   <span data-ttu-id="b157d-118">Un documento de esquema para el espacio de nombres **Sqltypes** , para el que se devuelven los tipos SQL base.</span><span class="sxs-lookup"><span data-stu-id="b157d-118">One schema document for the **Sqltypes** namespace, and for which the base SQL types are being returned.</span></span>  
  
-   <span data-ttu-id="b157d-119">Otro documento de esquema que describe la forma del resultado de la consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="b157d-119">Another schema document that describes the shape of the FOR XML query result.</span></span>  
  
 <span data-ttu-id="b157d-120">Asimismo, si se incluyen tipos de datos `xml` con tipo en el resultado de la consulta, se incluyen los esquemas asociados a esos tipos de datos `xml` con tipo.</span><span class="sxs-lookup"><span data-stu-id="b157d-120">Also, if any typed `xml` data types are included in the query result, the schemas associated with those typed `xml` data types are included.</span></span>  
  
 <span data-ttu-id="b157d-121">El espacio de nombres de destino del documento de esquema que describe la forma del resultado de la consulta FOR XML contiene una parte fija y una parte numérica que se incrementa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b157d-121">The target namespace of the schema document that describes the shape of the FOR XML result contains a fixed portion and a numeric portion that increments automatically.</span></span> <span data-ttu-id="b157d-122">El formato de este espacio de nombres se muestra a continuación, siendo *n* un entero positivo.</span><span class="sxs-lookup"><span data-stu-id="b157d-122">The format of this namespace is shown in the following where *n* is a positive integer.</span></span> <span data-ttu-id="b157d-123">Por ejemplo, en la consulta anterior, urn:schemas-microsoft-com:sql:SqlRowSet1 es el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="b157d-123">For example, in the previous query, urn:schemas-microsoft-com:sql:SqlRowSet1 is the target namespace.</span></span>  
  
```  
urn:schemas-microsoft-com:sql:SqlRowSetn  
```  
  
 <span data-ttu-id="b157d-124">Es posible que no se desee el cambio de espacios de nombres de destino que se produce en el resultado obtenido entre una ejecución y otra.</span><span class="sxs-lookup"><span data-stu-id="b157d-124">The change in the target namespaces in the result that occurred from one execution to another may not be desirable.</span></span> <span data-ttu-id="b157d-125">Por ejemplo, si se consulta el XML resultante, el cambio del espacio de nombres de destino hará que sea necesario actualizar la consulta.</span><span class="sxs-lookup"><span data-stu-id="b157d-125">For example, if you query the resulting XML, the change in target namespace will require that you update your query.</span></span> <span data-ttu-id="b157d-126">Existe la posibilidad de especificar un espacio de nombres de destino cuando se agrega la opción XMLSCHEMA en la cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="b157d-126">You can optionally specify a target namespace when the XMLSCHEMA option is added in the FOR XML clause.</span></span> <span data-ttu-id="b157d-127">En ese caso, el XML resultante incluiría el espacio de nombres suministrado, que permanecería invariable con independencia de las veces que se ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="b157d-127">The resulting XML will include the namespace you provided and will remain the same, regardless of how many times you run the query.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM   Production.ProductModel  
WHERE ProductModelID=1  
FOR XML AUTO, XMLSCHEMA ('MyURI')  
```  
  
## <a name="entity-elements"></a><span data-ttu-id="b157d-128">Elementos de entidad</span><span class="sxs-lookup"><span data-stu-id="b157d-128">Entity Elements</span></span>  
 <span data-ttu-id="b157d-129">Para explicar los detalles de la estructura del esquema XSD generado para el resultado de la consulta, primero es necesario describir el elemento de entidad.</span><span class="sxs-lookup"><span data-stu-id="b157d-129">In order to discuss the details of the XSD schema structure generated for the query result, the entity element has to first be described</span></span>  
  
 <span data-ttu-id="b157d-130">Un elemento de entidad de los datos XML devueltos por una consulta FOR XML es un elemento que se genera a partir de una tabla, no a partir de una columna.</span><span class="sxs-lookup"><span data-stu-id="b157d-130">An entity element in the XML data returned by FOR XML query is an element that is generated from a table and not from a column.</span></span> <span data-ttu-id="b157d-131">Por ejemplo, la siguiente consulta FOR XML devuelve información de contacto de la tabla `Person` de la base de datos `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="b157d-131">For example, the following FOR XML query returns contact information from the `Person` table in the `AdventureWorks2012` database.</span></span>  
  
```  
SELECT BusinessEntityID, FirstName  
FROM Person.Person  
WHERE BusinessEntityID = 1  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="b157d-132">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b157d-132">This is the result:</span></span>  
  
 `<Person>`  
  
 `<BusinessEntityID>1</BusinessEntityID>`  
  
 `<FirstName>Ken</FirstName>`  
  
 `</Person>`  
  
 <span data-ttu-id="b157d-133">En este resultado, <`Person`> es el elemento de entidad.</span><span class="sxs-lookup"><span data-stu-id="b157d-133">In this result, <`Person`> is the entity element.</span></span> <span data-ttu-id="b157d-134">En el resultado XML puede haber varios elementos de entidad, cada uno de los cuales tiene una declaración global en el esquema XSD insertado.</span><span class="sxs-lookup"><span data-stu-id="b157d-134">There can be multiple entity elements in the XML result and each of these has a global declaration in the inline XSD schema.</span></span> <span data-ttu-id="b157d-135">Por ejemplo, la consulta siguiente recupera la información de encabezado y los detalles de un pedido de venta específico.</span><span class="sxs-lookup"><span data-stu-id="b157d-135">For example, the following query retrieves sales order header and detail information for a specific order.</span></span>  
  
```  
SELECT  SalesOrderHeader.SalesOrderID, ProductID, OrderQty  
FROM    Sales.SalesOrderHeader, Sales.SalesOrderDetail  
WHERE   SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
AND     SalesOrderHeader.SalesOrderID=5001  
FOR XML AUTO, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="b157d-136">Dado que en la consulta se especifica la directiva ELEMENTS, el XML resultante está centrado en elementos.</span><span class="sxs-lookup"><span data-stu-id="b157d-136">Because the query specifies the ELEMENTS directive, the resulting XML is element-centric.</span></span> <span data-ttu-id="b157d-137">La consulta especifica también la directiva XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="b157d-137">The query also specifies the XMLSCHEMA directive.</span></span> <span data-ttu-id="b157d-138">Por lo tanto, se devuelve un esquema XSD insertado.</span><span class="sxs-lookup"><span data-stu-id="b157d-138">Therefore, an inline XSD schema is returned.</span></span> <span data-ttu-id="b157d-139">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b157d-139">This is the result:</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="Sales.SalesOrderHeader">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="SalesOrderID" type="sqltypes:int" />`  
  
 `<xsd:element ref="schema:Sales.SalesOrderDetail" minOccurs="0" maxOccurs="unbounded" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `<xsd:element name="Sales.SalesOrderDetail">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="OrderQty" type="sqltypes:smallint" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 <span data-ttu-id="b157d-140">Observe lo siguiente en la consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="b157d-140">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="b157d-141">En el resultado, <`SalesOrderHeader`> y <`SalesOrderDetail`> son elementos de entidad.</span><span class="sxs-lookup"><span data-stu-id="b157d-141">In the result, <`SalesOrderHeader`> and <`SalesOrderDetail`> are entity elements.</span></span> <span data-ttu-id="b157d-142">Por este motivo, se declaran de manera global en el esquema.</span><span class="sxs-lookup"><span data-stu-id="b157d-142">Because of this, they are globally declared in the schema.</span></span> <span data-ttu-id="b157d-143">Dicho de otro modo, la declaración aparece en el nivel superior dentro del elemento <`Schema`>.</span><span class="sxs-lookup"><span data-stu-id="b157d-143">That is, the declaration appears at the top level inside the <`Schema`> element.</span></span>  
  
-   <span data-ttu-id="b157d-144"><`SalesOrderID`>, <`ProductID`> y <`OrderQty`> no son elementos de entidad porque se asignan a columnas.</span><span class="sxs-lookup"><span data-stu-id="b157d-144">The <`SalesOrderID`>, <`ProductID`>, and <`OrderQty`> are not entity elements, because they map to columns.</span></span> <span data-ttu-id="b157d-145">Los datos de columna se devuelven como elementos en el XML, debido a la directiva ELEMENTS.</span><span class="sxs-lookup"><span data-stu-id="b157d-145">The column data is returned as elements in the XML, because of the ELEMENTS directive.</span></span> <span data-ttu-id="b157d-146">Éstos se asignan a elementos locales del tipo complejo del elemento de entidad.</span><span class="sxs-lookup"><span data-stu-id="b157d-146">These are mapped to local elements of the entity element's complex type.</span></span> <span data-ttu-id="b157d-147">Observe que, si no se especifica la directiva ELEMENTS, los valores `SalesOrderID`, `ProductID` y `OrderQty` se asignan a los atributos locales del tipo complejo del elemento de entidad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b157d-147">Note that if the ELEMENTS directive is not specified, the `SalesOrderID`, `ProductID` and `OrderQty` values are mapped to local attributes of the corresponding entity element's complex type.</span></span>  
  
## <a name="attribute-name-clashes"></a><span data-ttu-id="b157d-148">Conflictos de nombres de atributos</span><span class="sxs-lookup"><span data-stu-id="b157d-148">Attribute Name Clashes</span></span>  
 <span data-ttu-id="b157d-149">Lo descrito a continuación se basa en las tablas `CustOrder` y `CustOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="b157d-149">The following discussion is based on the `CustOrder` and `CustOrderDetail` tables.</span></span> <span data-ttu-id="b157d-150">Para probar los ejemplos siguientes, cree estas tablas y agregue sus propios datos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b157d-150">To test the following samples, create these tables and add your own sample data:</span></span>  
  
```  
CREATE TABLE CustOrder (OrderID int primary key, CustomerID int)  
GO  
CREATE TABLE CustOrderDetail (OrderID int, ProductID int, Qty int)  
GO  
```  
  
 <span data-ttu-id="b157d-151">En FOR XML, a veces se utiliza el mismo nombre para indicar diferentes propiedades, atributos.</span><span class="sxs-lookup"><span data-stu-id="b157d-151">In FOR XML, the same name is sometimes used to indicate different properties, attributes.</span></span> <span data-ttu-id="b157d-152">Por ejemplo, la siguiente consulta en modo RAW centrada en atributos genera dos atributos con el mismo nombre, OrderID.</span><span class="sxs-lookup"><span data-stu-id="b157d-152">For example, the following attribute-centric RAW mode query generates two attributes that have the same name, OrderID.</span></span> <span data-ttu-id="b157d-153">Esto genera un error.</span><span class="sxs-lookup"><span data-stu-id="b157d-153">This generates an error.</span></span>  
  
```  
SELECT CustOrder.OrderID,   
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
FROM   dbo.CustOrder, dbo.CustOrderDetail  
WHERE  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA  
```  
  
 <span data-ttu-id="b157d-154">Sin embargo, como es aceptable que dos elementos tengan el mismo nombre, el problema desaparece al agregar la directiva ELEMENTS:</span><span class="sxs-lookup"><span data-stu-id="b157d-154">However, because it is acceptable to have two elements that have the same name, you can eliminate the problem by adding the ELEMENTS directive:</span></span>  
  
```  
SELECT CustOrder.OrderID,  
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
from   dbo.CustOrder, dbo.CustOrderDetail  
where  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA, ELEMENTS  
```  
  
 <span data-ttu-id="b157d-155">Éste es el resultado.</span><span class="sxs-lookup"><span data-stu-id="b157d-155">This is the result.</span></span> <span data-ttu-id="b157d-156">Observe que en el esquema XSD insertado, el elemento OrderID se define dos veces.</span><span class="sxs-lookup"><span data-stu-id="b157d-156">Note in the inline XSD schema, the OrderID element is defined two times.</span></span> <span data-ttu-id="b157d-157">En una de las declaraciones, minOccurs se establece en 0, que se corresponde con el valor de OrderID en la tabla CustOrderDetail, y en la segunda se asigna a la columna de clave principal OrderID de la tabla `CustOrder` , donde minOccurs es 1 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b157d-157">One of the declarations has minOccurs set to 0, corresponding to the OrderID from the CustOrderDetail table, and the second one maps to the OrderID primary key column of the `CustOrder` table where minOccurs is 1 by default.</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" />`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" minOccurs="0" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
## <a name="element-name-clashes"></a><span data-ttu-id="b157d-158">Conflictos de nombres de elementos</span><span class="sxs-lookup"><span data-stu-id="b157d-158">Element Name Clashes</span></span>  
 <span data-ttu-id="b157d-159">En FOR XML se puede utilizar el mismo nombre para indicar dos subelementos.</span><span class="sxs-lookup"><span data-stu-id="b157d-159">In FOR XML, the same name can be used to indicate two subelements.</span></span> <span data-ttu-id="b157d-160">Por ejemplo, la consulta siguiente recupera los valores de ListPrice y DealerPrice de los productos, pero la consulta especifica el mismo alias, Price, para estas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="b157d-160">For example, the following query retrieves ListPrice and DealerPrice values of products, but the query specifies the same alias, Price, for these two columns.</span></span> <span data-ttu-id="b157d-161">Por tanto, el conjunto de resultados obtenido tiene dos columnas con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="b157d-161">Therefore, the resulting rowset will have two columns with same name.</span></span>  
  
### <a name="case-1-both-subelements-are-nonkey-columns-of-the-same-type-and-can-be-null"></a><span data-ttu-id="b157d-162">Caso 1: ambos subelementos son columnas sin clave, son del mismo tipo y pueden ser NULL</span><span class="sxs-lookup"><span data-stu-id="b157d-162">Case 1: Both subelements are nonkey columns of the same type and can be NULL</span></span>  
 <span data-ttu-id="b157d-163">En la consulta siguiente, ambos subelementos son columnas sin clave, son del mismo tipo y pueden ser NULL.</span><span class="sxs-lookup"><span data-stu-id="b157d-163">In the following query, both subelements are nonkey columns of the same type and can be NULL.</span></span>  
  
```  
DROP TABLE T  
go  
CREATE TABLE T (ProductID int primary key, ListPrice money, DealerPrice money)  
go  
INSERT INTO T values (1, 1.25, null)  
go  
  
SELECT ProductID, ListPrice Price, DealerPrice Price  
FROM   T  
for    XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="b157d-164">Éste es el XML correspondiente que se genera.</span><span class="sxs-lookup"><span data-stu-id="b157d-164">This is the corresponding XML generated.</span></span> <span data-ttu-id="b157d-165">Solo se muestra una parte del XSD insertado:</span><span class="sxs-lookup"><span data-stu-id="b157d-165">Only a fraction of the inline XSD is shown:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" minOccurs="0" maxOccurs="2" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `</row>`  
  
 <span data-ttu-id="b157d-166">Tenga en cuenta lo siguiente en el esquema XSD insertado:</span><span class="sxs-lookup"><span data-stu-id="b157d-166">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="b157d-167">Tanto ListPrice como DealerPrice son del mismo tipo, `money`, y ambos pueden ser NULL en la tabla.</span><span class="sxs-lookup"><span data-stu-id="b157d-167">Both the ListPrice and DealerPrice are of the same type, `money`, and both can be NULL in the table.</span></span> <span data-ttu-id="b157d-168">Por tanto, como es posible que no se devuelvan en el XML resultante, solo hay un único elemento secundario <`Price`> en la declaración de tipo complejo del elemento <`row`> con minOccurs=0 y maxOccurs=2.</span><span class="sxs-lookup"><span data-stu-id="b157d-168">Therefore, because they may not be returned in the resulting XML, there is only one <`Price`> child element in the complex type declaration of the <`row`> element that has minOccurs=0 and maxOccurs=2.</span></span>  
  
-   <span data-ttu-id="b157d-169">En el resultado, como el valor de `DealerPrice` es NULL en la tabla, solo se devuelve `ListPrice` como elemento <`Price`>.</span><span class="sxs-lookup"><span data-stu-id="b157d-169">In the result, because the `DealerPrice` value is NULL in the table, only `ListPrice` is returned as a <`Price`> element.</span></span> <span data-ttu-id="b157d-170">Si se agrega el parámetro `XSINIL` a la directiva ELEMENTS, se recibirán los dos elementos que tienen el valor `xsi:nil` establecido en TRUE para el elemento <`Price`> que corresponde a DealerPrice.</span><span class="sxs-lookup"><span data-stu-id="b157d-170">If you add the `XSINIL` parameter to the ELEMENTS directive, you will receive both of the elements that have the `xsi:nil` value set to TRUE for the<`Price`> element that corresponds to DealerPrice.</span></span> <span data-ttu-id="b157d-171">También se recibirán dos elementos secundarios <`Price`> en la definición de tipo complejo del elemento <`row`> del esquema XSD insertado, con el atributo `nillable` establecido en TRUE para ambos.</span><span class="sxs-lookup"><span data-stu-id="b157d-171">You will also receive two <`Price`> child elements in the <`row`> complex type definition in the inline XSD schema with the `nillable` attribute set to TRUE for both.</span></span> <span data-ttu-id="b157d-172">Este fragmento es un resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="b157d-172">This fragment is a partial result:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `<Price xsi:nil="true" />`  
  
 `</row>`  
  
### <a name="case-2-one-key-and-one-nonkey-column-of-the-same-type"></a><span data-ttu-id="b157d-173">Caso 2: una columna de clave y una columna sin clave del mismo tipo</span><span class="sxs-lookup"><span data-stu-id="b157d-173">Case 2: One key and one nonkey column of the same type</span></span>  
 <span data-ttu-id="b157d-174">La siguiente consulta ilustra una columna de clave y una columna sin clave del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="b157d-174">The following query illustrates one key and one nonkey column of the same type.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 int, Col3 nvarchar(20))  
go  
INSERT INTO T VALUES (1, 1, 'test')  
go   
```  
  
 <span data-ttu-id="b157d-175">La siguiente consulta en la tabla **T** especifica el mismo alias para Col1 y Col2, donde Col1 es una clave primaria y no puede ser NULL, y Col2 puede ser NULL.</span><span class="sxs-lookup"><span data-stu-id="b157d-175">The following query against table **T** specifies the same alias for Col1 and Col2, where Col1 is a primary key and cannot be null, and Col2 can be null.</span></span> <span data-ttu-id="b157d-176">Se generan dos elementos del mismo nivel que son elementos secundarios del elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="b157d-176">This generates two sibling elements that are children of the <`row`> element.</span></span>  
  
```  
SELECT Col1 as Col, Col2 as Col, Col3  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="b157d-177">Éste es el resultado.</span><span class="sxs-lookup"><span data-stu-id="b157d-177">This is the result.</span></span> <span data-ttu-id="b157d-178">Solo se muestra un fragmento del esquema XSD insertado.</span><span class="sxs-lookup"><span data-stu-id="b157d-178">Only a fragment of the inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="Col3" minOccurs="0">`  
  
 `<xsd:simpleType>`  
  
 `<xsd:restriction base="sqltypes:nvarchar"`  
  
 `sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth"`  
  
 `sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `</xsd:element>`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col>1</Col>`  
  
 `<Col>1</Col>`  
  
 `<Col3>test</Col3>`  
  
 `</row>`  
  
 <span data-ttu-id="b157d-179">Observe que, en el esquema XSD insertado, el elemento <`Col`> que se corresponde con Col2 tiene minOccurs establecido en 0.</span><span class="sxs-lookup"><span data-stu-id="b157d-179">Note in the inline XSD schema that the <`Col`> element corresponding to the Col2 has minOccurs set to 0.</span></span>  
  
### <a name="case-3-both-elements-of-different-types-and-corresponding-columns-can-be-null"></a><span data-ttu-id="b157d-180">Caso 3: los dos elementos son de tipos diferentes y las columnas correspondientes pueden ser NULL</span><span class="sxs-lookup"><span data-stu-id="b157d-180">Case 3: Both elements of different types and corresponding columns can be NULL</span></span>  
 <span data-ttu-id="b157d-181">La consulta siguiente se especifica utilizando la tabla de ejemplo mostrada en el caso 2:</span><span class="sxs-lookup"><span data-stu-id="b157d-181">The following query is specified against the sample table shown in case 2:</span></span>  
  
```  
SELECT Col1, Col2 as Col, Col3 as Col  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="b157d-182">En la consulta siguiente, se asignan los mismos alias a Col2 y Col3.</span><span class="sxs-lookup"><span data-stu-id="b157d-182">In the following query, Col2 and Col3 are given the same aliases.</span></span> <span data-ttu-id="b157d-183">De esta forma se generan dos elementos del mismo nivel, que tienen el mismo nombre y que son elementos secundarios del elemento <`raw`> del resultado.</span><span class="sxs-lookup"><span data-stu-id="b157d-183">This generates two sibling elements that have the same name and that are both children of the <`raw`> element in the result.</span></span> <span data-ttu-id="b157d-184">Las dos columnas son de tipos diferentes y pueden ser NULL.</span><span class="sxs-lookup"><span data-stu-id="b157d-184">Both of these columns are of different types and both can be NULL.</span></span> <span data-ttu-id="b157d-185">Éste es el resultado.</span><span class="sxs-lookup"><span data-stu-id="b157d-185">This is the result.</span></span> <span data-ttu-id="b157d-186">Solo se muestra una parte del esquema XSD insertado.</span><span class="sxs-lookup"><span data-stu-id="b157d-186">Only partial inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:simpleType name="Col1">`  
  
 `<xsd:restriction base="sqltypes:int" />`  
  
 `</xsd:simpleType>`  
  
 `<xsd:simpleType name="Col2">`  
  
 `<xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col1" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" minOccurs="0" maxOccurs="2" type="xsd:anySimpleType" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col1>1</Col1>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col1">1</Col>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col2">test</Col>`  
  
 `</row>`  
  
 <span data-ttu-id="b157d-187">Tenga en cuenta lo siguiente en el esquema XSD insertado:</span><span class="sxs-lookup"><span data-stu-id="b157d-187">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="b157d-188">Dado que Col2 y Col3 pueden ser NULL, la declaración del elemento <`Col`> especifica minOccurs como 0 y maxOccurs como 2.</span><span class="sxs-lookup"><span data-stu-id="b157d-188">Because both Col2 and Col3 can be NULL, the <`Col`> element declaration specifies the minOccurs as 0 and maxOccurs as 2.</span></span>  
  
-   <span data-ttu-id="b157d-189">Como los dos elementos <`Col`> están en el mismo nivel, hay una sola declaración de elemento en el esquema.</span><span class="sxs-lookup"><span data-stu-id="b157d-189">Because both the <`Col`> elements are siblings, there is one element declaration in the schema.</span></span> <span data-ttu-id="b157d-190">Por otra parte, como los dos elementos son de tipos simples, aunque diferentes, el tipo del elemento es `xsd:anySimpleType`en el esquema.</span><span class="sxs-lookup"><span data-stu-id="b157d-190">Also, because both of the elements are also of different types, though both are simple types, the type of the element in the schema is `xsd:anySimpleType`.</span></span> <span data-ttu-id="b157d-191">En el resultado, cada tipo de instancia se identifica mediante el atributo `xsi:type` .</span><span class="sxs-lookup"><span data-stu-id="b157d-191">In the result, each instance type is identified by the `xsi:type` attribute.</span></span>  
  
-   <span data-ttu-id="b157d-192">En el resultado, cada instancia del elemento <`Col`> hace referencia a su tipo de instancia por medio del atributo `xsi:type`.</span><span class="sxs-lookup"><span data-stu-id="b157d-192">In the result, every instance of the <`Col`> element refers to its instance type by using the `xsi:type` attribute.</span></span>  
  
  
