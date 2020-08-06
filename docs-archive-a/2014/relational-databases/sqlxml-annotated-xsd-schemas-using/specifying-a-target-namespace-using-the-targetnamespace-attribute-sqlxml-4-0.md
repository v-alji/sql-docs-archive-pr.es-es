---
title: Especificar un espacio de nombres de destino mediante el atributo targetNamespace (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- targetNamespace attribute
- XSD schemas [SQLXML], target namespaces
- annotated XSD schemas, target namespaces
- xsd:targetNamespace
- attributeFormDefault attribute
- elementFormDefault attribute
- target namespaces [SQLXML]
ms.assetid: f3df9877-6672-4444-8245-2670063c9310
author: rothja
ms.author: jroth
ms.openlocfilehash: 823bcbf7f4906a2e1d2ced1ff58b681c0ca41a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676419"
---
# <a name="specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-40"></a><span data-ttu-id="a59c0-102">Especificar un espacio de nombres de destino mediante el atributo targetNamespace (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a59c0-102">Specifying a Target Namespace Using the targetNamespace Attribute (SQLXML 4.0)</span></span>
  <span data-ttu-id="a59c0-103">Al escribir esquemas XSD, puede usar el atributo **targetNamespace** de XSD para especificar un espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="a59c0-103">In writing XSD schemas, you can use the XSD **targetNamespace** attribute to specify a target namespace.</span></span> <span data-ttu-id="a59c0-104">En este tema se describe cómo funcionan los atributos XSD **targetNamespace**, **elementFormDefault**y **attributeFormDefault** , cómo afectan a la instancia XML que se genera y cómo se especifican las consultas XPath con espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="a59c0-104">This topic describes how the XSD **targetNamespace**, **elementFormDefault**, and **attributeFormDefault** attributes work, how they affect the XML instance that is generated, and how XPath queries are specified with namespaces.</span></span>  
  
 <span data-ttu-id="a59c0-105">Puede usar el atributo **xsd: targetNamespace** para colocar elementos y atributos del espacio de nombres predeterminado en un espacio de nombres diferente.</span><span class="sxs-lookup"><span data-stu-id="a59c0-105">You can use the **xsd:targetNamespace** attribute to place elements and attributes from the default namespace into a different namespace.</span></span> <span data-ttu-id="a59c0-106">También puede especificar si los elementos y los atributos del esquema declarados localmente deben estar certificados por un espacio de nombres, ya sea explícitamente mediante un prefijo o implícitamente de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a59c0-106">You can also specify whether the locally declared elements and attributes of the schema should appear qualified by a namespace, either explicitly by using a prefix or implicitly by default.</span></span> <span data-ttu-id="a59c0-107">Puede usar los atributos **elementFormDefault** y **attributeFormDefault** en el **\<xsd:schema>** elemento para especificar globalmente la calificación de elementos y atributos locales, o puede usar el atributo **Form** para especificar elementos y atributos individuales por separado.</span><span class="sxs-lookup"><span data-stu-id="a59c0-107">You can use the **elementFormDefault** and **attributeFormDefault** attributes on the **\<xsd:schema>** element to globally specify the qualification of local elements and attributes, or you can use the **form** attribute to specify individual elements and attributes separately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a59c0-108">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a59c0-108">Examples</span></span>  
 <span data-ttu-id="a59c0-109">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="a59c0-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="a59c0-110">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="a59c0-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-a-target-namespace"></a><span data-ttu-id="a59c0-111">A.</span><span class="sxs-lookup"><span data-stu-id="a59c0-111">A.</span></span> <span data-ttu-id="a59c0-112">Especificar un espacio de nombres de destino</span><span class="sxs-lookup"><span data-stu-id="a59c0-112">Specifying a target namespace</span></span>  
 <span data-ttu-id="a59c0-113">El siguiente esquema XSD especifica un espacio de nombres de destino mediante el atributo **xsd: targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="a59c0-113">The following XSD schema specifies a target namespace by using the **xsd:targetNamespace** attribute.</span></span> <span data-ttu-id="a59c0-114">El esquema también establece los valores de atributo **elementFormDefault** y **attributeFormDefault** en **"Unqualified"** (el valor predeterminado de estos atributos).</span><span class="sxs-lookup"><span data-stu-id="a59c0-114">The schema also sets the **elementFormDefault** and **attributeFormDefault** attribute values to **"unqualified"** (the default value for these attributes).</span></span> <span data-ttu-id="a59c0-115">Se trata de una declaración global que afecta a todos los elementos locales ( **\<Order>** en el esquema) y atributos (**CustomerID**, **ContactName**y **OrderID** en el esquema).</span><span class="sxs-lookup"><span data-stu-id="a59c0-115">This is a global declaration and affects all the local elements (**\<Order>** in the schema) and attributes (**CustomerID**, **ContactName**, and **OrderID** in the schema).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:CO="urn:MyNamespace"   
            targetNamespace="urn:MyNamespace" >  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer"   
               sql:relation="Sales.Customer"   
               type="CO:CustomerType" />  
  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustOrders"  
                     type="CO:OrderType" />  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesPersonID"  type="xsd:string" />  
  </xsd:complexType>  
  <xsd:complexType name="OrderType" >  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="a59c0-116">En el esquema:</span><span class="sxs-lookup"><span data-stu-id="a59c0-116">In the schema:</span></span>  
  
-   <span data-ttu-id="a59c0-117">Las declaraciones de tipos **CustomerType** y **OrderType** son globales y, por lo tanto, se incluyen en el espacio de nombres de destino del esquema.</span><span class="sxs-lookup"><span data-stu-id="a59c0-117">The **CustomerType** and **OrderType** type declarations are global and, therefore, are included in the schema's target namespace.</span></span> <span data-ttu-id="a59c0-118">Como resultado, cuando se hace referencia a estos tipos en la declaración del **\<Customer>** elemento y en su **\<Order>** elemento secundario, se especifica un prefijo que está asociado con el espacio de nombres de destino.</span><span class="sxs-lookup"><span data-stu-id="a59c0-118">As a result, when these types are referenced in the declaration of **\<Customer>** element and its **\<Order>** child element, a prefix is specified that is associated with the target namespace.</span></span>  
  
-   <span data-ttu-id="a59c0-119">El **\<Customer>** elemento también se incluye en el espacio de nombres de destino del esquema porque es un elemento global del esquema.</span><span class="sxs-lookup"><span data-stu-id="a59c0-119">The **\<Customer>** element is also included in the target namespace of the schema because it is a global element in the schema.</span></span>  
  
 <span data-ttu-id="a59c0-120">Ejecute la siguiente consulta XPath en el esquema:</span><span class="sxs-lookup"><span data-stu-id="a59c0-120">Execute the following XPath query against the schema:</span></span>  
  
```  
(/CO:Customer[@CustomerID=1)   
```  
  
 <span data-ttu-id="a59c0-121">La consulta XPath genera este documento de instancia (solo se muestran algunos pedidos):</span><span class="sxs-lookup"><span data-stu-id="a59c0-121">The XPath query generates this instance document (only a few of the orders are shown):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <y0:Customer xmlns:y0="urn:MyNamespace"   
      CustomerID="ALFKI" ContactName="Maria Anders">  
        <Order CustomerID="ALFKI" OrderID="10643" />   
        <Order CustomerID="ALFKI" OrderID="10692" />   
        ...  
  </y0:Customer>  
  </ROOT>  
```  
  
 <span data-ttu-id="a59c0-122">Este documento de instancia define el espacio de nombres urn: myNameSpace y le asocia un prefijo (Y0).</span><span class="sxs-lookup"><span data-stu-id="a59c0-122">This instance document defines the urn:MyNamespace namespace and associates a prefix (y0) to it.</span></span> <span data-ttu-id="a59c0-123">El prefijo solo se aplica al **\<Customer>** elemento global.</span><span class="sxs-lookup"><span data-stu-id="a59c0-123">The prefix is applied only to the **\<Customer>** global element.</span></span> <span data-ttu-id="a59c0-124">(El elemento es global porque se declara como elemento secundario del **\<xsd:schema>** elemento en el esquema).</span><span class="sxs-lookup"><span data-stu-id="a59c0-124">(The element is global because it is declared as a child of **\<xsd:schema>** element in the schema.)</span></span>  
  
 <span data-ttu-id="a59c0-125">El prefijo no se aplica a los elementos y atributos locales porque el valor de los atributos **elementFormDefault** y **attributeFormDefault** se establece en **"Unqualified"** en el esquema.</span><span class="sxs-lookup"><span data-stu-id="a59c0-125">The prefix is not applied to the local elements and attributes because the value of **elementFormDefault** and **attributeFormDefault** attributes is set to **"unqualified"** in the schema.</span></span> <span data-ttu-id="a59c0-126">Tenga en cuenta que el **\<Order>** elemento es local porque su declaración aparece como un elemento secundario del **\<complexType>** elemento que define el **\<CustomerType>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a59c0-126">Note that the **\<Order>** element is local because its declaration appears as a child of the **\<complexType>** element that defines the **\<CustomerType>** element.</span></span> <span data-ttu-id="a59c0-127">Del mismo modo, los atributos (**CustomerID**, **OrderID**y **ContactName**) son locales, no globales.</span><span class="sxs-lookup"><span data-stu-id="a59c0-127">Similarly, the attributes (**CustomerID**, **OrderID**, and **ContactName**) are local, not global.</span></span>  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="a59c0-128">Para crear un ejemplo funcional de este esquema</span><span class="sxs-lookup"><span data-stu-id="a59c0-128">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="a59c0-129">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a59c0-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="a59c0-130">Guarde el archivo como targetNameSpace.xml.</span><span class="sxs-lookup"><span data-stu-id="a59c0-130">Save the file as targetNameSpace.xml.</span></span>  
  
2.  <span data-ttu-id="a59c0-131">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a59c0-131">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="a59c0-132">Guarde el archivo como targetNameSpaceT.xml en el mismo directorio donde guardó targetNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="a59c0-132">Save the file as targetNameSpaceT.xml in the same directory where you saved targetNamespace.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="targetNamespace.xml"  
                       xmlns:CO="urn:MyNamespace" >  
        /CO:Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="a59c0-133">La consulta XPath de la plantilla devuelve el **\<Customer>** elemento para el cliente con un CustomerID de 1.</span><span class="sxs-lookup"><span data-stu-id="a59c0-133">The XPath query in the template returns the **\<Customer>** element for the customer with a CustomerID of 1.</span></span> <span data-ttu-id="a59c0-134">Observe que la consulta XPath especifica el prefijo de espacio de nombres del elemento en la consulta y no del atributo.</span><span class="sxs-lookup"><span data-stu-id="a59c0-134">Note that the XPath query specifies the namespace prefix for the element in the query and not for the attribute.</span></span> <span data-ttu-id="a59c0-135">(Los atributos locales, tal y como se especifican en el esquema, no se certifican).</span><span class="sxs-lookup"><span data-stu-id="a59c0-135">(Local attributes are not qualified, as specified in the schema.)</span></span>  
  
     <span data-ttu-id="a59c0-136">La ruta de acceso al directorio especificada para el esquema de asignación (targetNamespace.xml) es una ubicación relativa con respecto al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a59c0-136">The directory path specified for the mapping schema (targetNamespace.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="a59c0-137">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a59c0-137">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\targetNamepsace.xml"  
    ```  
  
3.  <span data-ttu-id="a59c0-138">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a59c0-138">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a59c0-139">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a59c0-139">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="a59c0-140">Si el esquema especifica atributos **elementFormDefault** y **attributeFormDefault** con el valor **"Qualified"**, el documento de instancia tendrá todos los elementos y atributos locales calificados.</span><span class="sxs-lookup"><span data-stu-id="a59c0-140">If the schema specifies **elementFormDefault** and **attributeFormDefault** attributes with value **"qualified"**, the instance document will have all of the local elements and attributes qualified.</span></span> <span data-ttu-id="a59c0-141">Puede cambiar el esquema anterior para incluir estos atributos en el **\<xsd:schema>** elemento y volver a ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a59c0-141">You can change the previous schema to include these attributes in the **\<xsd:schema>** element and execute the template again.</span></span> <span data-ttu-id="a59c0-142">Como los atributos están ahora certificados en la instancia, la consulta XPath cambiará e incluirá el prefijo de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a59c0-142">Because the attributes are now also qualified in the instance, the XPath query will change to include the namespace prefix.</span></span>  
  
 <span data-ttu-id="a59c0-143">Esta es la consulta XPath modificada:</span><span class="sxs-lookup"><span data-stu-id="a59c0-143">This is the revised XPath query:</span></span>  
  
```  
/CO:Customer[@CO:CustomerID=1]  
```  
  
 <span data-ttu-id="a59c0-144">Este el documento XML devuelto:</span><span class="sxs-lookup"><span data-stu-id="a59c0-144">This is the XML document that is returned:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <y0:Customer xmlns:y0="urn:MyNamespace" CustomerID="1" SalesPersonID="280">  
      <Order SalesOrderID="43860" CustomerID="1" />   
      <Order SalesOrderID="44501" CustomerID="1" />   
      <Order SalesOrderID="45283" CustomerID="1" />   
      <Order SalesOrderID="46042" CustomerID="1" />   
   </y0:Customer>  
</ROOT>  
```  
  
  
