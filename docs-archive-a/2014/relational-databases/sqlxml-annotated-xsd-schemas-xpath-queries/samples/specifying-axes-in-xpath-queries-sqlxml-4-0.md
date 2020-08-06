---
title: Especificar ejes en consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- context node [SQLXML]
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- axes [SQLXML]
ms.assetid: d17b8278-da58-4576-95b4-7a92772566d8
author: rothja
ms.author: jroth
ms.openlocfilehash: f6f17404ea109bb0e687f9116b61025bbc411008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662755"
---
# <a name="specifying-axes-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="65a98-102">Especificar ejes en consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="65a98-102">Specifying Axes in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="65a98-103">Los ejemplos siguientes muestran cómo se especifican los ejes en las consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="65a98-103">The following examples show how axes are specified in XPath queries.</span></span>  
  
 <span data-ttu-id="65a98-104">Las consultas XPath de estos ejemplos se especifican en el esquema de asignación que se incluye en SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="65a98-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="65a98-105">Para obtener información acerca de este esquema de ejemplo, vea [ejemplo de esquema XSD anotado para los ejemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="65a98-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="65a98-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="65a98-106">Examples</span></span>  
  
### <a name="a-retrieve-child-elements-of-the-context-node"></a><span data-ttu-id="65a98-107">A.</span><span class="sxs-lookup"><span data-stu-id="65a98-107">A.</span></span> <span data-ttu-id="65a98-108">Recuperar elementos secundarios del nodo de contexto</span><span class="sxs-lookup"><span data-stu-id="65a98-108">Retrieve child elements of the context node</span></span>  
 <span data-ttu-id="65a98-109">La consulta XPath siguiente selecciona todos los **\<Contact>** elementos secundarios del nodo de contexto:</span><span class="sxs-lookup"><span data-stu-id="65a98-109">The following XPath query selects all the **\<Contact>** child elements of the context node:</span></span>  
  
```  
/child::Contact  
```  
  
 <span data-ttu-id="65a98-110">En la consulta, `child` es el eje y `Contact` es la prueba de nodo (true si `Contact` es un **\<element>** nodo, porque \<element> es el tipo de nodo principal asociado al `child` eje).</span><span class="sxs-lookup"><span data-stu-id="65a98-110">In the query, `child` is the axis and `Contact` is the node test (TRUE if `Contact` is an **\<element>** node, because \<element> is the primary node type associated with the `child` axis).</span></span>  
  
 <span data-ttu-id="65a98-111">El eje `child` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="65a98-111">The `child` axis is the default.</span></span> <span data-ttu-id="65a98-112">Por tanto, la consulta puede escribirse como:</span><span class="sxs-lookup"><span data-stu-id="65a98-112">Therefore, the query can be written as:</span></span>  
  
```  
/Contact  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="65a98-113">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="65a98-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="65a98-114">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="65a98-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="65a98-115">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="65a98-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="65a98-116">Cree la siguiente plantilla (XPathAxesSampleA.xml) y guárdela en el mismo directorio en el que esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="65a98-116">Create the following template (XPathAxesSampleA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="65a98-117">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="65a98-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="65a98-118">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="65a98-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="65a98-119">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="65a98-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="65a98-120">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65a98-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="65a98-121">Este es el conjunto parcial de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="65a98-121">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Contact ContactID="1" LastName="Achong" FirstName="Gustavo" Title="Mr." />   
  <Contact ContactID="2" LastName="Abel" FirstName="Catherine" Title="Ms." />   
  <Contact ContactID="3" LastName="Abercrombie" FirstName="Kim" Title="Ms." />   
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />  
  ...  
</ROOT>  
```  
  
### <a name="b-retrieve-grandchildren-of-the-context-node"></a><span data-ttu-id="65a98-122">B.</span><span class="sxs-lookup"><span data-stu-id="65a98-122">B.</span></span> <span data-ttu-id="65a98-123">Recuperar descendientes del nodo de contexto</span><span class="sxs-lookup"><span data-stu-id="65a98-123">Retrieve grandchildren of the context node</span></span>  
 <span data-ttu-id="65a98-124">La consulta XPath siguiente selecciona todos los elementos **\<Order>** secundarios del elemento **\<Customer>** secundarios del nodo de contexto:</span><span class="sxs-lookup"><span data-stu-id="65a98-124">The following XPath query selects all the **\<Order>** element children of the **\<Customer>** element children of the context node:</span></span>  
  
```  
/child::Customer/child::Order  
```  
  
 <span data-ttu-id="65a98-125">En la consulta, `child` es el eje y `Customer` y `Order` son las pruebas de nodo (estas pruebas de nodo son verdaderas si Customer y Order son **\<element>** nodos, porque el **\<element>** nodo es el nodo principal del `child` eje).</span><span class="sxs-lookup"><span data-stu-id="65a98-125">In the query, `child` is the axis and `Customer` and `Order` are the node tests (these node tests are TRUE if Customer and Order are **\<element>** nodes, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="65a98-126">Para cada nodo que coincide con **\<Customer>** , los nodos que coinciden con **\<Orders>** se agregan al resultado.</span><span class="sxs-lookup"><span data-stu-id="65a98-126">For each node matching **\<Customer>**, the nodes matching **\<Orders>** are added to the result.</span></span> <span data-ttu-id="65a98-127">Solo **\<Order>** se devuelve en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="65a98-127">Only **\<Order>** is returned in the result set.</span></span>  
  
 <span data-ttu-id="65a98-128">El eje `child` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="65a98-128">The `child` axis is the default.</span></span> <span data-ttu-id="65a98-129">Por lo tanto, la consulta puede especificarse como:</span><span class="sxs-lookup"><span data-stu-id="65a98-129">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="65a98-130">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="65a98-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="65a98-131">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="65a98-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="65a98-132">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="65a98-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="65a98-133">Cree la plantilla siguiente (XPathAxesSampleB.xml) y guárdela en el directorio donde:</span><span class="sxs-lookup"><span data-stu-id="65a98-133">Create the following template (XPathAxesSampleB.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="65a98-134">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="65a98-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="65a98-135">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="65a98-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="65a98-136">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="65a98-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="65a98-137">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65a98-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="65a98-138">Este es el conjunto parcial de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="65a98-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</ROOT>  
```  
  
 <span data-ttu-id="65a98-139">Si la consulta XPath se especifica como `Customer/Order/OrderDetail` , de cada nodo que coincida con **\<Customer>** la consulta navega a sus **\<Order>** elementos.</span><span class="sxs-lookup"><span data-stu-id="65a98-139">If the XPath query is specified as `Customer/Order/OrderDetail`, from each node matching **\<Customer>** the query navigates to its **\<Order>** elements.</span></span> <span data-ttu-id="65a98-140">Y para cada nodo coincidente **\<Order>** , la consulta agrega los nodos **\<OrderDetail>** al resultado.</span><span class="sxs-lookup"><span data-stu-id="65a98-140">And for each node matching **\<Order>**, the query adds the nodes **\<OrderDetail>** to the result.</span></span> <span data-ttu-id="65a98-141">Solo **\<OrderDetail>** se devuelve en el conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="65a98-141">Only **\<OrderDetail>** is returned in the result set.</span></span>  
  
### <a name="c-use--to-specify-the-parent-axis"></a><span data-ttu-id="65a98-142">C.</span><span class="sxs-lookup"><span data-stu-id="65a98-142">C.</span></span> <span data-ttu-id="65a98-143">Usar .</span><span class="sxs-lookup"><span data-stu-id="65a98-143">Use ..</span></span> <span data-ttu-id="65a98-144">para especificar el eje primario</span><span class="sxs-lookup"><span data-stu-id="65a98-144">to specify the parent axis</span></span>  
 <span data-ttu-id="65a98-145">La consulta siguiente recupera todos los **\<Order>** elementos con un elemento primario **\<Customer>** con un valor de atributo **CustomerID** de 1.</span><span class="sxs-lookup"><span data-stu-id="65a98-145">The following query retrieves all the **\<Order>** elements with a parent **\<Customer>** element with a **CustomerID** attribute value of 1.</span></span> <span data-ttu-id="65a98-146">La consulta usa el `child` eje en el predicado para buscar el elemento primario del **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="65a98-146">The query uses the `child` axis in the predicate to find the parent of the **\<Order>** element.</span></span>  
  
```  
/child::Customer/child::Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="65a98-147">El eje `child` es el eje predeterminado.</span><span class="sxs-lookup"><span data-stu-id="65a98-147">The `child` axis is the default axis.</span></span> <span data-ttu-id="65a98-148">Por lo tanto, la consulta puede especificarse como:</span><span class="sxs-lookup"><span data-stu-id="65a98-148">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="65a98-149">La consulta XPath es equivalente a:</span><span class="sxs-lookup"><span data-stu-id="65a98-149">The XPath query is equivalent to:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="65a98-150">La consulta XPath `/Order[../@CustomerID="1"]` devolverá un error porque no hay ningún elemento primario de **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="65a98-150">The XPath query `/Order[../@CustomerID="1"]` will return an error because there is no parent of **\<Order>**.</span></span> <span data-ttu-id="65a98-151">Aunque puede haber elementos en el esquema de asignación que contengan **\<Order>** , el XPath no comenzó en ninguno de ellos; por lo tanto, **\<Order>** se considera que es el tipo de elemento de nivel superior del documento.</span><span class="sxs-lookup"><span data-stu-id="65a98-151">Although there may be elements in the mapping schema that contain **\<Order>**, the XPath did not begin at any of them; consequently, **\<Order>** is considered to be the top-level element type in the document.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="65a98-152">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="65a98-152">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="65a98-153">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="65a98-153">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="65a98-154">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="65a98-154">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="65a98-155">Cree la plantilla siguiente (XPathAxesSampleC.xml) y guárdela en el directorio donde:</span><span class="sxs-lookup"><span data-stu-id="65a98-155">Create the following template (XPathAxesSampleC.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order[../@CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="65a98-156">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="65a98-156">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="65a98-157">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="65a98-157">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="65a98-158">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="65a98-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="65a98-159">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65a98-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="65a98-160">Este es el conjunto parcial de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="65a98-160">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</Order>  
</ROOT>  
```  
  
### <a name="d-specify-the-attribute-axis"></a><span data-ttu-id="65a98-161">D.</span><span class="sxs-lookup"><span data-stu-id="65a98-161">D.</span></span> <span data-ttu-id="65a98-162">Especificar el eje de atributo</span><span class="sxs-lookup"><span data-stu-id="65a98-162">Specify the attribute axis</span></span>  
 <span data-ttu-id="65a98-163">La consulta XPath siguiente selecciona todos los **\<Customer>** elementos secundarios del nodo de contexto con un valor de atributo **CustomerID** de 1:</span><span class="sxs-lookup"><span data-stu-id="65a98-163">The following XPath query selects all the **\<Customer>** child elements of the context node with a **CustomerID** attribute value of 1:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]  
```  
  
 <span data-ttu-id="65a98-164">En el predicado `attribute::CustomerID` , `attribute` es el eje y `CustomerID` es la prueba de nodo (si `CustomerID` es un atributo, la prueba de nodo es true, porque el **\<attribute>** nodo es el nodo principal del `attribute` eje).</span><span class="sxs-lookup"><span data-stu-id="65a98-164">In the predicate `attribute::CustomerID`, `attribute` is the axis and `CustomerID` is the node test (if `CustomerID` is an attribute the node test is TRUE, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span>  
  
 <span data-ttu-id="65a98-165">Se puede especificar un acceso directo al eje `attribute` (@) y, puesto que el eje `child` es el eje predeterminado, puede omitirse en la consulta:</span><span class="sxs-lookup"><span data-stu-id="65a98-165">A shortcut to the `attribute` axis (@) can be specified, and because `child` is the default axis, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="65a98-166">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="65a98-166">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="65a98-167">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="65a98-167">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="65a98-168">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="65a98-168">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="65a98-169">Cree la siguiente plantilla (XPathAxesSampleD.xml) y guárdela en el mismo directorio en el que esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="65a98-169">Create the following template (XPathAxesSampleD.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        child::Customer[attribute::CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="65a98-170">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="65a98-170">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="65a98-171">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="65a98-171">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="65a98-172">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="65a98-172">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="65a98-173">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="65a98-173">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="65a98-174">Este es el conjunto parcial de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="65a98-174">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280"   
            TerritoryID="1" AccountNumber="1"   
            CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
       <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
                    OrderQty="1" UnitPriceDiscount="0" />   
      ...   
    </Order>  
   ...  
  </Customer>  
</ROOT>  
```  
  
  
