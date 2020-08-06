---
title: Especificar funciones booleanas en consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], Boolean functions
- false function
- not function [SQLXML]
- true function
- Boolean functions
ms.assetid: c72cd333-9294-4d41-84f2-1748bf20e3eb
author: rothja
ms.author: jroth
ms.openlocfilehash: d230c7cd8792066732085b9ce501c0794687d17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662753"
---
# <a name="specifying-boolean-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="49a96-102">Especificar funciones booleanas en consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="49a96-102">Specifying Boolean Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="49a96-103">Los ejemplos siguientes muestran cómo se especifican funciones booleanas en consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="49a96-103">The following examples show how Boolean functions are specified in XPath queries.</span></span> <span data-ttu-id="49a96-104">Las consultas XPath de estos ejemplos se especifican en el esquema de asignación que se incluye en SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="49a96-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="49a96-105">Para obtener información acerca de este esquema de ejemplo, vea [ejemplo de esquema XSD anotado para los ejemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="49a96-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="49a96-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="49a96-106">Examples</span></span>  
  
## <a name="a-specify-the-not-boolean-function"></a><span data-ttu-id="49a96-107">A.</span><span class="sxs-lookup"><span data-stu-id="49a96-107">A.</span></span> <span data-ttu-id="49a96-108">Especificar la función booleana not()</span><span class="sxs-lookup"><span data-stu-id="49a96-108">Specify the not() Boolean function</span></span>  
 <span data-ttu-id="49a96-109">Esta consulta devuelve todos los **\<Customer>** elementos secundarios del nodo de contexto que no tienen **\<Order>** elementos secundarios:</span><span class="sxs-lookup"><span data-stu-id="49a96-109">This query returns all the **\<Customer>** child elements of the context node that do not have **\<Order>** child elements:</span></span>  
  
```  
/child::Customer[not(child::Order)]  
```  
  
 <span data-ttu-id="49a96-110">El eje `child` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="49a96-110">The `child` axis is the default.</span></span> <span data-ttu-id="49a96-111">Por lo tanto, la consulta puede especificarse como:</span><span class="sxs-lookup"><span data-stu-id="49a96-111">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="49a96-112">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="49a96-112">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="49a96-113">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="49a96-113">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="49a96-114">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="49a96-114">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="49a96-115">Cree la siguiente plantilla (BooleanFunctionsA.xml) y guárdela en el directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="49a96-115">Create the following template (BooleanFunctionsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[not(Order)]  
    </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="49a96-116">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="49a96-116">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="49a96-117">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49a96-117">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="49a96-118">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="49a96-118">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="49a96-119">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="49a96-119">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="49a96-120">Este es el conjunto parcial de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="49a96-120">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
## <a name="b-specify-the-true-and-false-boolean-functions"></a><span data-ttu-id="49a96-121">B.</span><span class="sxs-lookup"><span data-stu-id="49a96-121">B.</span></span> <span data-ttu-id="49a96-122">Especificar las funciones booleanas true () y false ()</span><span class="sxs-lookup"><span data-stu-id="49a96-122">Specify the true() and false() Boolean functions</span></span>  
 <span data-ttu-id="49a96-123">Esta consulta devuelve todos los elementos **\<Customer>** secundarios del nodo de contexto que no tienen **\<Order>** elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="49a96-123">This query returns all **\<Customer>** element children of the context node that do not have **\<Order>** child elements.</span></span> <span data-ttu-id="49a96-124">En términos relacionales, esta consulta devuelve todos los clientes que no han realizado ningún pedido.</span><span class="sxs-lookup"><span data-stu-id="49a96-124">In relational terms, this query returns all customers who have not placed any orders.</span></span>  
  
```  
/child::Customer[child::Order=false()]  
```  
  
 <span data-ttu-id="49a96-125">El eje `child` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="49a96-125">The `child` axis is the default.</span></span> <span data-ttu-id="49a96-126">Por lo tanto, la consulta puede especificarse como:</span><span class="sxs-lookup"><span data-stu-id="49a96-126">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order=false()]  
```  
  
 <span data-ttu-id="49a96-127">Esta consulta equivale a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49a96-127">This query is equivalent to the following:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
 <span data-ttu-id="49a96-128">La consulta siguiente devuelve todos los clientes que han realizado al menos un pedido:</span><span class="sxs-lookup"><span data-stu-id="49a96-128">The following query returns all the customers who have placed at least one order:</span></span>  
  
```  
/Customer[Order=true()]  
```  
  
 <span data-ttu-id="49a96-129">Esta consulta equivale a ésta:</span><span class="sxs-lookup"><span data-stu-id="49a96-129">This query is equivalent to this one:</span></span>  
  
```  
/Customer[Order]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="49a96-130">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="49a96-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="49a96-131">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="49a96-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="49a96-132">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="49a96-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="49a96-133">Cree la siguiente plantilla (BooleanFunctionsB.xml) y guárdela en el directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="49a96-133">Create the following template (BooleanFunctionsB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order=false()]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="49a96-134">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="49a96-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="49a96-135">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49a96-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="49a96-136">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="49a96-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="49a96-137">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="49a96-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="49a96-138">Este es el conjunto parcial de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="49a96-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
  
