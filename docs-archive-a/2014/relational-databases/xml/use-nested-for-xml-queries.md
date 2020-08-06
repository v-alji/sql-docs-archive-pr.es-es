---
title: Usar consultas FOR XML anidadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, nested FOR XML queries
- queries [XML in SQL Server], nested FOR XML
- nested FOR XML queries
ms.assetid: 7604161a-a958-446d-b102-7dee432979d0
author: rothja
ms.author: jroth
ms.openlocfilehash: 60c4198697f8d19c9b2e5bc1b415e0787861d40a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748682"
---
# <a name="use-nested-for-xml-queries"></a><span data-ttu-id="87863-102">Usar consultas FOR XML anidadas</span><span class="sxs-lookup"><span data-stu-id="87863-102">Use Nested FOR XML Queries</span></span>
  <span data-ttu-id="87863-103">El `xml` tipo de datos y la [Directiva Type en las consultas for XML](type-directive-in-for-xml-queries.md) permiten que el XML devuelto por las consultas for XML se procese en el servidor y en el cliente.</span><span class="sxs-lookup"><span data-stu-id="87863-103">The `xml` data type and the [TYPE directive in FOR XML queries](type-directive-in-for-xml-queries.md) enable the XML returned by the FOR XML queries to be processed on the server as well as on the client.</span></span>  
  
## <a name="processing-with-xml-type-variables"></a><span data-ttu-id="87863-104">Procesar con variables de tipo xml</span><span class="sxs-lookup"><span data-stu-id="87863-104">Processing with xml Type Variables</span></span>  
 <span data-ttu-id="87863-105">Puede asignar el resultado de la consulta FOR XML a una variable de tipo `xml`, o utilizar XQuery para consultar el resultado y asignarlo a una variable de tipo `xml` para seguir procesándolo.</span><span class="sxs-lookup"><span data-stu-id="87863-105">You can assign the FOR XML query result to an `xml` type variable, or use XQuery to query the result, and assign that result to an `xml` type variable for more processing.</span></span>  
  
```  
DECLARE @x xml  
SET @x=(SELECT ProductModelID, Name  
        FROM Production.ProductModel  
        WHERE ProductModelID=122 or ProductModelID=119  
        FOR XML RAW, TYPE)  
SELECT @x  
-- Result  
--<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
--<row ProductModelID="119" Name="Bike Wash" />  
```  
  
 <span data-ttu-id="87863-106">También puede procesar el XML devuelto en la variable, `@x`, utilizando alguno de los métodos de tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="87863-106">You can additionally process the XML returned in the variable, `@x`, by using one of the `xml` data type methods.</span></span> <span data-ttu-id="87863-107">Por ejemplo, puede recuperar el valor del atributo `ProductModelID` al usar el [método value()](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="87863-107">For example, you can retrieve the `ProductModelID` attribute value by using the [value() method](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
DECLARE @i int;  
SET @i = (SELECT @x.value('/row[1]/@ProductModelID[1]', 'int'));  
SELECT @i;  
```  
  
 <span data-ttu-id="87863-108">En el siguiente ejemplo, el resultado de la consulta `FOR XML` se devuelve como un tipo `xml` porque se ha especificado la directiva `TYPE` en la cláusula `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="87863-108">In the following example, the `FOR XML` query result is returned as an `xml` type, because the `TYPE` directive is specified in the `FOR XML` clause.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=119 or ProductModelID=122  
FOR XML RAW, TYPE,ROOT('myRoot');  
  
```  
  
 <span data-ttu-id="87863-109">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="87863-109">This is the result:</span></span>  
  
```  
<myRoot>  
  <row ProductModelID="122" Name="All-Purpose Bike Stand" />  
  <row ProductModelID="119" Name="Bike Wash" />  
</myRoot>  
```  
  
 <span data-ttu-id="87863-110">Puesto que el resultado es de tipo `xml`, puede especificar uno de los métodos de tipo de datos `xml` directamente para este XML, como se muestra en la siguiente consulta.</span><span class="sxs-lookup"><span data-stu-id="87863-110">Because the result is of `xml` type, you can specify one of the `xml` data type methods directly against this XML, as shown in the following query.</span></span> <span data-ttu-id="87863-111">En la consulta, se usa el [método query() de tipo de datos xml](/sql/t-sql/xml/query-method-xml-data-type) para recuperar el primer elemento secundario <`row`> del elemento <`myRoot`>.</span><span class="sxs-lookup"><span data-stu-id="87863-111">In the query, the [query() method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) is used to retrieve the first <`row`> element child of the <`myRoot`> element.</span></span>  
  
```  
SELECT  (SELECT ProductModelID, Name  
         FROM Production.ProductModel  
         WHERE ProductModelID=119 or ProductModelID=122  
         FOR XML RAW, TYPE,ROOT('myRoot')).query('/myRoot[1]/row[1]');  
  
```  
  
 <span data-ttu-id="87863-112">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="87863-112">This is the result:</span></span>  
  
```  
<row ProductModelID="122" Name="All-Purpose Bike Stand" />  
```  
  
## <a name="returning-inner-for-xml-query-results-to-outer-queries-as-xml-type-instances"></a><span data-ttu-id="87863-113">Devolver resultados de consultas FOR XML internas a consultas externas como instancias de tipo xml</span><span class="sxs-lookup"><span data-stu-id="87863-113">Returning Inner FOR XML Query Results to Outer Queries as xml Type Instances</span></span>  
 <span data-ttu-id="87863-114">Puede escribir consultas `FOR XML` anidadas en las que el resultado de la consulta interna se devuelve como un tipo `xml` a la consulta externa.</span><span class="sxs-lookup"><span data-stu-id="87863-114">You can write nested `FOR XML` queries where the result of the inner query is returned as an `xml` type to the outer query.</span></span> <span data-ttu-id="87863-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="87863-115">For example:</span></span>  
  
```  
SELECT Col1,   
       Col2,   
       ( SELECT Col3, Col4   
        FROM  T2  
        WHERE T2.Col = T1.Col  
        ...  
        FOR XML AUTO, TYPE )  
FROM T1  
WHERE ...  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="87863-116">Observe lo siguiente en la consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="87863-116">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="87863-117">El XML generado por la consulta `FOR XML` interna se agrega al XML generado por la consulta `FOR XML`externa.</span><span class="sxs-lookup"><span data-stu-id="87863-117">The XML generated by the inner `FOR XML` query is added to the XML generated by the outer `FOR XML`.</span></span>  
  
-   <span data-ttu-id="87863-118">En la siguiente consulta interna se especifica la directiva `TYPE` .</span><span class="sxs-lookup"><span data-stu-id="87863-118">The inner query specifies the `TYPE` directive.</span></span> <span data-ttu-id="87863-119">Por lo tanto, los datos XML devueltos por la consulta interna son de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="87863-119">Therefore, the XML data returned by the inner query is of `xml` type.</span></span> <span data-ttu-id="87863-120">Si no se especifica la directiva TYPE, el resultado de la consulta `FOR XML` interna se devuelve como `nvarchar(max)` y se crean entidades de los datos XML.</span><span class="sxs-lookup"><span data-stu-id="87863-120">If the TYPE directive is not specified, the result of the inner `FOR XML` query is returned as `nvarchar(max)` and the XML data is entitized.</span></span>  
  
## <a name="controlling-the-shape-of-resulting-xml-data"></a><span data-ttu-id="87863-121">Controlar la forma de los datos XML resultantes</span><span class="sxs-lookup"><span data-stu-id="87863-121">Controlling the Shape of Resulting XML Data</span></span>  
 <span data-ttu-id="87863-122">Las consultas FOR XML anidadas ofrecen mayor control en la definición de la forma de los datos XML resultantes.</span><span class="sxs-lookup"><span data-stu-id="87863-122">Nested FOR XML queries give you more control in defining the shape of the resulting XML data.</span></span> <span data-ttu-id="87863-123">Es posible utilizar consultas FOR XML anidadas para construir XML parcialmente centrado en atributos y parcialmente centrado en elementos.</span><span class="sxs-lookup"><span data-stu-id="87863-123">You can use nested FOR XML queries to construct XML that is partly attribute-centric and partly element-centric.</span></span>  
  
 <span data-ttu-id="87863-124">Para obtener más información sobre cómo especificar XML centrado en atributos y XML centrado en elementos para las consultas FOR XML anidadas, vea [Comparación de la consulta FOR XML con la consulta FOR XML anidada](../xml/for-xml-query-compared-to-nested-for-xml-query.md) y [Dar forma a XML con consultas FOR XML anidadas](../xml/shape-xml-with-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="87863-124">For more information about specifying both attribute-centric and element-centric XML with nested FOR XML queries, see [FOR XML Query Compared to Nested FOR XML Query](../xml/for-xml-query-compared-to-nested-for-xml-query.md) and [Shape XML with Nested FOR XML Queries](../xml/shape-xml-with-nested-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="87863-125">Puede generar jerarquías XML que incluyen elementos del mismo nivel si especifica consultas FOR XML en modo AUTO anidadas.</span><span class="sxs-lookup"><span data-stu-id="87863-125">You can generate XML hierarchies that include siblings by specifying nested AUTO mode FOR XML queries.</span></span> <span data-ttu-id="87863-126">Para obtener más información, vea [Generar elementos del mismo nivel con una consulta de modo AUTO anidada](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span><span class="sxs-lookup"><span data-stu-id="87863-126">For more information, see [Generate Siblings with a Nested AUTO Mode Query](../xml/generate-siblings-with-a-nested-auto-mode-query.md).</span></span>  
  
 <span data-ttu-id="87863-127">Con independencia del modo que se utilice, las consultas FOR XML anidadas proporcionan mayor control en la descripción de la forma del XML resultante.</span><span class="sxs-lookup"><span data-stu-id="87863-127">Regardless of which mode you use, nested FOR XML queries provide more control in describing the shape of the resulting XML.</span></span> <span data-ttu-id="87863-128">Se pueden usar en lugar de las consultas en modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="87863-128">They can be used in the place of EXPLICIT mode queries.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="87863-129">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="87863-129">Examples</span></span>  
 <span data-ttu-id="87863-130">Los temas siguientes proporcionan ejemplos de consultas FOR XML anidadas.</span><span class="sxs-lookup"><span data-stu-id="87863-130">The following topics provide examples of nested FOR XML queries.</span></span>  
  
 [<span data-ttu-id="87863-131">Comparación de la consulta FOR XML con la consulta FOR XML anidada</span><span class="sxs-lookup"><span data-stu-id="87863-131">FOR XML Query Compared to Nested FOR XML Query</span></span>](../xml/for-xml-query-compared-to-nested-for-xml-query.md)  
 <span data-ttu-id="87863-132">Compara una consulta FOR XML de un solo nivel con una consulta FOR XML anidada.</span><span class="sxs-lookup"><span data-stu-id="87863-132">Compares a single-level FOR XML query to a nested FOR XML query.</span></span> <span data-ttu-id="87863-133">Este ejemplo incluye una demostración de cómo especificar XML centrado en atributos y XML centrado en elementos como resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="87863-133">This example includes a demonstration of how to specify both attribute-centric and element-centric XML as the result of the query.</span></span>  
  
 [<span data-ttu-id="87863-134">Generar elementos del mismo nivel con una consulta de modo AUTO anidada</span><span class="sxs-lookup"><span data-stu-id="87863-134">Generate Siblings with a Nested AUTO Mode Query</span></span>](../xml/generate-siblings-with-a-nested-auto-mode-query.md)  
 <span data-ttu-id="87863-135">Muestra cómo generar elementos del mismo nivel con una consulta en modo AUTO anidada.</span><span class="sxs-lookup"><span data-stu-id="87863-135">Shows how to generate siblings by using a nested AUTO mode query</span></span>  
  
 [<span data-ttu-id="87863-136">Usar consultas FOR XML anidadas en ASP.NET</span><span class="sxs-lookup"><span data-stu-id="87863-136">Use Nested FOR XML Queries in ASP.NET</span></span>](use-nested-for-xml-queries-in-asp-net.md)  
 <span data-ttu-id="87863-137">Muestra cómo una aplicación ASPX puede utilizar FOR XML para devolver XML de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87863-137">Demonstrates how an ASPX application can use FOR XML to return XML from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="87863-138">Dar forma a XML con consultas FOR XML anidadas</span><span class="sxs-lookup"><span data-stu-id="87863-138">Shape XML with Nested FOR XML Queries</span></span>](../xml/shape-xml-with-nested-for-xml-queries.md)  
 <span data-ttu-id="87863-139">Muestra cómo utilizar consultas FOR XML anidadas para controlar la estructura de un documento XML creado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87863-139">Shows how to use nested FOR XML queries to control the structure of an XML document created by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
  
