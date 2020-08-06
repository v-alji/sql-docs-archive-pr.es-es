---
title: Especificar funciones de conversión explícitas en consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit conversion functions [SQLXML]
- string function
- number function
- XPath queries [SQLXML], explicit conversion functions
ms.assetid: 1111cb5d-2bd9-4bdb-8de2-dc0e47452dd6
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b4b9bd5f5665c8cb86cb74c1397e2bd06e113fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662748"
---
# <a name="specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="3aa73-102">Especificar funciones de conversión explícita en consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3aa73-102">Specifying Explicit Conversion Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="3aa73-103">En los siguientes ejemplos se muestra cómo especificar funciones de conversión explícita en consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="3aa73-103">The following examples show how explicit conversion functions are specified in XPath queries.</span></span> <span data-ttu-id="3aa73-104">Las consultas XPath de estos ejemplos se especifican en el esquema de asignación que se incluye en SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3aa73-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="3aa73-105">Para obtener información acerca de este esquema de ejemplo, vea [ejemplo de esquema XSD anotado para los ejemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="3aa73-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3aa73-106">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3aa73-106">Examples</span></span>  
  
### <a name="a-use-the-number-explicit-conversion-function"></a><span data-ttu-id="3aa73-107">A.</span><span class="sxs-lookup"><span data-stu-id="3aa73-107">A.</span></span> <span data-ttu-id="3aa73-108">Usar la función de conversión explícita number()</span><span class="sxs-lookup"><span data-stu-id="3aa73-108">Use the number() explicit conversion function</span></span>  
 <span data-ttu-id="3aa73-109">La función `number()` convierte un argumento en un número.</span><span class="sxs-lookup"><span data-stu-id="3aa73-109">The `number()` function converts an argument to a number.</span></span>  
  
 <span data-ttu-id="3aa73-110">Suponiendo que el valor de **ContactID** no es numérico, la siguiente consulta convierte **ContactID** en un número y lo compara con el valor 4.</span><span class="sxs-lookup"><span data-stu-id="3aa73-110">Assuming the value of **ContactID** is nonnumeric, the following query converts **ContactID** to a number and compares it with the value 4.</span></span> <span data-ttu-id="3aa73-111">A continuación, la consulta devuelve todos los **\<Employee>** elementos secundarios del nodo de contexto con el atributo **ContactID** que tiene un valor numérico de 4:</span><span class="sxs-lookup"><span data-stu-id="3aa73-111">The query then returns all **\<Employee>** element children of the context node with the **ContactID** attribute that has a numeric value of 4:</span></span>  
  
```  
/child::Contact[number(attribute::ContactID)= 4]  
```  
  
 <span data-ttu-id="3aa73-112">Se puede especificar un acceso directo al eje `attribute` (@) y, puesto que el eje `child` es el valor predeterminado, puede omitirse en la consulta:</span><span class="sxs-lookup"><span data-stu-id="3aa73-112">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[number(@ContactID) = 4]  
```  
  
 <span data-ttu-id="3aa73-113">En términos relacionales, la consulta devuelve un empleado con un **ContactID** de 4.</span><span class="sxs-lookup"><span data-stu-id="3aa73-113">In relational terms, the query returns an employee with a **ContactID** of 4.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="3aa73-114">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="3aa73-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="3aa73-115">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="3aa73-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="3aa73-116">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3aa73-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="3aa73-117">Cree la siguiente plantilla (ExplicitConversionA.xml) y guárdela en el mismo directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3aa73-117">Create the following template (ExplicitConversionA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact[number(@ContactID)=4]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3aa73-118">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3aa73-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3aa73-119">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3aa73-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="3aa73-120">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3aa73-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3aa73-121">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3aa73-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3aa73-122">Éste es el conjunto de resultados de ejecución de esta plantilla:</span><span class="sxs-lookup"><span data-stu-id="3aa73-122">The result set for this template execution is:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
### <a name="b-use-the-string-explicit-conversion-function"></a><span data-ttu-id="3aa73-123">B.</span><span class="sxs-lookup"><span data-stu-id="3aa73-123">B.</span></span> <span data-ttu-id="3aa73-124">Usar la función de conversión explícita string()</span><span class="sxs-lookup"><span data-stu-id="3aa73-124">Use the string() explicit conversion function</span></span>  
 <span data-ttu-id="3aa73-125">La función `string()` convierte un argumento en una cadena.</span><span class="sxs-lookup"><span data-stu-id="3aa73-125">The `string()` function converts an argument to a string.</span></span>  
  
 <span data-ttu-id="3aa73-126">La siguiente consulta convierte **ContactID** en una cadena y lo compara con el valor de cadena "4".</span><span class="sxs-lookup"><span data-stu-id="3aa73-126">The following query converts **ContactID** to a string and compares it with the string value "4".</span></span> <span data-ttu-id="3aa73-127">La consulta devuelve todos los **\<Employee>** elementos secundarios del nodo de contexto con un **ContactID** con un valor de cadena de "4":</span><span class="sxs-lookup"><span data-stu-id="3aa73-127">The query returns all **\<Employee>** element children of the context node with a **ContactID** with a string value of "4":</span></span>  
  
```  
/child::Contact[string(attribute::ContactID)="4"]  
```  
  
 <span data-ttu-id="3aa73-128">Se puede especificar un acceso directo al eje `attribute` (@) y, puesto que el eje `child` es el valor predeterminado, puede omitirse en la consulta:</span><span class="sxs-lookup"><span data-stu-id="3aa73-128">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[string(@ContactID)="4"]  
```  
  
 <span data-ttu-id="3aa73-129">Funcionalmente, esta consulta devuelve los mismos resultados que la consulta de ejemplo anterior, pero la evaluación se realiza en un valor de cadena y no en el valor numérico (es decir, el número 4).</span><span class="sxs-lookup"><span data-stu-id="3aa73-129">Functionally, this query returns the same results as the previous example query, though the evaluation is done against a string value and not the numeric value (that is, the number 4).</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="3aa73-130">Para probar la consulta XPath en el esquema de asignación</span><span class="sxs-lookup"><span data-stu-id="3aa73-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="3aa73-131">Copie el [código de esquema de ejemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="3aa73-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="3aa73-132">Guarde el archivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3aa73-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="3aa73-133">Cree la siguiente plantilla (ExplicitConversionB.xml) y guárdela en el mismo directorio donde esté guardado el archivo SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="3aa73-133">Create the following template (ExplicitConversionB.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Contact[string(@ContactID)="4"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3aa73-134">La ruta de acceso al directorio especificada para el esquema de asignación (SampleSchema1.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3aa73-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3aa73-135">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3aa73-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="3aa73-136">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3aa73-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3aa73-137">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3aa73-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3aa73-138">Éste es el conjunto de resultados de ejecución de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="3aa73-138">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
  
