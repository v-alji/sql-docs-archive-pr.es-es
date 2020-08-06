---
title: 'Identificar columnas de clave mediante SQL: Key-Fields (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nesting XML results
- proper nesting in results [SQLXML]
- sql:key-fields
- XSD schemas [SQLXML], key columns
- identifying key columns [SQLXML]
- annotated XSD schemas, key columns
- key columns [SQLXML]
- relationships [SQLXML], key columns
- hierarchical relationships [SQLXML]
- key-fields annotation
ms.assetid: 1a5ad868-8602-45c4-913d-6fbb837eebb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ab12b34874a54bad2e08a96d08ebd0cc994f946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750562"
---
# <a name="identifying-key-columns-using-sqlkey-fields-sqlxml-40"></a><span data-ttu-id="7177e-102">Identificar columnas de clave mediante sql:key-fields (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="7177e-102">Identifying Key Columns Using sql:key-fields (SQLXML 4.0)</span></span>
  <span data-ttu-id="7177e-103">Cuando se especifica una consulta XPath en un esquema XSD, la información de claves resulta necesaria en la mayoría de los casos para obtener un anidamiento correcto en el resultado.</span><span class="sxs-lookup"><span data-stu-id="7177e-103">When an XPath query is specified against an XSD schema, key information is required in most cases to obtain proper nesting in the result.</span></span> <span data-ttu-id="7177e-104">Especificar la anotación `sql:key-fields` es una forma de asegurarse de que se genera la jerarquía correcta.</span><span class="sxs-lookup"><span data-stu-id="7177e-104">Specifying the `sql:key-fields` annotation is a way of ensuring that the appropriate hierarchy is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7177e-105">Para garantizar un anidamiento correcto, es recomendable que especifique `sql:key-fields` para los elementos que se asignan a tablas.</span><span class="sxs-lookup"><span data-stu-id="7177e-105">To ensure proper nesting, it is recommended that you specify `sql:key-fields` for elements that map to tables.</span></span> <span data-ttu-id="7177e-106">El código XML generado distingue la ordenación del conjunto de resultados subyacente.</span><span class="sxs-lookup"><span data-stu-id="7177e-106">The XML produced is sensitive to the ordering of the underlying result set.</span></span> <span data-ttu-id="7177e-107">Si no se especifica `sql:key-fields`, es posible que el código XML generado no tenga un formato correcto.</span><span class="sxs-lookup"><span data-stu-id="7177e-107">If `sql:key-fields` is not specified, the XML generated might not be formed properly.</span></span>  
  
 <span data-ttu-id="7177e-108">El valor de `sql:key-fields` identifica las columnas que identifican de forma única las filas de la relación.</span><span class="sxs-lookup"><span data-stu-id="7177e-108">The value of `sql:key-fields` identifies the column(s) that uniquely identify the rows in the relation.</span></span> <span data-ttu-id="7177e-109">Si es necesaria más de una columna para identificar de forma única una fila, los valores de columna se delimitan mediante espacios.</span><span class="sxs-lookup"><span data-stu-id="7177e-109">If more than one column is required to uniquely identify a row, the column values are delimited by spaces.</span></span>  
  
 <span data-ttu-id="7177e-110">Debe utilizar la `sql:key-fields` anotación cuando un elemento contiene un **\<sql:relationship>** que se define entre el elemento y un elemento secundario, pero no proporciona la clave principal de la tabla que se especifica en el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="7177e-110">You must use the `sql:key-fields` annotation when an element contains a **\<sql:relationship>** that is defined between the element and a child element but does not provide the primary key of the table that is specified in the parent element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7177e-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7177e-111">Examples</span></span>  
 <span data-ttu-id="7177e-112">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="7177e-112">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="7177e-113">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="7177e-113">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-producing-the-appropriate-nesting-when-sqlrelationship-does-not-provide-sufficient-information"></a><span data-ttu-id="7177e-114">A.</span><span class="sxs-lookup"><span data-stu-id="7177e-114">A.</span></span> <span data-ttu-id="7177e-115">Producir el anidamiento adecuado cuando \<sql:relationship> no proporciona información suficiente</span><span class="sxs-lookup"><span data-stu-id="7177e-115">Producing the appropriate nesting when \<sql:relationship> does not provide sufficient information</span></span>  
 <span data-ttu-id="7177e-116">En este ejemplo se muestra dónde debe especificarse `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="7177e-116">This example shows where `sql:key-fields` must be specified.</span></span>  
  
 <span data-ttu-id="7177e-117">Fíjese en el siguiente esquema.</span><span class="sxs-lookup"><span data-stu-id="7177e-117">Consider the following schema.</span></span> <span data-ttu-id="7177e-118">El esquema especifica una jerarquía entre los **\<Order>** **\<Customer>** elementos y en los que el **\<Order>** elemento es el elemento primario y el **\<Customer>** elemento es un elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="7177e-118">The schema specifies a hierarchy between the **\<Order>** and **\<Customer>** elements in which the **\<Order>** element is the parent and the **\<Customer>** element is a child.</span></span>  
  
 <span data-ttu-id="7177e-119">La **\<sql:relationship>** etiqueta se usa para especificar la relación de elementos primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="7177e-119">The **\<sql:relationship>** tag is used to specify the parent-child relationship.</span></span> <span data-ttu-id="7177e-120">Identifica CustomerID en la tabla Sales.SalesOrderHeader como la clave primaria que hace referencia a la clave secundaria CustomerID en la tabla Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="7177e-120">It identifies CustomerID in the Sales.SalesOrderHeader table as the parent key that refers to the CustomerID child key in the Sales.Customer table.</span></span> <span data-ttu-id="7177e-121">La información proporcionada en **\<sql:relationship>** no es suficiente para identificar de forma única las filas de la tabla primaria (sales. SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="7177e-121">The information provided in **\<sql:relationship>** is not sufficient to uniquely identify rows in the parent table (Sales.SalesOrderHeader).</span></span> <span data-ttu-id="7177e-122">Por lo tanto, sin la anotación `sql:key-fields`, la jerarquía que se genera es inexacta.</span><span class="sxs-lookup"><span data-stu-id="7177e-122">Therefore, without the `sql:key-fields` annotation, the hierarchy that is generated is inaccurate.</span></span>  
  
 <span data-ttu-id="7177e-123">Con `sql:key-fields` especificado en **\<Order>** , la anotación identifica de forma única las filas de la tabla primaria (sales. SalesOrderHeader) y sus elementos secundarios aparecen debajo de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="7177e-123">With `sql:key-fields` specified on **\<Order>**, the annotation uniquely identifies the rows in the parent (Sales.SalesOrderHeader table), and its child elements appear below its parent.</span></span>  
  
 <span data-ttu-id="7177e-124">Éste es el esquema:</span><span class="sxs-lookup"><span data-stu-id="7177e-124">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrdCust"  
        parent="Sales.SalesOrderHeader"  
        parent-key="CustomerID"  
        child="Sales.Customer"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
               sql:key-fields="SalesOrderID">  
   <xsd:complexType>  
     <xsd:sequence>  
     <xsd:element name="Customer" sql:relation="Sales.Customer"   
                       sql:relationship="OrdCust"  >  
       <xsd:complexType>  
         <xsd:attribute name="CustID" sql:field="CustomerID" />  
         <xsd:attribute name="SoldBy" sql:field="SalesPersonID" />  
       </xsd:complexType>  
     </xsd:element>  
     </xsd:sequence>  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name= "CustomerID" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="7177e-125">Para crear un ejemplo funcional de este esquema</span><span class="sxs-lookup"><span data-stu-id="7177e-125">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="7177e-126">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7177e-126">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="7177e-127">Guarde el archivo como KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="7177e-127">Save the file as KeyFields1.xml.</span></span>  
  
2.  <span data-ttu-id="7177e-128">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7177e-128">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="7177e-129">Guarde el archivo como KeyFields1T.xml en el mismo directorio donde guardó KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="7177e-129">Save the file as KeyFields1T.xml in the same directory where you saved KeyFields1.xml.</span></span> <span data-ttu-id="7177e-130">La consulta XPath de la plantilla devuelve todos los **\<Order>** elementos cuyo CustomerID es menor que 3.</span><span class="sxs-lookup"><span data-stu-id="7177e-130">The XPath query in the template returns all the **\<Order>** elements with a CustomerID of less than 3.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="KeyFields1.xml">  
            /Order[@CustomerID < 3]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="7177e-131">La ruta de acceso al directorio especificada para el esquema de asignación (KeyFields1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7177e-131">The directory path specified for the mapping schema (KeyFields1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="7177e-132">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7177e-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields1.xml"  
    ```  
  
3.  <span data-ttu-id="7177e-133">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7177e-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="7177e-134">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7177e-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="7177e-135">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="7177e-135">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
    <Order SalesOrderID="43860" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="44501" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="45283" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    .....  
</ROOT>  
```  
  
### <a name="b-specifying-sqlkey-fields-to-produce-proper-nesting-in-the-result"></a><span data-ttu-id="7177e-136">B.</span><span class="sxs-lookup"><span data-stu-id="7177e-136">B.</span></span> <span data-ttu-id="7177e-137">Especificar sql:key-fields para generar un anidamiento correcto del resultado</span><span class="sxs-lookup"><span data-stu-id="7177e-137">Specifying sql:key-fields to produce proper nesting in the result</span></span>  
 <span data-ttu-id="7177e-138">En el esquema siguiente, no se ha especificado ninguna jerarquía mediante **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="7177e-138">In the following schema, there is no hierarchy specified using **\<sql:relationship>**.</span></span> <span data-ttu-id="7177e-139">El esquema todavía requiere que se especifique la anotación `sql:key-fields` para identificar de forma única a empleados en la tabla HumanResources.Employee.</span><span class="sxs-lookup"><span data-stu-id="7177e-139">The schema still requires specifying the `sql:key-fields` annotation to uniquely identify employees in the HumanResources.Employee table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="HumanResources.Employee" sql:key-fields="EmployeeID" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Title">  
          <xsd:complexType>  
            <xsd:simpleContent>  
              <xsd:extension base="xsd:string">  
                 <xsd:attribute name="EmployeeID" type="xsd:integer" />  
              </xsd:extension>  
            </xsd:simpleContent>  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="7177e-140">Para crear un ejemplo funcional de este esquema</span><span class="sxs-lookup"><span data-stu-id="7177e-140">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="7177e-141">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7177e-141">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="7177e-142">Guarde el archivo como KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="7177e-142">Save the file as KeyFields2.xml.</span></span>  
  
2.  <span data-ttu-id="7177e-143">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7177e-143">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="7177e-144">Guarde el archivo como KeyFields2T.xml en el mismo directorio donde guardó KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="7177e-144">Save the file as KeyFields2T.xml in the same directory where you saved KeyFields2.xml.</span></span> <span data-ttu-id="7177e-145">La consulta XPath de la plantilla devuelve todos los **\<HumanResources.Employee>** elementos:</span><span class="sxs-lookup"><span data-stu-id="7177e-145">The XPath query in the template returns all the **\<HumanResources.Employee>** elements:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="KeyFields2.xml">  
        /HumanResources.Employee  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="7177e-146">La ruta de acceso al directorio especificada para el esquema de asignación (KeyFields2.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7177e-146">The directory path specified for the mapping schema (KeyFields2.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="7177e-147">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7177e-147">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields2.xml"  
    ```  
  
3.  <span data-ttu-id="7177e-148">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7177e-148">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="7177e-149">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7177e-149">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="7177e-150">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="7177e-150">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <HumanResources.Employee>  
    <Title EmployeeID="1">Production Technician - WC60</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="2">Marketing Assistant</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="3">Engineering Manager</Title>   
  </HumanResources.Employee>  
  ...  
</ROOT>  
```  
  
  
