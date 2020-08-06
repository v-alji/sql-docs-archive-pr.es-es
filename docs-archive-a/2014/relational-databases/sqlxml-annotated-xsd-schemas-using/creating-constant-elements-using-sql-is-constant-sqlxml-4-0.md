---
title: 'Crear elementos constantes mediante SQL: is-Constant (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- sql:is-constant
- XSD schemas [SQLXML], constant elements
- element mapping [SQLXML], constant elements
- is-constant annotation
- constant elements [SQLXML]
- annotated XSD schemas, constant elements
ms.assetid: 940eea1b-54f5-445f-b844-c894d9f3941b
author: rothja
ms.author: jroth
ms.openlocfilehash: 8deedd8547d6bc3f0154eedb889ad908750f071a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746821"
---
# <a name="creating-constant-elements-using-sqlis-constant-sqlxml-40"></a><span data-ttu-id="80bf0-102">Crear elementos constantes mediante sql:is-constant (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="80bf0-102">Creating Constant Elements Using sql:is-constant (SQLXML 4.0)</span></span>
  <span data-ttu-id="80bf0-103">Para especificar un elemento de constante, es decir, un elemento en el esquema XSD que no se asigna a ninguna tabla o columna de base de datos, puede usar la `sql:is-constant` anotación.</span><span class="sxs-lookup"><span data-stu-id="80bf0-103">To specify a constant element-that is, an element in the XSD schema that does not map to any database table or column-you can use the `sql:is-constant` annotation.</span></span> <span data-ttu-id="80bf0-104">Esta anotación toma un valor booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="80bf0-104">This annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="80bf0-105">Los valores permitidos son 0, 1, true y false.</span><span class="sxs-lookup"><span data-stu-id="80bf0-105">The acceptable values are 0, 1, true, and false.</span></span> <span data-ttu-id="80bf0-106">La anotación `sql:is-constant` se puede especificar en un elemento que no tiene ningún atributo.</span><span class="sxs-lookup"><span data-stu-id="80bf0-106">The `sql:is-constant` annotation can be specified on an element that does not have any attributes.</span></span> <span data-ttu-id="80bf0-107">Si se especifica en un elemento con el valor true (o 1), ese elemento no está asignado a la base de datos pero sigue apareciendo en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="80bf0-107">If it is specified on an element with the value true (or 1), that element is not mapped to the database but still appears in the XML document.</span></span>  
  
 <span data-ttu-id="80bf0-108">La anotación `sql:is-constant` se puede utilizar para:</span><span class="sxs-lookup"><span data-stu-id="80bf0-108">The `sql:is-constant` annotation can be used for:</span></span>  
  
-   <span data-ttu-id="80bf0-109">Agregar un elemento de nivel superior al documento XML.</span><span class="sxs-lookup"><span data-stu-id="80bf0-109">Adding a top-level element to the XML document.</span></span> <span data-ttu-id="80bf0-110">XML requiere un único elemento de nivel superior (root) para el documento.</span><span class="sxs-lookup"><span data-stu-id="80bf0-110">XML requires a single top-level element (root element) for the document.</span></span>  
  
-   <span data-ttu-id="80bf0-111">Crear elementos de contenedor, como un **\<Orders>** elemento que contiene todos los pedidos.</span><span class="sxs-lookup"><span data-stu-id="80bf0-111">Creating container elements, such as an **\<Orders>** element that wraps all orders.</span></span>  
  
 <span data-ttu-id="80bf0-112">La `sql:is-constant` anotación puede agregarse a un **\<complexType>** elemento.</span><span class="sxs-lookup"><span data-stu-id="80bf0-112">The `sql:is-constant` annotation can be added to a **\<complexType>** element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="80bf0-113">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="80bf0-113">Examples</span></span>  
 <span data-ttu-id="80bf0-114">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="80bf0-114">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="80bf0-115">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="80bf0-115">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlis-constant-to-add-a-container-element"></a><span data-ttu-id="80bf0-116">A.</span><span class="sxs-lookup"><span data-stu-id="80bf0-116">A.</span></span> <span data-ttu-id="80bf0-117">Especificar sql:is-constant para agregar un elemento contenedor</span><span class="sxs-lookup"><span data-stu-id="80bf0-117">Specifying sql:is-constant to add a container element</span></span>  
 <span data-ttu-id="80bf0-118">En este esquema XSD anotado, **\<CustomerOrders>** se define como un elemento constante especificando el `sql:is-constant` atributo con un valor de 1.</span><span class="sxs-lookup"><span data-stu-id="80bf0-118">In this annotated XSD schema, **\<CustomerOrders>** is defined as a constant element by specifying the `sql:is-constant` attribute with a value of 1.</span></span> <span data-ttu-id="80bf0-119">Por lo tanto, **\<CustomerOrders>** no se asigna a ninguna tabla o columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="80bf0-119">Therefore, **\<CustomerOrders>** is not mapped to any database table or column.</span></span> <span data-ttu-id="80bf0-120">Este elemento Constant está compuesto de los **\<Order>** elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="80bf0-120">This constant element consists of the **\<Order>** child elements.</span></span>  
  
 <span data-ttu-id="80bf0-121">Aunque no **\<CustomerOrders>** se asigna a ninguna tabla o columna de base de datos, sigue apareciendo en el XML resultante como un elemento contenedor que contiene los **\<Order>** elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="80bf0-121">Although **\<CustomerOrders>** does not map to any database table or column, it still appears in the resulting XML as a container element containing the **\<Order>** child elements.</span></span>  
  
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
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="CustomerOrders" sql:is-constant="1" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"  
                           sql:relationship="CustOrders"   
                           maxOccurs="unbounded" >  
                <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="OrderDate" type="xsd:date" />  
                   <xsd:attribute name="CustomerID" type="xsd:string" />  
                </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>  
         </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="80bf0-122">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="80bf0-122">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="80bf0-123">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="80bf0-123">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="80bf0-124">Guarde el archivo como isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="80bf0-124">Save the file as isConstant.xml.</span></span>  
  
2.  <span data-ttu-id="80bf0-125">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="80bf0-125">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="80bf0-126">Guarde el archivo como isConstantT.xml en el mismo directorio donde guardó isConstantT.xml.</span><span class="sxs-lookup"><span data-stu-id="80bf0-126">Save the file as isConstantT.xml in the same directory where you saved isConstant.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="isConstant.xml">  
            Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="80bf0-127">La ruta de acceso al directorio especificada para el esquema de asignación (isConstant.xml) es una ubicación relativa con respecto al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="80bf0-127">The directory path specified for the mapping schema (isConstant.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="80bf0-128">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="80bf0-128">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\isConstant.xml"  
    ```  
  
3.  <span data-ttu-id="80bf0-129">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="80bf0-129">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="80bf0-130">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="80bf0-130">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="80bf0-131">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="80bf0-131">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
<Customer CustomerID="1">   
  <CustomerOrders>   
    <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1" />   
    <Order SalesOrderID="44501" OrderDate="2001-11-01" CustomerID="1" />   
    <Order SalesOrderID="45283" OrderDate="2002-02-01" CustomerID="1" />   
    <Order SalesOrderID="46042" OrderDate="2002-05-01" CustomerID="1" />   
    ...  
  </CustomerOrders>   
</Customer>   
</ROOT>  
```  
  
  
