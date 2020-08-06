---
title: Especificar operadores aritméticos en consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- arithmetic operators
- XPath operators [SQLXML]
- XPath queries [SQLXML], arithmetic operators
- operators [SQLXML]
ms.assetid: fdfbc87d-759f-4abc-acf5-a21de01f78d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 904f3b920029d45d1b72641a19e2ac07befd4def
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662756"
---
# <a name="specifying-arithmetic-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="4488d-102">Especificar operadores aritméticos en consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4488d-102">Specifying Arithmetic Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="4488d-103">En el ejemplo siguiente se muestra cómo se especifican los operadores aritméticos en consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="4488d-103">The following example shows how arithmetic operators are specified in XPath queries.</span></span> <span data-ttu-id="4488d-104">La consulta XPath de este ejemplo se especifica en el esquema de asignación que se incluye en SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="4488d-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="4488d-105">Para obtener información acerca de este esquema de ejemplo, vea [ejemplo de esquema XSD anotado para los ejemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4488d-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4488d-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4488d-106">Examples</span></span>  
  
### <a name="a-specify-the--arithmetic-operator"></a><span data-ttu-id="4488d-107">A.</span><span class="sxs-lookup"><span data-stu-id="4488d-107">A.</span></span> <span data-ttu-id="4488d-108">Especificar el operador aritmético \*</span><span class="sxs-lookup"><span data-stu-id="4488d-108">Specify the \* arithmetic operator</span></span>  
 <span data-ttu-id="4488d-109">Esta consulta XPath devuelve **\<OrderDetail>** los elementos que satisfacen el predicado especificado:</span><span class="sxs-lookup"><span data-stu-id="4488d-109">This XPath query returns **\<OrderDetail>** elements that satisfy the predicate specified:</span></span>  
  
```  
/child::OrderDetail[@UnitPrice * @Quantity = 12.350]  
```  
  
 <span data-ttu-id="4488d-110">En la consulta, `child` es el eje y `OrderDetail` es la prueba de nodo (true si **OrderDetail** es **\<element node>** , porque el **\<element>** nodo es el nodo principal del `child` eje).</span><span class="sxs-lookup"><span data-stu-id="4488d-110">In the query, `child` is the axis and `OrderDetail` is the node test (TRUE if **OrderDetail** is an **\<element node>**, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="4488d-111">En todos los **\<OrderDetail>** nodos de elemento, se aplica la prueba del predicado y solo se devuelven los nodos que satisfacen la condición.</span><span class="sxs-lookup"><span data-stu-id="4488d-111">For all the **\<OrderDetail>** element nodes, the test in the predicate is applied, and only those nodes that satisfy the condition are returned.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4488d-112">Los números en XPath son números de punto flotante de precisión doble y la comparación de números de punto flotante, como los del ejemplo, hace que éstos se redondeen.</span><span class="sxs-lookup"><span data-stu-id="4488d-112">The numbers in XPath are double-precision floating-point numbers, and comparing floating-point numbers as in the example causes rounding.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="4488d-113">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="4488d-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="4488d-114">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4488d-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="4488d-115">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="4488d-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="4488d-116">Cree la siguiente plantilla (ArithmeticOperatorA.xml) y guárdela en el directorio donde haya guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="4488d-116">Create the following template (ArithmeticOperatorA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /OrderDetail[@UnitPrice * @OrderQty = 12.350]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="4488d-117">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4488d-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="4488d-118">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4488d-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="4488d-119">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4488d-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4488d-120">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4488d-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
```  
Here is the partial result set of the template execution:    
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-709" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-710" UnitPrice="6.175" OrderQty="2" UnitPriceDiscount="0" />   
   ...  
</ROOT>  
```  
  
  
