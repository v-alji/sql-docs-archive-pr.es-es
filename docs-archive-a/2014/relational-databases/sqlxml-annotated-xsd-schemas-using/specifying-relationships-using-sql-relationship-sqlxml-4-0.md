---
title: 'Especificar relaciones mediante SQL: Relationship (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- parent attribute [SQLXML]
- element relationships [SQLXML]
- multiple element relationships
- attribute relationships [SQLXML]
- sql:relationship
- relationship chains [SQLXML]
- IDREF relationships [SQLXML]
- parent-child relationships [SQLXML]
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- relationships [SQLXML], specifying
- unnamed relationships
- ID relationships [SQLXML]
- hierarchical relationships [SQLXML]
- named relationships [SQLXML]
ms.assetid: 98820afa-74e1-4e62-b336-6111a3dede4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 42c703de9d564580eb0baa1349a45b193109c87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672893"
---
# <a name="specifying-relationships-using-sqlrelationship-sqlxml-40"></a><span data-ttu-id="64f5c-102">Especificar relaciones mediante sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="64f5c-102">Specifying Relationships Using sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="64f5c-103">Los elementos de un documento XML pueden estar relacionados.</span><span class="sxs-lookup"><span data-stu-id="64f5c-103">The elements in an XML document can be related.</span></span> <span data-ttu-id="64f5c-104">Los elementos pueden estar anidados jerárquicamente y pueden especificarse relaciones ID, IDREF o IDREFS entre los elementos.</span><span class="sxs-lookup"><span data-stu-id="64f5c-104">The elements can be nested hierarchically, and ID, IDREF, or IDREFS relationships can be specified between the elements.</span></span>  
  
 <span data-ttu-id="64f5c-105">Por ejemplo, en un esquema XSD, un **\<Customer>** elemento contiene **\<Order>** elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="64f5c-105">For example, in an XSD schema, a **\<Customer>** element contains **\<Order>** child elements.</span></span> <span data-ttu-id="64f5c-106">Cuando el esquema se asigna a la base de datos AdventureWorks, el **\<Customer>** elemento se asigna a la tabla sales. Customer y el **\<Order>** elemento se asigna a la tabla sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="64f5c-106">When the schema is mapped to the AdventureWorks database, the **\<Customer>** element maps to the Sales.Customer table and the **\<Order>** element maps to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="64f5c-107">Estas tablas subyacentes, Sales.Customer y Sales.SalesOrderHeader, están relacionadas puesto que los clientes realizan pedidos.</span><span class="sxs-lookup"><span data-stu-id="64f5c-107">These underlying tables, Sales.Customer and Sales.SalesOrderHeader, are related because customers place orders.</span></span> <span data-ttu-id="64f5c-108">La columna CustomerID de la tabla Sales.SalesOrderHeader es una clave externa que hace referencia a la clave principal CustomerID de la tabla Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="64f5c-108">The CustomerID in the Sales.SalesOrderHeader table is a foreign key referring to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="64f5c-109">Puede establecer estas relaciones entre los elementos de esquema de asignación mediante la `sql:relationship` anotación.</span><span class="sxs-lookup"><span data-stu-id="64f5c-109">You can establish these relationships among mapping schema elements by using the `sql:relationship` annotation.</span></span>  
  
 <span data-ttu-id="64f5c-110">En el esquema XDR anotado, la anotación `sql:relationship` se usa para anidar jerárquicamente los elementos de esquema en función de las relaciones de clave principal y clave externa entre las tablas subyacentes a las que se asignan los elementos.</span><span class="sxs-lookup"><span data-stu-id="64f5c-110">In the annotated XSD schema, the `sql:relationship` annotation is used to nest the schema elements hierarchically, on the basis of primary key and foreign key relationships among the underlying tables to which the elements map.</span></span> <span data-ttu-id="64f5c-111">Para especificar la anotación `sql:relationship`, debe identificar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="64f5c-111">In specifying the `sql:relationship` annotation, you must identify the following:</span></span>  
  
-   <span data-ttu-id="64f5c-112">La tabla primaria (Sales.Customer) y la tabla secundaria (Sales.SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="64f5c-112">The parent table (Sales.Customer) and the child table (Sales.SalesOrderHeader).</span></span>  
  
-   <span data-ttu-id="64f5c-113">La columna o las columnas que crean la relación entre las tablas primarias y secundarias.</span><span class="sxs-lookup"><span data-stu-id="64f5c-113">The column or columns that compose the relationship between the parent and child tables.</span></span> <span data-ttu-id="64f5c-114">Por ejemplo, la columna CustomerID, que aparece tanto en las tablas primarias como en las secundarias.</span><span class="sxs-lookup"><span data-stu-id="64f5c-114">For example, the CustomerID column, which appears in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="64f5c-115">Esta información se usa para generar la jerarquía apropiada.</span><span class="sxs-lookup"><span data-stu-id="64f5c-115">This information is used to generate the proper hierarchy.</span></span>  
  
 <span data-ttu-id="64f5c-116">Para proporcionar los nombres de tabla y la información de combinación necesaria, se especifican los siguientes atributos en la `sql:relationship` anotación.</span><span class="sxs-lookup"><span data-stu-id="64f5c-116">To provide the table names and the necessary join information, the following attributes are specified on the `sql:relationship` annotation.</span></span> <span data-ttu-id="64f5c-117">Estos atributos solo son válidos con el **\<sql:relationship>** elemento:</span><span class="sxs-lookup"><span data-stu-id="64f5c-117">These attributes are valid only with the **\<sql:relationship>** element:</span></span>  
  
 <span data-ttu-id="64f5c-118">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="64f5c-118">**Name**</span></span>  
 <span data-ttu-id="64f5c-119">Especifica el nombre único de la relación.</span><span class="sxs-lookup"><span data-stu-id="64f5c-119">Specifies the unique name of the relationship.</span></span>  
  
 <span data-ttu-id="64f5c-120">**Parent**</span><span class="sxs-lookup"><span data-stu-id="64f5c-120">**Parent**</span></span>  
 <span data-ttu-id="64f5c-121">Especifica la relación primaria (tabla).</span><span class="sxs-lookup"><span data-stu-id="64f5c-121">Specifies the parent relation (table).</span></span> <span data-ttu-id="64f5c-122">Es un atributo opcional; si no se especifica, el nombre de la tabla primaria se obtiene a partir de la información de la jerarquía secundaria del documento.</span><span class="sxs-lookup"><span data-stu-id="64f5c-122">This is an optional attribute; if the attribute is not specified, the parent table name is obtained from information in the child hierarchy in the document.</span></span> <span data-ttu-id="64f5c-123">Si el esquema especifica dos jerarquías de elementos primarios y secundarios que utilizan los mismos **\<sql:relationship>** elementos primarios pero distintos, no se especifica el atributo primario en **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="64f5c-123">If the schema specifies two parent-child hierarchies that use the same **\<sql:relationship>** but different parent elements, you do not specify the parent attribute in **\<sql:relationship>**.</span></span> <span data-ttu-id="64f5c-124">Esta información se obtiene de la jerarquía del esquema.</span><span class="sxs-lookup"><span data-stu-id="64f5c-124">This information is obtained from the hierarchy in the schema.</span></span>  
  
 <span data-ttu-id="64f5c-125">**parent-key**</span><span class="sxs-lookup"><span data-stu-id="64f5c-125">**parent-key**</span></span>  
 <span data-ttu-id="64f5c-126">Especifica la clave principal del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="64f5c-126">Specifies the parent key of the parent.</span></span> <span data-ttu-id="64f5c-127">Si la clave principal se compone de varias columnas, los valores se especifican con un espacio entre ellos.</span><span class="sxs-lookup"><span data-stu-id="64f5c-127">If the parent key is composed of multiple columns, values are specified with a space between them.</span></span> <span data-ttu-id="64f5c-128">Hay una asignación de posición entre los valores que se especifican para la clave de varias columnas y la clave secundaria correspondiente.</span><span class="sxs-lookup"><span data-stu-id="64f5c-128">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding child key.</span></span>  
  
 <span data-ttu-id="64f5c-129">**Elemento secundario**</span><span class="sxs-lookup"><span data-stu-id="64f5c-129">**Child**</span></span>  
 <span data-ttu-id="64f5c-130">Especifica la relación secundaria (tabla).</span><span class="sxs-lookup"><span data-stu-id="64f5c-130">Specifies the child relation (table).</span></span>  
  
 <span data-ttu-id="64f5c-131">**child-key**</span><span class="sxs-lookup"><span data-stu-id="64f5c-131">**child-key**</span></span>  
 <span data-ttu-id="64f5c-132">Especifica la clave secundaria del elemento secundario que hace referencia a la clave principal del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="64f5c-132">Specifies the child key in the child referring to parent-key in parent.</span></span> <span data-ttu-id="64f5c-133">Si la clave secundaria está compuesta de varios atributos (columnas), los valores de la clave del elemento secundario se especifican con un espacio entre ellos.</span><span class="sxs-lookup"><span data-stu-id="64f5c-133">If the child key is composed of multiple attributes (columns), the child-key values are specified with a space between them.</span></span> <span data-ttu-id="64f5c-134">Hay una asignación de posición entre los valores que se especifican para la clave de varias columnas y la clave principal correspondiente.</span><span class="sxs-lookup"><span data-stu-id="64f5c-134">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding parent key.</span></span>  
  
 <span data-ttu-id="64f5c-135">**Inverse**</span><span class="sxs-lookup"><span data-stu-id="64f5c-135">**Inverse**</span></span>  
 <span data-ttu-id="64f5c-136">Diagramas usa este atributo especificado en **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="64f5c-136">This attribute specified on **\<sql:relationship>** is used by updategrams.</span></span> <span data-ttu-id="64f5c-137">Para obtener más información, vea [especificar el atributo SQL: inverso en SQL: Relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="64f5c-137">For more information, see [Specifying the sql:inverse Attribute on sql:relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="64f5c-138">La `sql:key-fields` anotación debe especificarse en un elemento que contenga un elemento secundario, que tiene un **\<sql:relationship>** definido entre el elemento y el elemento secundario, y que no proporciona la clave principal de la tabla especificada en el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="64f5c-138">The `sql:key-fields` annotation must be specified in an element that contains a child element, that has a **\<sql:relationship>** defined between the element and the child, and that does not provide the primary key of the table specified in the parent element.</span></span> <span data-ttu-id="64f5c-139">Incluso si el esquema no especifica **\<sql:relationship>** , debe especificar `sql:key-fields` para generar la jerarquía adecuada.</span><span class="sxs-lookup"><span data-stu-id="64f5c-139">Even if the schema does not specify **\<sql:relationship>**, you must specify `sql:key-fields` to produce the proper hierarchy.</span></span> <span data-ttu-id="64f5c-140">Para obtener más información, vea [identificar columnas de clave mediante SQL: Key-Fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="64f5c-140">For more information, see [Identifying Key Columns by Using sql:key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="64f5c-141">Para generar el anidamiento correcto en el resultado, se recomienda `sql:key-fields` especificar en todos los esquemas.</span><span class="sxs-lookup"><span data-stu-id="64f5c-141">To produce proper nesting in the result, it is recommended that `sql:key-fields` are specified in all schemas.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="64f5c-142">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="64f5c-142">Examples</span></span>  
 <span data-ttu-id="64f5c-143">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="64f5c-143">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="64f5c-144">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="64f5c-144">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelationship-annotation-on-an-element"></a><span data-ttu-id="64f5c-145">A.</span><span class="sxs-lookup"><span data-stu-id="64f5c-145">A.</span></span> <span data-ttu-id="64f5c-146">Especificar la anotación sql:relationship en un elemento</span><span class="sxs-lookup"><span data-stu-id="64f5c-146">Specifying the sql:relationship annotation on an element</span></span>  
 <span data-ttu-id="64f5c-147">El siguiente esquema XSD anotado incluye **\<Customer>** **\<Order>** los elementos y.</span><span class="sxs-lookup"><span data-stu-id="64f5c-147">The following annotated XSD schema includes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="64f5c-148">El **\<Order>** elemento es un elemento secundario del **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="64f5c-148">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span>  
  
 <span data-ttu-id="64f5c-149">En el esquema, la `sql:relationship` anotación se especifica en el **\<Order>** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="64f5c-149">In the schema, the `sql:relationship` annotation is specified on the **\<Order>** child element.</span></span> <span data-ttu-id="64f5c-150">La propia relación se define en el **\<xsd:appinfo>** elemento.</span><span class="sxs-lookup"><span data-stu-id="64f5c-150">The relationship itself is defined in the **\<xsd:appinfo>** element.</span></span>  
  
 <span data-ttu-id="64f5c-151">El **\<relationship>** elemento identifica CustomerID en la tabla sales. SalesOrderHeader como una clave externa que hace referencia a la clave principal CustomerID de la tabla sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="64f5c-151">The **\<relationship>** element identifies CustomerID in the Sales.SalesOrderHeader table as a foreign key that refers to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="64f5c-152">Por lo tanto, los pedidos que pertenecen a un cliente aparecen como un elemento secundario de dicho **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="64f5c-152">Therefore, orders that belong to a customer appear as a child element of that **\<Customer>** element.</span></span>  
  
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
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                    sql:relationship="CustOrders" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="64f5c-153">El esquema anterior usa una relación con nombre.</span><span class="sxs-lookup"><span data-stu-id="64f5c-153">The previous schema uses a named relationship.</span></span> <span data-ttu-id="64f5c-154">También puede especificar una relación sin nombre.</span><span class="sxs-lookup"><span data-stu-id="64f5c-154">You can also specify an unnamed relationship.</span></span> <span data-ttu-id="64f5c-155">Los resultados son los mismos.</span><span class="sxs-lookup"><span data-stu-id="64f5c-155">The results are same.</span></span>  
  
 <span data-ttu-id="64f5c-156">Éste es el esquema revisado en el que se especifica una relación sin nombre:</span><span class="sxs-lookup"><span data-stu-id="64f5c-156">This is the revised schema in which an unnamed relationship is specified:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer"  type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader">  
           <xsd:annotation>  
            <xsd:appinfo>  
              <sql:relationship   
                parent="Sales.Customer"  
                parent-key="CustomerID"  
                child="Sales.SalesOrderHeader"  
                child-key="CustomerID" />  
            </xsd:appinfo>  
           </xsd:annotation>  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="64f5c-157">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="64f5c-157">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="64f5c-158">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-158">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="64f5c-159">Guarde el archivo como sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-159">Save the file as sql-relationship.xml.</span></span>  
  
2.  <span data-ttu-id="64f5c-160">Copie la siguiente plantilla y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-160">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="64f5c-161">Guarde el archivo como sql-relationshipT.xml en el mismo directorio donde guardó sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-161">Save the file as sql-relationshipT.xml in the same directory where you saved sql-relationship.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-relationship.xml">  
            /Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="64f5c-162">La ruta de acceso al directorio especificada para el esquema de asignación (sql-relationship.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-162">The directory path specified for the mapping schema (sql-relationship.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="64f5c-163">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64f5c-163">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-relationship.xml"  
    ```  
  
3.  <span data-ttu-id="64f5c-164">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-164">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="64f5c-165">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="64f5c-165">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="64f5c-166">El conjunto de resultados es:</span><span class="sxs-lookup"><span data-stu-id="64f5c-166">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1">   
    <Order OrderID="43860" CustomerID="1" />   
    <Order OrderID="44501" CustomerID="1" />   
    <Order OrderID="45283" CustomerID="1" />   
    <Order OrderID="46042" CustomerID="1" />   
  </Customer>   
</ROOT>  
```  
  
### <a name="b-specifying-a-relationship-chain"></a><span data-ttu-id="64f5c-167">B.</span><span class="sxs-lookup"><span data-stu-id="64f5c-167">B.</span></span> <span data-ttu-id="64f5c-168">Especificar una cadena de relación</span><span class="sxs-lookup"><span data-stu-id="64f5c-168">Specifying a relationship chain</span></span>  
 <span data-ttu-id="64f5c-169">Para este ejemplo, supongamos que desea que el siguiente documento XML use los datos obtenidos de la base de datos AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="64f5c-169">For this example, assume that you want the following XML document using data obtained from the AdventureWorks database:</span></span>  
  
```  
<Order SalesOrderID="43659">  
  <Product Name="Mountain Bike Socks, M"/>   
  <Product Name="Sport-100 Helmet, Blue"/>  
  ...  
</Order>  
...  
```  
  
 <span data-ttu-id="64f5c-170">Para cada pedido de la tabla sales. SalesOrderHeader, el documento XML tiene un **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="64f5c-170">For each order in the Sales.SalesOrderHeader table, the XML document has one **\<Order>** element.</span></span> <span data-ttu-id="64f5c-171">Y cada **\<Order>** elemento tiene una lista de **\<Product>** elementos secundarios, uno para cada producto solicitado en el orden.</span><span class="sxs-lookup"><span data-stu-id="64f5c-171">And each **\<Order>** element has a list of **\<Product>** child elements, one for each product requested in the order.</span></span>  
  
 <span data-ttu-id="64f5c-172">Para especificar un esquema XSD que generará esta jerarquía, debe especificar dos relaciones: OrderOD y ODProduct.</span><span class="sxs-lookup"><span data-stu-id="64f5c-172">To specify an XSD schema that will produce this hierarchy, you must specify two relationships: OrderOD and ODProduct.</span></span> <span data-ttu-id="64f5c-173">La relación OrderOD especifica la relación de elementos primarios y secundarios entre las tablas Sales.SalesOrderHeader y Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="64f5c-173">The OrderOD relationship specifies the parent-child relationship between the Sales.SalesOrderHeader and Sales.SalesOrderDetail tables.</span></span> <span data-ttu-id="64f5c-174">La relación ODProduct especifica la relación entre las tablas Sales.SalesOrderDetail y Production.Product.</span><span class="sxs-lookup"><span data-stu-id="64f5c-174">The ODProduct relationship specifies the relationship between the Sales.SalesOrderDetail and Production.Product tables.</span></span>  
  
 <span data-ttu-id="64f5c-175">En el esquema siguiente, la `msdata:relationship` anotación en el **\<Product>** elemento especifica dos valores: OrderOD y ODProduct.</span><span class="sxs-lookup"><span data-stu-id="64f5c-175">In the following schema, the `msdata:relationship` annotation on the **\<Product>** element specifies two values: OrderOD and ODProduct.</span></span> <span data-ttu-id="64f5c-176">Es importante el orden en que se especifican estos valores.</span><span class="sxs-lookup"><span data-stu-id="64f5c-176">The order in which these values are specified is important.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <msdata:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  
    <msdata:relationship name="ODProduct"  
          parent="Sales.SalesOrderDetail"  
          parent-key="ProductID"  
          child="Production.Product"  
          child-key="ProductID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID"  
                     msdata:relationship="OrderOD ODProduct">  
          <xsd:complexType>  
             <xsd:attribute name="Name" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="64f5c-177">En lugar de especificar una relación con nombre, puede especificar una relación anónima.</span><span class="sxs-lookup"><span data-stu-id="64f5c-177">Instead of specifying a named relationship, you can specify an anonymous relationship.</span></span> <span data-ttu-id="64f5c-178">En este caso, todo el contenido de **\<annotation>** ... **\</annotation>** , que describe las dos relaciones, aparece como un elemento secundario de **\<Product>** .</span><span class="sxs-lookup"><span data-stu-id="64f5c-178">In this case, the entire contents of **\<annotation>**...**\</annotation>**, which describes the two relationships, appear as a child element of **\<Product>**.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID" >  
         <xsd:annotation>  
          <xsd:appinfo>  
           <msdata:relationship   
               parent="Sales.SalesOrderHeader"  
               parent-key="SalesOrderID"  
               child="Sales.SalesOrderDetail"  
               child-key="SalesOrderID" />  
  
           <msdata:relationship   
               parent="Sales.SalesOrderDetail"  
               parent-key="ProductID"  
               child="Production.Product"  
               child-key="ProductID" />  
         </xsd:appinfo>  
       </xsd:annotation>  
       <xsd:complexType>  
          <xsd:attribute name="Name" type="xsd:string" />  
       </xsd:complexType>  
     </xsd:element>  
   </xsd:sequence>  
   <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
  </xsd:complexType>  
 </xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="64f5c-179">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="64f5c-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="64f5c-180">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-180">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="64f5c-181">Guarde el archivo como relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-181">Save the file as relationshipChain.xml.</span></span>  
  
2.  <span data-ttu-id="64f5c-182">Copie la siguiente plantilla y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-182">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="64f5c-183">Guarde el archivo como relationshipChainT.xml en el mismo directorio donde guardó relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-183">Save the file as relationshipChainT.xml in the same directory where you saved relationshipChain.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationshipChain.xml">  
            /Order  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="64f5c-184">La ruta de acceso al directorio especificada para el esquema de asignación (relationshipChain.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-184">The directory path specified for the mapping schema (relationshipChain.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="64f5c-185">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64f5c-185">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationshipChain.xml"  
    ```  
  
3.  <span data-ttu-id="64f5c-186">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-186">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="64f5c-187">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="64f5c-187">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="64f5c-188">El conjunto de resultados es:</span><span class="sxs-lookup"><span data-stu-id="64f5c-188">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Order SalesOrderID="43659">  
    <Product Name="Mountain Bike Socks, M" />   
    <Product Name="Sport-100 Helmet, Blue" />   
    <Product Name="AWC Logo Cap" />   
    <Product Name="Long-Sleeve Logo Jersey, M" />   
    <Product Name="Long-Sleeve Logo Jersey, XL" />   
    ...  
  </Order>  
  ...  
</ROOT>  
```  
  
### <a name="c-specifying-the-relationship-annotation-on-an-attribute"></a><span data-ttu-id="64f5c-189">C.</span><span class="sxs-lookup"><span data-stu-id="64f5c-189">C.</span></span> <span data-ttu-id="64f5c-190">Especificar la anotación relationship en un atributo</span><span class="sxs-lookup"><span data-stu-id="64f5c-190">Specifying the relationship annotation on an attribute</span></span>  
 <span data-ttu-id="64f5c-191">El esquema de este ejemplo incluye un \<Customer> elemento con un \<CustomerID> elemento secundario y un atributo atributo OrderIDList de tipo IDREFS.</span><span class="sxs-lookup"><span data-stu-id="64f5c-191">The schema in this example includes a \<Customer> element with a \<CustomerID> child element and an OrderIDList attribute of IDREFS type.</span></span> <span data-ttu-id="64f5c-192">El \<Customer> elemento se asigna a la tabla sales. Customer de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="64f5c-192">The \<Customer> element maps to the Sales.Customer table in the AdventureWorks database.</span></span> <span data-ttu-id="64f5c-193">De forma predeterminada, el ámbito de esta asignación se aplica a todos los elementos o atributos secundarios, a menos que `sql:relation` se especifique en el elemento o atributo secundario, en cuyo caso, la relación de clave principal y clave externa adecuada debe definirse mediante el \<relationship> elemento.</span><span class="sxs-lookup"><span data-stu-id="64f5c-193">By default, the scope of this mapping applies to all the child elements or attributes unless `sql:relation` is specified on the child element or attribute, in which case, the appropriate primary-key/foreign-key relationship must be defined using the \<relationship> element.</span></span> <span data-ttu-id="64f5c-194">Además, el elemento o atributo secundario, que especifica una tabla distinta mediante la anotación `relation`, también debe especificar la anotación `relationship`.</span><span class="sxs-lookup"><span data-stu-id="64f5c-194">And the child element or attribute, which specifies the different table using the `relation` annotation, must also specify the `relationship` annotation.</span></span>  
  
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
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="CustomerID"   type="xsd:string" />   
     </xsd:sequence>  
     <xsd:attribute name="OrderIDList"   
                     type="xsd:IDREFS"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:field="SalesOrderID"  
                     sql:relationship="CustOrders" >  
        </xsd:attribute>  
    </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="64f5c-195">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="64f5c-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="64f5c-196">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-196">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="64f5c-197">Guarde el archivo como relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-197">Save the file as relationship-on-attribute.xml.</span></span>  
  
2.  <span data-ttu-id="64f5c-198">Copie la plantilla siguiente y péguela en un archivo.</span><span class="sxs-lookup"><span data-stu-id="64f5c-198">Copy the following template and paste it into a file.</span></span> <span data-ttu-id="64f5c-199">Guarde el archivo como relationship-on-attributeT.xml en el mismo directorio donde guardó relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-199">Save the file as relationship-on-attributeT.xml in the same directory where you saved relationship-on-attribute.xml.</span></span> <span data-ttu-id="64f5c-200">La consulta de la plantilla selecciona un cliente cuyo CustomerID es 1.</span><span class="sxs-lookup"><span data-stu-id="64f5c-200">The query in the template selects a customer with the CustomerID of 1.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-on-attribute.xml">  
        /Customer[CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="64f5c-201">La ruta de acceso al directorio especificada para el esquema de asignación (relationship-on-attribute.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-201">The directory path specified for the mapping schema (relationship-on-attribute.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="64f5c-202">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64f5c-202">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-on-attribute.xml"  
    ```  
  
3.  <span data-ttu-id="64f5c-203">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-203">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="64f5c-204">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="64f5c-204">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="64f5c-205">El conjunto de resultados es:</span><span class="sxs-lookup"><span data-stu-id="64f5c-205">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer OrderIDList="43860 44501 45283 46042">  
    <CustomerID>1</CustomerID>   
  </Customer>  
</ROOT>  
```  
  
### <a name="d-specifying-sqlrelationship-on-multiple-elements"></a><span data-ttu-id="64f5c-206">D.</span><span class="sxs-lookup"><span data-stu-id="64f5c-206">D.</span></span> <span data-ttu-id="64f5c-207">Especificar sql:relationship en varios elementos</span><span class="sxs-lookup"><span data-stu-id="64f5c-207">Specifying sql:relationship on multiple elements</span></span>  
 <span data-ttu-id="64f5c-208">En este ejemplo, el esquema XSD anotado contiene los **\<Customer>** **\<Order>** elementos, y **\<OrderDetail>** .</span><span class="sxs-lookup"><span data-stu-id="64f5c-208">In this example, the annotated XSD schema contains the **\<Customer>**, **\<Order>**, and **\<OrderDetail>** elements.</span></span>  
  
 <span data-ttu-id="64f5c-209">El **\<Order>** elemento es un elemento secundario del **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="64f5c-209">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span> <span data-ttu-id="64f5c-210">**\<sql:relationship>** se especifica en el **\<Order>** elemento secundario; por lo tanto, los pedidos pertenecientes a un cliente aparecen como elementos secundarios de **\<Customer>** .</span><span class="sxs-lookup"><span data-stu-id="64f5c-210">**\<sql:relationship>** is specified on the **\<Order>** child element; therefore, orders that belong to a customer appear as child elements of **\<Customer>**.</span></span>  
  
 <span data-ttu-id="64f5c-211">El **\<Order>** elemento incluye el **\<OrderDetail>** elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="64f5c-211">The **\<Order>** element includes the **\<OrderDetail>** child element.</span></span> <span data-ttu-id="64f5c-212">**\<sql:relationship>** se especifica en **\<OrderDetail>** el elemento secundario, por lo que los detalles del pedido que pertenecen a un pedido aparecen como elementos secundarios de ese **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="64f5c-212">**\<sql:relationship>** is specified on **\<OrderDetail>** child element, so the order details that pertain to an order appear as child elements of that **\<Order>** element.</span></span>  
  
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
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="64f5c-213">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="64f5c-213">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="64f5c-214">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-214">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="64f5c-215">Guarde el archivo como relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-215">Save the file as relationship-multiple-elements.xml.</span></span>  
  
2.  <span data-ttu-id="64f5c-216">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-216">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="64f5c-217">Guarde el archivo como relationship-multiple-elementsT.xml en el mismo directorio donde guardó relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-217">Save the file as relationship-multiple-elementsT.xml in the same directory where you saved relationship-multiple-elements.xml.</span></span> <span data-ttu-id="64f5c-218">La consulta de la plantilla devuelve la información de pedidos de un cliente cuyo CustomerID es 1 y cuyo SalesOrderID es 43860.</span><span class="sxs-lookup"><span data-stu-id="64f5c-218">The query in the template returns order information for a customer with the CustomerID of 1 and SalesOrderID of 43860.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-multiple-elements.xml">  
        /Customer[@CustomerID=1]/Order[@SalesOrderID=43860]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="64f5c-219">La ruta de acceso al directorio especificada para el esquema de asignación (relationship-multiple-elements.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-219">The directory path specified for the mapping schema (relationship-multiple-elements.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="64f5c-220">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64f5c-220">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-multiple-elements.xml"  
    ```  
  
3.  <span data-ttu-id="64f5c-221">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-221">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="64f5c-222">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="64f5c-222">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="64f5c-223">El conjunto de resultados es:</span><span class="sxs-lookup"><span data-stu-id="64f5c-223">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1">  
     <OrderDetail SalesOrderID="43860" ProductID="761" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="770" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="758" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="765" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="762" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="768" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="763" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="756" OrderQty="1" />   
  </Order>  
</ROOT>  
```  
  
### <a name="e-specifying-the-sqlrelationship-without-the-parent-attribute"></a><span data-ttu-id="64f5c-224">E.</span><span class="sxs-lookup"><span data-stu-id="64f5c-224">E.</span></span> <span data-ttu-id="64f5c-225">Especificar \<sql:relationship> sin el atributo primario</span><span class="sxs-lookup"><span data-stu-id="64f5c-225">Specifying the \<sql:relationship> without the parent attribute</span></span>  
 <span data-ttu-id="64f5c-226">En este ejemplo se muestra cómo especificar **\<sql:relationship>** sin el atributo **primario** .</span><span class="sxs-lookup"><span data-stu-id="64f5c-226">This example illustrates specifying the **\<sql:relationship>** without the **parent** attribute.</span></span> <span data-ttu-id="64f5c-227">Por ejemplo, imagine que tiene las siguientes tablas de empleados:</span><span class="sxs-lookup"><span data-stu-id="64f5c-227">For example, assume you have the following employee tables:</span></span>  
  
```  
Emp1(SalesPersonID, FirstName, LastName, ReportsTo)  
Emp2(SalesPersonID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="64f5c-228">La siguiente vista XML tiene los **\<Emp1>** **\<Emp2>** elementos y asignados a las tablas sales. Emp1 y sales. Emp2:</span><span class="sxs-lookup"><span data-stu-id="64f5c-228">The following XML view has the **\<Emp1>** and **\<Emp2>** elements mapping to the Sales.Emp1 and Sales.Emp2 tables:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="EmpOrders"  
          parent-key="SalesPersonID"  
          child="Sales.SalesOrderHeader"  
          child-key="SalesPersonID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Emp1" sql:relation="Sales.Emp1" type="EmpType" />  
  <xsd:element name="Emp2" sql:relation="Sales.Emp2" type="EmpType" />  
   <xsd:complexType name="EmpType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:relationship="EmpOrders" >  
          <xsd:complexType>  
             <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesPersonID"   type="xsd:integer" />   
        <xsd:attribute name="LastName"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="64f5c-229">En el esquema, el **\<Emp1>** elemento y el **\<Emp2>** elemento son de tipo `EmpType` .</span><span class="sxs-lookup"><span data-stu-id="64f5c-229">In the schema, both the **\<Emp1>** element and **\<Emp2>** element are of type `EmpType`.</span></span> <span data-ttu-id="64f5c-230">El tipo `EmpType` describe un **\<Order>** elemento secundario y el correspondiente **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="64f5c-230">The type `EmpType` describes an **\<Order>** child element and the corresponding **\<sql:relationship>**.</span></span> <span data-ttu-id="64f5c-231">En este caso, no hay ningún elemento primario único que se pueda identificar en **\<sql:relationship>** mediante el atributo **primario** .</span><span class="sxs-lookup"><span data-stu-id="64f5c-231">In this case, there is no single parent that can be identified in **\<sql:relationship>** by using the **parent** attribute.</span></span> <span data-ttu-id="64f5c-232">En esta situación, no se especifica el atributo **primario** en **\<sql:relationship>** ; la información de atributo **primario** se obtiene de la jerarquía del esquema.</span><span class="sxs-lookup"><span data-stu-id="64f5c-232">In this situation, you don't specify the **parent** attribute in **\<sql:relationship>**; the **parent** attribute information is obtained from the hierarchy in the schema.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="64f5c-233">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="64f5c-233">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="64f5c-234">Cree estas tablas en la base de datos AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="64f5c-234">Create these tables in the AdventureWorks database:</span></span>  
  
    ```  
    USE AdventureWorks  
    CREATE TABLE Sales.Emp1 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    CREATE TABLE Sales.Emp2 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    ```  
  
2.  <span data-ttu-id="64f5c-235">Agregue estos datos de ejemplo en las tablas:</span><span class="sxs-lookup"><span data-stu-id="64f5c-235">Add this sample data in the tables:</span></span>  
  
    ```  
    INSERT INTO Sales.Emp1 values (279, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Sales.Emp1 values (282, 'Andrew', 'Fuller',1)  
    INSERT INTO Sales.Emp1 values (276, 'Janet', 'Leverling',1)  
    INSERT INTO Sales.Emp2 values (277, 'Margaret', 'Peacock',3)  
    INSERT INTO Sales.Emp2 values (283, 'Steven', 'Devolio',4)  
    INSERT INTO Sales.Emp2 values (275, 'Nancy', 'Buchanan',5)  
    INSERT INTO Sales.Emp2 values (281, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="64f5c-236">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-236">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="64f5c-237">Guarde el archivo como relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-237">Save the file as relationship-noparent.xml.</span></span>  
  
4.  <span data-ttu-id="64f5c-238">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="64f5c-238">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="64f5c-239">Guarde el archivo como relationship-noparentT.xml en el mismo directorio donde guardó relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="64f5c-239">Save the file as relationship-noparentT.xml in the same directory where you saved relationship-noparent.xml.</span></span> <span data-ttu-id="64f5c-240">La consulta de la plantilla selecciona todos los \<Emp1> elementos (por lo tanto, el elemento primario es Emp1).</span><span class="sxs-lookup"><span data-stu-id="64f5c-240">The query in the template selects all the \<Emp1> elements (therefore, the parent is Emp1).</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationship-noparent.xml">  
            /Emp1  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="64f5c-241">La ruta de acceso al directorio especificada para el esquema de asignación (relationship-noparent.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-241">The directory path specified for the mapping schema (relationship-noparent.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="64f5c-242">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64f5c-242">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-noparent.xml"  
    ```  
  
5.  <span data-ttu-id="64f5c-243">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="64f5c-243">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="64f5c-244">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="64f5c-244">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="64f5c-245">A continuación se muestra un conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="64f5c-245">Here is a partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<Emp1 SalesPersonID="276" LastName="Leverling">  
  <Order SalesOrderID="43663" CustomerID="510" />   
  <Order SalesOrderID="43666" CustomerID="511" />   
  <Order SalesOrderID="43859" CustomerID="259" />  
  ...  
</Emp1>  
```  
  
  
