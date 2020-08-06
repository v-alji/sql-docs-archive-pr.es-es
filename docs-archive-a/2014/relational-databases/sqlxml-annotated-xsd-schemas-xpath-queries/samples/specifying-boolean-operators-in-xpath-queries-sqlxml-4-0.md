---
title: Especificar operadores booleanos en consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath operators [SQLXML]
- OR operator
- Boolean operators
- XPath queries [SQLXML], Boolean operators
- operators [SQLXML]
ms.assetid: 9928cff5-62ac-42aa-96bf-2e09a1df0bc3
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dd6e1f120b53382ce984684ea352b36d34b768
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662752"
---
# <a name="specifying-boolean-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="b49c0-102">Especificar operadores booleanos en consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b49c0-102">Specifying Boolean Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="b49c0-103">El ejemplo siguiente muestra cómo los operadores booleanos se especifican en consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="b49c0-103">The following example shows how Boolean operators are specified in XPath queries.</span></span> <span data-ttu-id="b49c0-104">La consulta XPath de este ejemplo se especifica en el esquema de asignación que se incluye en SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="b49c0-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="b49c0-105">Para obtener información acerca de este esquema de ejemplo, vea [ejemplo de esquema XSD anotado para los ejemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="b49c0-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b49c0-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b49c0-106">Examples</span></span>  
  
### <a name="a-specify-the-or-boolean-operator"></a><span data-ttu-id="b49c0-107">A.</span><span class="sxs-lookup"><span data-stu-id="b49c0-107">A.</span></span> <span data-ttu-id="b49c0-108">Especificar el operador booleano OR</span><span class="sxs-lookup"><span data-stu-id="b49c0-108">Specify the OR Boolean operator</span></span>  
 <span data-ttu-id="b49c0-109">Esta consulta XPath devuelve los **\<Customer>** elementos secundarios del nodo de contexto con el valor de atributo **CustomerID** de 13 o 31:</span><span class="sxs-lookup"><span data-stu-id="b49c0-109">This XPath query returns the **\<Customer>** element children of the context node with the **CustomerID** attribute value of 13 or 31:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="13" or attribute::CustomerID="31"]  
```  
  
 <span data-ttu-id="b49c0-110">Se puede especificar un acceso directo al eje `attribute` (@) y, puesto que el eje `child` es el valor predeterminado, puede omitirse:</span><span class="sxs-lookup"><span data-stu-id="b49c0-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted:</span></span>  
  
```  
/Customer[@CustomerID="13" or @CustomerID="31"]  
```  
  
 <span data-ttu-id="b49c0-111">En el predicado, `attribute` es el eje y `CustomerID` es la prueba de nodo (true si **CustomerID** es un **\<attribute>** nodo, porque el **\<attribute>** nodo es el nodo principal del `attribute` eje).</span><span class="sxs-lookup"><span data-stu-id="b49c0-111">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an **\<attribute>** node, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span> <span data-ttu-id="b49c0-112">El predicado filtra los **\<Customer>** elementos y devuelve solo aquellos que satisfacen la condición especificada en el predicado.</span><span class="sxs-lookup"><span data-stu-id="b49c0-112">The predicate filters the **\<Customer>** elements and returns only those that satisfy the condition specified in the predicate.</span></span>  
  
##### <a name="to-test-the-xpath-queries-against-the-mapping-schema"></a><span data-ttu-id="b49c0-113">Para probar las consultas XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="b49c0-113">To test the XPath queries against the mapping schema</span></span>  
  
1.  <span data-ttu-id="b49c0-114">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="b49c0-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="b49c0-115">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="b49c0-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="b49c0-116">Cree la siguiente plantilla (BooleanOperatorsA.xml) y guárdela en el directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="b49c0-116">Create the following template (BooleanOperatorsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="13" or @CustomerID="31"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="b49c0-117">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b49c0-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="b49c0-118">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b49c0-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="b49c0-119">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b49c0-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="b49c0-120">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b49c0-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="b49c0-121">Éste es el conjunto de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="b49c0-121">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="31" SalesPersonID="286" TerritoryID="7" AccountNumber="31" CustomerType="S" Orders="Ord-51803 Ord-69427">  
    <Order SalesOrderID="Ord-51803" SalesPersonID="286" OrderDate="2003-08-01T00:00:00" DueDate="2003-08-13T00:00:00" ShipDate="2003-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-718" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-838" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    <Order SalesOrderID="Ord-69427" SalesPersonID="286" OrderDate="2004-05-01T00:00:00" DueDate="2004-05-13T00:00:00" ShipDate="2004-05-08T00:00:00">  
      <OrderDetail ProductID="Prod-835" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
  </Customer>  
</ROOT>  
```  
  
  
