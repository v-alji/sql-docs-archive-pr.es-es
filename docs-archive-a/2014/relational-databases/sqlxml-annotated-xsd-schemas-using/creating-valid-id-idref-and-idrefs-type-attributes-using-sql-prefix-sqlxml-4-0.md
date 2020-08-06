---
title: 'Crear atributos válidos de tipo ID, IDREF e IDREFS mediante SQL: prefix (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- annotated XSD schemas, ID type attribute
- IDREF type attribute [SQLXML]
- annotated XSD schemas, IDREFS type attribute
- ID type attribute [SQLXML]
- sql:prefix
- prefix annotation
- IDREF relationships [SQLXML]
- IDREFS type attribute [SQLXML]
- annotated XSD schemas, IDREF type attribute
- ID relationships [SQLXML]
ms.assetid: 1c7f77d3-81f3-4820-bb63-c4aaa4ea9aa1
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9e63bebd0cebbfeed75ea5cbe2ea62683234fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672897"
---
# <a name="creating-valid-id-idref-and-idrefs-type-attributes-using-sqlprefix-sqlxml-40"></a><span data-ttu-id="4baeb-102">Crear atributos válidos de tipo ID, IDREF e IDREFS mediante sql:prefix (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4baeb-102">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix (SQLXML 4.0)</span></span>
  <span data-ttu-id="4baeb-103">Es posible especificar que un atributo sea un atributo de tipo ID.</span><span class="sxs-lookup"><span data-stu-id="4baeb-103">An attribute can be specified to be an ID type attribute.</span></span> <span data-ttu-id="4baeb-104">Los atributos especificados como IDREF o IDREFS pueden usarse para hacer referencia a los atributos de tipo ID, lo que habilita los vínculos entre documentos.</span><span class="sxs-lookup"><span data-stu-id="4baeb-104">Attributes specified as IDREF or IDREFS can then be used to refer to the ID type attributes, enabling links between documents.</span></span>  
  
 <span data-ttu-id="4baeb-105">ID, IDREF e IDREFS corresponden a relaciones PK/FK (clave principal/clave externa) de la base de datos, con algunas diferencias.</span><span class="sxs-lookup"><span data-stu-id="4baeb-105">ID, IDREF, and IDREFS correspond to PK/FK (primary key/foreign key) relationships in the database, with few differences.</span></span> <span data-ttu-id="4baeb-106">En un documento XML, los valores de los atributos de tipo ID deben ser distintos.</span><span class="sxs-lookup"><span data-stu-id="4baeb-106">In an XML document, the values of ID type attributes must be distinct.</span></span> <span data-ttu-id="4baeb-107">Si los atributos **CustomerID** y **OrderID** se especifican como tipo de identificador en un documento XML, estos valores deben ser distintos.</span><span class="sxs-lookup"><span data-stu-id="4baeb-107">If **CustomerID** and **OrderID** attributes are specified as ID type in an XML document, these values must be distinct.</span></span> <span data-ttu-id="4baeb-108">Sin embargo, en una base de datos, las columnas CustomerID y OrderID pueden tener los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="4baeb-108">However, in a database, CustomerID and OrderID columns can have the same values.</span></span> <span data-ttu-id="4baeb-109">(Por ejemplo, CustomerID = 1 y OrderID = 1 sería válido en la base de datos).</span><span class="sxs-lookup"><span data-stu-id="4baeb-109">(For example, CustomerID = 1 and OrderID = 1 are valid in the database).</span></span>  
  
 <span data-ttu-id="4baeb-110">Para que los atributos ID, IDREFS e IDREF sean válidos:</span><span class="sxs-lookup"><span data-stu-id="4baeb-110">For the ID, IDREF, and IDREFS attributes to be valid:</span></span>  
  
-   <span data-ttu-id="4baeb-111">El valor de ID debe ser único dentro del documento XML.</span><span class="sxs-lookup"><span data-stu-id="4baeb-111">The value of ID must be unique within the XML document.</span></span>  
  
-   <span data-ttu-id="4baeb-112">Para cada atributo IDREF e IDREFS, los valores de ID a los que se haga referencia deben estar en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="4baeb-112">For every IDREF and IDREFS, the referenced ID values must be in the XML document.</span></span>  
  
-   <span data-ttu-id="4baeb-113">El valor de un atributo ID, IDREF e IDREFS debe ser un token con nombre.</span><span class="sxs-lookup"><span data-stu-id="4baeb-113">The value of an ID, IDREF, and IDREFS must be a named token.</span></span> <span data-ttu-id="4baeb-114">(Por ejemplo, el valor entero 101 no puede ser un valor ID.)</span><span class="sxs-lookup"><span data-stu-id="4baeb-114">(For example, the integer value 101 cannot be an ID value.)</span></span>  
  
-   <span data-ttu-id="4baeb-115">Los atributos de tipo ID, IDREF e IDREFS no se pueden asignar a columnas del tipo `text` , `ntext` , o a `image` cualquier otro tipo de datos binarios (por ejemplo, `timestamp` ).</span><span class="sxs-lookup"><span data-stu-id="4baeb-115">The attributes of ID, IDREF, and IDREFS type cannot be mapped to columns of the type `text`, `ntext`, or `image` or any other binary data type (for example, `timestamp`).</span></span>  
  
 <span data-ttu-id="4baeb-116">Si un documento XML contiene varios atributos de tipo ID, use la anotación `sql:prefix` para asegurarse de que los valores sean únicos.</span><span class="sxs-lookup"><span data-stu-id="4baeb-116">If an XML document contains multiple IDs, use the `sql:prefix` annotation to ensure that the values are unique.</span></span>  
  
 <span data-ttu-id="4baeb-117">Tenga en cuenta que la anotación `sql:prefix` no puede usarse con un atributo XSD fijo.</span><span class="sxs-lookup"><span data-stu-id="4baeb-117">Note that `sql:prefix` annotation cannot be used with XSD fixed attribute.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4baeb-118">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4baeb-118">Examples</span></span>  
 <span data-ttu-id="4baeb-119">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="4baeb-119">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="4baeb-120">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="4baeb-120">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-id-and-idrefs-types"></a><span data-ttu-id="4baeb-121">A.</span><span class="sxs-lookup"><span data-stu-id="4baeb-121">A.</span></span> <span data-ttu-id="4baeb-122">Especificar tipos ID e IDREFS</span><span class="sxs-lookup"><span data-stu-id="4baeb-122">Specifying ID and IDREFS types</span></span>  
 <span data-ttu-id="4baeb-123">En el esquema siguiente, el **\<Customer>** elemento está compuesto del **\<Order>** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="4baeb-123">In the following schema, the **\<Customer>** element consists of the **\<Order>** child element.</span></span> <span data-ttu-id="4baeb-124">El **\<Order>** elemento también tiene un elemento secundario, el **\<OrderDetail>** elemento.</span><span class="sxs-lookup"><span data-stu-id="4baeb-124">The **\<Order>** element also has a child element, the **\<OrderDetail>** element.</span></span>  
  
 <span data-ttu-id="4baeb-125">El atributo **atributo OrderIDList** de **\<Customer>** es un atributo de tipo IDREFS que hace referencia al atributo **OrderID** del **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="4baeb-125">The **OrderIDList** attribute of **\<Customer>** is an IDREFS type attribute that refers to the **OrderID** attribute of the **\<Order>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
                 parent="Sales.Customer"  
                 parent-key="CustomerID"  
                 child="Sales.SalesOrderHeader"  
                 child-key="CustomerID" />  
    <sql:relationship name="OrderOrderDetail"  
                 parent="Sales.SalesOrderHeader"  
                 parent-key="SalesOrderID"  
                 child="Sales.SalesOrderDetail"  
                 child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"    
               sql:relationship="CustOrders" maxOccurs="unbounded" >  
          <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OrderDetail"   
                             sql:relation="Sales.SalesOrderDetail"   
                   sql:relationship="OrderOrderDetail"   
                   maxOccurs="unbounded" >  
                  <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="ProductID" type="xsd:string" />  
                   <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  </xsd:complexType>  
               </xsd:element>  
             </xsd:sequence>  
             <xsd:attribute name="SalesOrderID"   
                            type="xsd:ID" sql:prefix="ord-" />  
             <xsd:attribute name="OrderDate" type="xsd:date" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CustomerID" type="xsd:string" />  
    <xsd:attribute name="OrderIDList" type="xsd:IDREFS"   
                   sql:relation="Sales.SalesOrderHeader" sql:field="SalesOrderID"  
                   sql:relationship="CustOrders" sql:prefix="ord-">  
    </xsd:attribute>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="4baeb-126">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="4baeb-126">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="4baeb-127">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4baeb-127">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="4baeb-128">Guarde el archivo como sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="4baeb-128">Save the file as sqlPrefix.xml.</span></span>  
  
2.  <span data-ttu-id="4baeb-129">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4baeb-129">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="4baeb-130">Guarde el archivo como sqlPrefixT.xml en el mismo directorio donde guardó sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="4baeb-130">Save the file as sqlPrefixT.xml in the same directory where you saved sqlPrefix.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="sqlPrefix.xml">  
        /Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="4baeb-131">La ruta de acceso al directorio especificada para el esquema de asignación (sqlPrefix.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4baeb-131">The directory path specified for the mapping schema (sqlPrefix.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="4baeb-132">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4baeb-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlPrefix.xml"  
    ```  
  
3.  <span data-ttu-id="4baeb-133">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4baeb-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4baeb-134">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4baeb-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4baeb-135">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="4baeb-135">This is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" OrderIDList="ord-43860 ord-44501 ord-45283 ord-46042">  
    <Order SalesOrderID="ord-43860" OrderDate="2001-08-01" CustomerID="1">  
      <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
      ...  
    </Order>  
    ...  
 </Customer>  
</ROOT>  
```  
  
  
