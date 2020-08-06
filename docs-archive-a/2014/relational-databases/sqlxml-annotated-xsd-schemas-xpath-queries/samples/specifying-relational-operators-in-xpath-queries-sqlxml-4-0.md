---
title: Especificar operadores relacionales en consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], relational operators
- relational operators [SQLXML]
- XPath operators [SQLXML]
- operators [SQLXML]
ms.assetid: 177a0eb2-11ef-4459-a317-485a433ee769
author: rothja
ms.author: jroth
ms.openlocfilehash: 50d59ebd3a776386c61f4c3a8a1e892d30981d1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662744"
---
# <a name="specifying-relational-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="32bf8-102">Especificar operadores relacionales en consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="32bf8-102">Specifying Relational Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="32bf8-103">En los siguientes ejemplos se muestra cómo especificar operadores relacionales en consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="32bf8-103">The following examples show how relational operators are specified in XPath queries.</span></span> <span data-ttu-id="32bf8-104">Las consultas XPath de estos ejemplos se especifican en el esquema de asignación que se incluye en SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="32bf8-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="32bf8-105">Para obtener información acerca de este esquema de ejemplo, vea [ejemplo de esquema XSD anotado para los ejemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="32bf8-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="32bf8-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="32bf8-106">Examples</span></span>  
  
### <a name="a-specify-relational-operator"></a><span data-ttu-id="32bf8-107">A.</span><span class="sxs-lookup"><span data-stu-id="32bf8-107">A.</span></span> <span data-ttu-id="32bf8-108">Especificar un operador relacional</span><span class="sxs-lookup"><span data-stu-id="32bf8-108">Specify relational operator</span></span>  
 <span data-ttu-id="32bf8-109">Esta consulta XPath devuelve los elementos secundarios del **\<Customer>** elemento donde el valor del atributo **CustomerID** es "1" y donde los **\<Order>** elementos secundarios contienen un **\<OrderDetail>** elemento secundario con un atributo **OrderQty** con un valor mayor que 3:</span><span class="sxs-lookup"><span data-stu-id="32bf8-109">This XPath query returns the child elements of the **\<Customer>** element where the **CustomerID** attribute value is "1" and where any child **\<Order>** elements contain an **\<OrderDetail>** child with a **OrderQty** attribute with a value greater than 3:</span></span>  
  
```  
/child::Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
 <span data-ttu-id="32bf8-110">El predicado especificado en los corchetes filtra los **\<Customer>** elementos.</span><span class="sxs-lookup"><span data-stu-id="32bf8-110">The predicate specified in the brackets filters the **\<Customer>** elements.</span></span> <span data-ttu-id="32bf8-111">Solo **\<Customer>** se devuelven los elementos que tienen al menos un **\<OrderDetail>** descendiente con un valor de atributo OrderQty mayor que 3.</span><span class="sxs-lookup"><span data-stu-id="32bf8-111">Only the **\<Customer>** elements that have at least one **\<OrderDetail>** grandchild with a OrderQty attribute value greater than 3 are returned.</span></span>  
  
 <span data-ttu-id="32bf8-112">El eje `child` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="32bf8-112">The `child` axis is the default.</span></span> <span data-ttu-id="32bf8-113">Por lo tanto, la consulta puede especificarse como:</span><span class="sxs-lookup"><span data-stu-id="32bf8-113">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="32bf8-114">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="32bf8-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="32bf8-115">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="32bf8-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="32bf8-116">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="32bf8-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="32bf8-117">Cree la siguiente plantilla (SpecifyRelationalA.xml) y guárdela en el mismo directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="32bf8-117">Create the following template (SpecifyRelationalA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="32bf8-118">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="32bf8-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="32bf8-119">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32bf8-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="32bf8-120">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="32bf8-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="32bf8-121">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="32bf8-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="32bf8-122">Éste es el conjunto de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="32bf8-122">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-760" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-766" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-757" UnitPrice="1049.7528" OrderQty="4" UnitPriceDiscount="0" />   
</ROOT>  
```  
  
### <a name="b-specify-relational-operator-in-the-xpath-query-and-use-boolean-function-to-compare-the-result"></a><span data-ttu-id="32bf8-123">B.</span><span class="sxs-lookup"><span data-stu-id="32bf8-123">B.</span></span> <span data-ttu-id="32bf8-124">Especificar el operador relacional de la consulta XPath y usar una función booleana para comparar el resultado</span><span class="sxs-lookup"><span data-stu-id="32bf8-124">Specify relational operator in the XPath query and use Boolean function to compare the result</span></span>  
 <span data-ttu-id="32bf8-125">Esta consulta devuelve todos los **\<Order>** elementos secundarios del nodo de contexto que tienen un valor de atributo **SalesPersonID** inferior a 270:</span><span class="sxs-lookup"><span data-stu-id="32bf8-125">This query returns all the **\<Order>** element children of the context node that have an **SalesPersonID** attribute value that is less than 270:</span></span>  
  
```  
/child::Customer/child::Order[(attribute::SalesPersonID < 270)=true()]  
```  
  
 <span data-ttu-id="32bf8-126">Se puede especificar un acceso directo al eje `attribute` (@) y, puesto que el eje `child` es el valor predeterminado, puede omitirse en la consulta:</span><span class="sxs-lookup"><span data-stu-id="32bf8-126">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer/Order[(@SalesPersonID < 270)=true()]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="32bf8-127">Cuando se especifica esta consulta en una plantilla, el carácter de < debe ser una entidad codificada porque el carácter < tiene un significado especial en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="32bf8-127">When this query is specified in a template, the < character must be entity encoded because the < character has special meaning in an XML document.</span></span> <span data-ttu-id="32bf8-128">En una plantilla, use `<` para especificar el carácter <.</span><span class="sxs-lookup"><span data-stu-id="32bf8-128">In a template, use `<` to specify the < character.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="32bf8-129">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="32bf8-129">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="32bf8-130">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="32bf8-130">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="32bf8-131">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="32bf8-131">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="32bf8-132">Cree la siguiente plantilla (SpecifyRelationalB.xml) y guárdela en el directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="32bf8-132">Create the following template (SpecifyRelationalB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="SampleSchema1.xml">  
            /Customer/Order[(@SalesPersonID<270)=true()]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="32bf8-133">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="32bf8-133">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="32bf8-134">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32bf8-134">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="32bf8-135">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="32bf8-135">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="32bf8-136">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="32bf8-136">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="32bf8-137">Este es el conjunto parcial de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="32bf8-137">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-46613" SalesPersonID="268"   
         OrderDate="2002-07-01T00:00:00"   
         DueDate="2002-07-13T00:00:00"   
         ShipDate="2002-07-08T00:00:00">  
    <OrderDetail ProductID="Prod-739" UnitPrice="917.9363"   
                 OrderQty="2" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-779" UnitPrice="1491.4221"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-825" UnitPrice="242.1391"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  <Order SalesOrderID="Ord-71919" SalesPersonID="268"  
         OrderDate="2004-06-01T00:00:00"   
         DueDate="2004-06-13T00:00:00"   
         ShipDate="2004-06-08T00:00:00">  
    <OrderDetail ProductID="Prod-961" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-965" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-966" UnitPrice="1716.5304"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  ...  
</ROOT>  
```  
  
  
