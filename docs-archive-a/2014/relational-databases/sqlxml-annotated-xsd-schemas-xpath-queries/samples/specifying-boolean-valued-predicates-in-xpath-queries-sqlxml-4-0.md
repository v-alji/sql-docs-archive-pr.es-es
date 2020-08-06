---
title: Especificar predicados con valores booleanos en consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- nested predicates
- successive predicates
- predicates [SQLXML]
- top-level predicates
- Boolean-valued predicates
- multiple predicates
ms.assetid: 5f6e7219-6911-4bca-a54b-56b95e0b43dd
author: rothja
ms.author: jroth
ms.openlocfilehash: 56f2f94ec895c5b76382d5103ca9d518b78cc899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662751"
---
# <a name="specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="fc4de-102">Especificar los predicados con valores booleanos en las consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="fc4de-102">Specifying Boolean-Valued Predicates in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="fc4de-103">En los ejemplos siguientes se muestra cómo se especifican los predicados con valores booleanos en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="fc4de-103">The following examples show how Boolean-valued predicates are specified in XPath queries.</span></span> <span data-ttu-id="fc4de-104">Las consultas XPath de estos ejemplos se especifican en el esquema de asignación que se incluye en SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="fc4de-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="fc4de-105">Para obtener información acerca de este esquema de ejemplo, vea [ejemplo de esquema XSD anotado para los ejemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="fc4de-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fc4de-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="fc4de-106">Examples</span></span>  
  
### <a name="a-specify-multiple-predicates"></a><span data-ttu-id="fc4de-107">A.</span><span class="sxs-lookup"><span data-stu-id="fc4de-107">A.</span></span> <span data-ttu-id="fc4de-108">Especificar varios predicados</span><span class="sxs-lookup"><span data-stu-id="fc4de-108">Specify multiple predicates</span></span>  
 <span data-ttu-id="fc4de-109">La consulta XPath siguiente utiliza varios predicados para buscar la información de pedido para un determinado identificador de pedido e identificador de cliente:</span><span class="sxs-lookup"><span data-stu-id="fc4de-109">The following XPath query uses multiple predicates to find order information for a given order ID and a customer ID:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]/child::Order[attribute::OrderID="Ord-43860"]  
```  
  
 <span data-ttu-id="fc4de-110">Se puede especificar un acceso directo al eje `attribute` (@) y, puesto que el eje `child` es el valor predeterminado, puede omitirse en la consulta:</span><span class="sxs-lookup"><span data-stu-id="fc4de-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="fc4de-111">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="fc4de-111">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="fc4de-112">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="fc4de-112">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="fc4de-113">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="fc4de-113">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="fc4de-114">Cree la siguiente plantilla (BooleanValuedPredicatesA.xml) y guárdela en el directorio donde esté guardado SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="fc4de-114">Create the following template (BooleanValuedPredicatesA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="fc4de-115">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fc4de-115">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="fc4de-116">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc4de-116">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="fc4de-117">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fc4de-117">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="fc4de-118">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fc4de-118">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
     <span data-ttu-id="fc4de-119">Éste es el resultado:</span><span class="sxs-lookup"><span data-stu-id="fc4de-119">Here is the result:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
        <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-761" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-762" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-765" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-768" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-770" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
      </Order>  
    </ROOT>  
    ```  
  
### <a name="b-specify-successive-and-nested-predicates"></a><span data-ttu-id="fc4de-120">B.</span><span class="sxs-lookup"><span data-stu-id="fc4de-120">B.</span></span> <span data-ttu-id="fc4de-121">Especificar los predicados sucesivos y anidados</span><span class="sxs-lookup"><span data-stu-id="fc4de-121">Specify successive and nested predicates</span></span>  
 <span data-ttu-id="fc4de-122">La consulta siguiente muestra cómo utilizar los predicados sucesivos.</span><span class="sxs-lookup"><span data-stu-id="fc4de-122">The following query shows using successive predicates.</span></span> <span data-ttu-id="fc4de-123">La consulta devuelve todos los **\<Customer>** elementos secundarios del nodo de contexto que tienen un atributo **SalesPersonID** con un valor de 277 y un atributo **TerritoryID** con un valor de 3:</span><span class="sxs-lookup"><span data-stu-id="fc4de-123">The query returns all the **\<Customer>** child elements of the context node that have both a **SalesPersonID** attribute with a value of 277 and a **TerritoryID** attribute with a value of 3:</span></span>  
  
```  
/child::Customer[attribute::SalesPersonID="277"][attribute::TerritoryID="3"]  
```  
  
 <span data-ttu-id="fc4de-124">La consulta devuelve los **\<Customer>** elementos que cumplen las condiciones especificadas en los predicados.</span><span class="sxs-lookup"><span data-stu-id="fc4de-124">The query returns the **\<Customer>** elements that satisfy both the conditions specified in the predicates.</span></span>  
  
 <span data-ttu-id="fc4de-125">Se puede especificar un acceso directo al eje `attribute` (@) y, puesto que el eje `child` es el valor predeterminado, puede omitirse en la consulta:</span><span class="sxs-lookup"><span data-stu-id="fc4de-125">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@SalesPersonID="277"][@TerritoryID="3"]  
```  
  
 <span data-ttu-id="fc4de-126">La consulta XPath siguiente muestra el uso de los predicados anidados.</span><span class="sxs-lookup"><span data-stu-id="fc4de-126">The following XPath query illustrates the use of nested predicates.</span></span> <span data-ttu-id="fc4de-127">La consulta devuelve todos los **\<Customer>** elementos secundarios del nodo de contexto que incluyen los **\<Order>** elementos secundarios con al menos un **\<Order>** elemento que tiene un valor de atributo **SalesPersonID** de 2.</span><span class="sxs-lookup"><span data-stu-id="fc4de-127">The query returns all the **\<Customer>** child elements of the context node that include **\<Order>** child elements with at least one **\<Order>** element that has a **SalesPersonID** attribute value of 2.</span></span>  
  
```  
/Customer[Order[@SalesPersonID=2]]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="fc4de-128">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="fc4de-128">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="fc4de-129">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="fc4de-129">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="fc4de-130">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="fc4de-130">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="fc4de-131">Cree la siguiente plantilla (nestedSuccessive.xml) y guárdela en el mismo directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="fc4de-131">Create the following template (nestedSuccessive.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
             /Customer[@SalesPersonID="277"][@TerritoryID="3"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="fc4de-132">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fc4de-132">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="fc4de-133">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc4de-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="fc4de-134">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fc4de-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="fc4de-135">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fc4de-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="fc4de-136">A continuación figura un resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="fc4de-136">The following is a partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="22" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="22" CustomerType="S"   
            Orders="Ord-43874 Ord-44519 Ord-46989 Ord-48013 Ord-49130 Ord-50274 Ord-51807 Ord-57113 Ord-63162 Ord-69495">  
    <Order SalesOrderID="Ord-43874" SalesPersonID="277"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
                   OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    ...  
  </Customer>  
  <Customer CustomerID="39" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="39" CustomerType="S"   
            Orders="Ord-47428 Ord-48367 Ord-49529 Ord-50742 Ord-53591 Ord-59051 Ord-65301 Ord-71912">    <Order SalesOrderID="Ord-47428" SalesPersonID="277"   
           OrderDate="2002-09-01T00:00:00"   
           DueDate="2002-09-13T00:00:00"   
           ShipDate="2002-09-08T00:00:00">  
      <OrderDetail ProductID="Prod-759" UnitPrice="563.7528" OrderQty="2" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-769" UnitPrice="563.7528" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
### <a name="c-specify-a-top-level-predicate"></a><span data-ttu-id="fc4de-137">C.</span><span class="sxs-lookup"><span data-stu-id="fc4de-137">C.</span></span> <span data-ttu-id="fc4de-138">Especificar un predicado de nivel superior</span><span class="sxs-lookup"><span data-stu-id="fc4de-138">Specify a top-level predicate</span></span>  
 <span data-ttu-id="fc4de-139">La consulta siguiente devuelve los **\<Customer>** nodos de elemento secundario del nodo de contexto que tienen elementos **\<Order>** secundarios.</span><span class="sxs-lookup"><span data-stu-id="fc4de-139">The following query returns the **\<Customer>** child element nodes of the context node that have **\<Order>** element children.</span></span> <span data-ttu-id="fc4de-140">La consulta prueba la ruta de acceso de la ubicación como el predicado de nivel superior:</span><span class="sxs-lookup"><span data-stu-id="fc4de-140">The query tests the location path as the top-level predicate:</span></span>  
  
```  
/child::Customer[child::Order]  
```  
  
 <span data-ttu-id="fc4de-141">El eje `child` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fc4de-141">The `child` axis is the default.</span></span> <span data-ttu-id="fc4de-142">Por lo tanto, la consulta puede especificarse como:</span><span class="sxs-lookup"><span data-stu-id="fc4de-142">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="fc4de-143">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="fc4de-143">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="fc4de-144">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="fc4de-144">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="fc4de-145">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="fc4de-145">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="fc4de-146">Cree la siguiente plantilla (TopLevelPredicate.xml) y guárdela en el mismo directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="fc4de-146">Create the following template (TopLevelPredicate.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="fc4de-147">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fc4de-147">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="fc4de-148">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fc4de-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="fc4de-149">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fc4de-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="fc4de-150">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="fc4de-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="fc4de-151">Este es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="fc4de-151">Here is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280" TerritoryID="1" AccountNumber="1" CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    <Order SalesOrderID="Ord-44501" SalesPersonID="280" OrderDate="2001-11-01T00:00:00" DueDate="2001-11-13T00:00:00" ShipDate="2001-11-08T00:00:00">  
      <OrderDetail ProductID="Prod-725" UnitPrice="226.8571" OrderQty="3" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-726" UnitPrice="226.8571" OrderQty="2" UnitPriceDiscount="0" />   
      ...  
    </Order>    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
  
