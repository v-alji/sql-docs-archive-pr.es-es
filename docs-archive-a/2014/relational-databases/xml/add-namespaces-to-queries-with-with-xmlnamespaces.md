---
title: Agregar espacios de nombres a consultas con WITH XMLNAMESPACES | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENTS XSINIL directive
- adding namespaces
- XSINIL directive
- default namespaces
- queries [XML in SQL Server], WITH XMLNAMESPACES clause
- predefined namespaces [XML in SQL Server]
- FOR XML clause, WITH XMLNAMESPACES clause
- namespaces [XML in SQL Server]
- xml data type [SQL Server], WITH XMLNAMESPACES clause
- WITH XMLNAMESPACES clause
ms.assetid: 2189cb5e-4460-46c5-a254-20c833ebbfec
author: rothja
ms.author: jroth
ms.openlocfilehash: ed5d719a845996215fffc18af64401779f848cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662715"
---
# <a name="add-namespaces-to-queries-with-with-xmlnamespaces"></a><span data-ttu-id="272b9-102">Agregar espacios de nombres a consultas con WITH XMLNAMESPACES</span><span class="sxs-lookup"><span data-stu-id="272b9-102">Add Namespaces to Queries with WITH XMLNAMESPACES</span></span>
  <span data-ttu-id="272b9-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) proporciona compatibilidad con los URI de espacio de nombres de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="272b9-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) provides namespace URI support in the following way:</span></span>  
  
-   <span data-ttu-id="272b9-104">Hace que las asignaciones de prefijos de espacio de nombres a los URI estén disponibles al [generar XML mediante FOR XML](for-xml-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="272b9-104">It makes the namespace prefix to URI mapping available when [Constructing XML Using FOR XML](for-xml-sql-server.md) queries.</span></span>  
  
-   <span data-ttu-id="272b9-105">Hace que las asignaciones de espacios de nombres a los URI estén disponibles para el contexto de espacio de nombres estático de los [métodos del tipo de datos xml](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="272b9-105">It makes the namespace to URI mapping available to the static namespace context of the [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span>  
  
## <a name="using-with-xmlnamespaces-in-the-for-xml-queries"></a><span data-ttu-id="272b9-106">Utilizar WITH XMLNAMESPACES en las consultas FOR XML</span><span class="sxs-lookup"><span data-stu-id="272b9-106">Using WITH XMLNAMESPACES in the FOR XML Queries</span></span>  
 <span data-ttu-id="272b9-107">WITH XMLNAMESPACES permite incluir espacios de nombres XML en las consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="272b9-107">WITH XMLNAMESPACES lets you include XML namespaces in FOR XML queries.</span></span> <span data-ttu-id="272b9-108">Por ejemplo, considere la siguiente consulta FOR XML:</span><span class="sxs-lookup"><span data-stu-id="272b9-108">For example, consider the following FOR XML query:</span></span>  
  
```  
SELECT ProductID, Name, Color  
FROM   Production.Product  
WHERE  ProductID=316 or ProductID=317  
FOR XML RAW  
```  
  
 <span data-ttu-id="272b9-109">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="272b9-109">This is the result:</span></span>  
  
```  
<row ProductID="316" Name="Blade" />  
<row ProductID="317" Name="LL Crankarm" Color="Black" />  
  
```  
  
 <span data-ttu-id="272b9-110">Para agregar espacios de nombres al XML generado por la consulta FOR XML, especifique primero las asignaciones de los prefijos de espacio de nombres a los URI mediante la cláusula WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="272b9-110">To add namespaces to the XML constructed by the FOR XML query, first specify the namespace prefix to URI mappings by using the WITH NAMESPACES clause.</span></span> <span data-ttu-id="272b9-111">A continuación, utilice los prefijos de espacio de nombres para especificar los nombres en la consulta, como se muestra en la siguiente consulta modificada.</span><span class="sxs-lookup"><span data-stu-id="272b9-111">Then, use the namespace prefixes in specifying the names in the query as shown in the following modified query.</span></span> <span data-ttu-id="272b9-112">Tenga en cuenta que la cláusula WITH XMLNAMESPACES especifica la asignación del prefijo de espacio de nombres (`ns1`) al URI (`uri`).</span><span class="sxs-lookup"><span data-stu-id="272b9-112">Note that the WITH XMLNAMESPACES clause specifies the namespace prefix (`ns1`) to URI (`uri`) mapping.</span></span> <span data-ttu-id="272b9-113">Después, el prefijo `ns1` se usa para especificar los nombres de elementos y atributos que la cláusula FOR XML debe generar.</span><span class="sxs-lookup"><span data-stu-id="272b9-113">The `ns1` prefix is then used in specifying the element and attribute names to be constructed by the FOR XML query.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Prod'), ELEMENTS  
  
```  
  
 <span data-ttu-id="272b9-114">El resultado XML incluye los prefijos de espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="272b9-114">The XML result includes the namespace prefixes:</span></span>  
  
```  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
</ns1:Prod>  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>317</ns1:ProductID>  
  <ns1:Name>LL Crankarm</ns1:Name>  
  <ns1:Color>Black</ns1:Color>  
</ns1:Prod>  
  
```  
  
 <span data-ttu-id="272b9-115">La siguiente información se aplica a la cláusula WITH XMLNAMESPACES:</span><span class="sxs-lookup"><span data-stu-id="272b9-115">The following applies to the WITH XMLNAMESPACES clause:</span></span>  
  
-   <span data-ttu-id="272b9-116">Se admite solamente en los modos RAW, AUTO y PATH de las consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="272b9-116">It is supported only on the RAW, AUTO, and PATH modes of the FOR XML queries.</span></span> <span data-ttu-id="272b9-117">No se admite el modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="272b9-117">The EXPLICIT mode is not supported.</span></span>  
  
-   <span data-ttu-id="272b9-118">Afecta a los prefijos de espacio de nombres de las consultas FOR XML y a los métodos del tipo de datos **xml** , pero no al analizador XML.</span><span class="sxs-lookup"><span data-stu-id="272b9-118">It only affects the namespace prefixes of FOR XML queries and the **xml** data type methods, but not the XML parser.</span></span> <span data-ttu-id="272b9-119">Por ejemplo, la consulta siguiente devuelve un error porque el documento XML no tiene ninguna declaración de espacio de nombres para el prefijo myNS.</span><span class="sxs-lookup"><span data-stu-id="272b9-119">For example, the following query returns an error, because the XML document has no namespace declaration for the myNS prefix.</span></span>  
  
-   <span data-ttu-id="272b9-120">Las directivas FOR XML, XMLSCHEMA y XMLDATA no se pueden utilizar con una cláusula WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="272b9-120">The FOR XML directives, XMLSCHEMA and XMLDATA cannot be used when a WITH XMLNAMESPACES clause is being used.</span></span>  
  
    ```  
    CREATE TABLE T (x xml)  
    go  
    WITH XMLNAMESPACES ('http://abc' as myNS )  
    INSERT INTO T VALUES('<myNS:root/>')  
    ```  
  
## <a name="using-the-xsinil-directive"></a><span data-ttu-id="272b9-121">Utilizar la directiva XSINIL</span><span class="sxs-lookup"><span data-stu-id="272b9-121">Using the XSINIL Directive</span></span>  
 <span data-ttu-id="272b9-122">No se puede definir el prefijo xsi en la cláusula WITH XMLNAMESPACES si se utiliza la directiva ELEMENTS XSINIL.</span><span class="sxs-lookup"><span data-stu-id="272b9-122">You cannot define the xsi prefix in the WITH XMLNAMESPACES clause if you are using the ELEMENTS XSINIL directive.</span></span> <span data-ttu-id="272b9-123">En su lugar, se agrega automáticamente cuando se utiliza ELEMENTS XSINIL.</span><span class="sxs-lookup"><span data-stu-id="272b9-123">Instead, it is added automatically when you use ELEMENTS XSINIL.</span></span> <span data-ttu-id="272b9-124">La consulta siguiente usa ELEMENTS XSINIL, que genera XML centrado en elementos donde los valores NULL se asignan a elementos que tienen el atributo **xsi:nil** establecido en True.</span><span class="sxs-lookup"><span data-stu-id="272b9-124">The following query uses ELEMENTS XSINIL that generates element-centric XML where null values are mapped to elements that have the **xsi:nil** attribute set to True.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316   
FOR XML RAW, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="272b9-125">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="272b9-125">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
  <ns1:Color xsi:nil="true" />  
</row>  
```  
  
## <a name="specifying-default-namespaces"></a><span data-ttu-id="272b9-126">Especificar espacios de nombres predeterminados</span><span class="sxs-lookup"><span data-stu-id="272b9-126">Specifying Default Namespaces</span></span>  
 <span data-ttu-id="272b9-127">En lugar de declarar un prefijo de espacio de nombres, se puede declarar un espacio de nombres predeterminado mediante la palabra clave DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="272b9-127">Instead of declaring a namespace prefix, you can declare a default namespace by using a DEFAULT keyword.</span></span> <span data-ttu-id="272b9-128">En la consulta FOR XML, enlazará el espacio de nombres predeterminado con los nodos XML del XML resultante.</span><span class="sxs-lookup"><span data-stu-id="272b9-128">In the FOR XML query, it will bind the default namespace to XML nodes in the resulting XML.</span></span> <span data-ttu-id="272b9-129">En el ejemplo siguiente, WITH XMLNAMESPACES especifica dos prefijos de espacio de nombres definidos con un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="272b9-129">In the following example, the WITH XMLNAMESPACES defines two namespace prefixes that are defined together with a default namespace.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,   
                    'uri2' as ns2,  
                    DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product   
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Product'), ROOT('ns2:root'), ELEMENTS  
```  
  
 <span data-ttu-id="272b9-130">La consulta FOR XML genera XML centrado en elementos.</span><span class="sxs-lookup"><span data-stu-id="272b9-130">The FOR XML query generates element-centric XML.</span></span> <span data-ttu-id="272b9-131">Observe que la consulta utiliza los prefijos de espacio de nombres para asignar nombres a los nodos.</span><span class="sxs-lookup"><span data-stu-id="272b9-131">Note that the query uses both the namespace prefixes in naming nodes.</span></span> <span data-ttu-id="272b9-132">En la cláusula SELECT, ProductID, Name y Color no especifican un nombre con ningún prefijo.</span><span class="sxs-lookup"><span data-stu-id="272b9-132">In the SELECT clause, the ProductID, Name, and Color do not specify a name with any prefix.</span></span> <span data-ttu-id="272b9-133">Por lo tanto, los elementos correspondientes en el XML resultante pertenecen al espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="272b9-133">Therefore, the corresponding elements in the resulting XML belong to the default namespace.</span></span>  
  
```  
<ns2:root xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">  
  <ns1:Product>  
    <ProductID>316</ProductID>  
    <Name>Blade</Name>  
  </ns1:Product>  
  <ns1:Product>  
    <ProductID>317</ProductID>  
    <Name>LL Crankarm</Name>  
    <Color>Black</Color>  
  </ns1:Product>  
</ns2:root>  
```  
  
 <span data-ttu-id="272b9-134">La consulta siguiente es similar a la anterior, con la diferencia de que se especifica el modo AUTO de FOR XML.</span><span class="sxs-lookup"><span data-stu-id="272b9-134">The following query is similar to the previous one, except that the FOR XML AUTO mode is specified.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,  'uri2' as ns2,DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product as "ns1:Product"  
WHERE ProductID=316 or ProductID=317  
FOR XML AUTO, ROOT('ns2:root'), ELEMENTS  
```  
  
## <a name="using-predefined-namespaces"></a><span data-ttu-id="272b9-135">Utilizar espacios de nombres predefinidos</span><span class="sxs-lookup"><span data-stu-id="272b9-135">Using Predefined Namespaces</span></span>  
 <span data-ttu-id="272b9-136">Si se utilizan espacios de nombres predefinidos, excepto los espacios de nombres xml y xsi cuando se utiliza ELEMENTS XSINIL, es necesario especificar explícitamente el enlace con el espacio de nombres por medio de WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="272b9-136">When you use predefined namespaces, except the xml namespace and the xsi namespace when ELEMENTS XSINIL is used, you must explicitly specify the namespace binding by using WITH XMLNAMESPACES.</span></span> <span data-ttu-id="272b9-137">En la consulta siguiente se define explícitamente el enlace entre el prefijo de espacio de nombres y el URI para el espacio de nombres predefinido (`urn:schemas-microsoft-com:xml-sql`).</span><span class="sxs-lookup"><span data-stu-id="272b9-137">The following query explicitly defines the namespace prefix to URI binding for the predefined namespace (`urn:schemas-microsoft-com:xml-sql`).</span></span>  
  
```  
WITH XMLNAMESPACES ('urn:schemas-microsoft-com:xml-sql' as sql)  
SELECT 'SELECT * FROM Customers FOR XML AUTO, ROOT("a")' AS "sql:query"  
FOR XML PATH('sql:root')  
```  
  
 <span data-ttu-id="272b9-138">Éste es el resultado.</span><span class="sxs-lookup"><span data-stu-id="272b9-138">This is the result.</span></span> <span data-ttu-id="272b9-139">Los usuarios de SQLXML están familiarizados con esta plantilla XML.</span><span class="sxs-lookup"><span data-stu-id="272b9-139">SQLXML users are familiar with this XML template.</span></span> <span data-ttu-id="272b9-140">Para obtener más información, vea [Conceptos de programación en SQLXML 4.0](../sqlxml/sqlxml-4-0-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="272b9-140">For more information, see [SQLXML 4.0 Programming Concepts](../sqlxml/sqlxml-4-0-programming-concepts.md).</span></span>  
  
```  
<sql:root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>SELECT * FROM Customers FOR XML AUTO, ROOT("a")</sql:query>  
</sql:root>  
```  
  
 <span data-ttu-id="272b9-141">Solo se puede utilizar el prefijo de espacio de nombres xml sin definirlo explícitamente en WITH XMLNAMESPACES, como se muestra en la siguiente consulta en modo PATH.</span><span class="sxs-lookup"><span data-stu-id="272b9-141">Only the xml namespace prefix can be used without explicitly defining it in WITH XMLNAMESPACES, as shown in the following PATH mode query.</span></span> <span data-ttu-id="272b9-142">Por otra parte, si se declara el prefijo, debe estar enlazado con el espacio de nombres http://www.w3.org/XML/1998/namespace.</span><span class="sxs-lookup"><span data-stu-id="272b9-142">Also, if the prefix is declared, it has to be bound to the namespace http://www.w3.org/XML/1998/namespace.</span></span> <span data-ttu-id="272b9-143">Los nombres especificados en la cláusula SELECT hacen referencia al prefijo de espacio de nombres xml que no se define explícitamente mediante WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="272b9-143">The names specified in the SELECT clause refer to the xml namespace prefix that is not explicitly defined by using WITH XMLNAMESPACES.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
go  
```  
  
 <span data-ttu-id="272b9-144">Los atributos @xml:lang usan el espacio de nombres xml predefinido.</span><span class="sxs-lookup"><span data-stu-id="272b9-144">The @xml:lang attributes use the predefined xml namespace.</span></span> <span data-ttu-id="272b9-145">Debido a que la versión 1.0 de XML no requiere la declaración explícita del enlace del espacio de nombres xml, el resultado no incluirá una declaración explícita del enlace de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="272b9-145">Because XML version 1.0 does not require the explicit declaration of the xml namespace binding, the result will not include an explicit declaration of the namespace binding.</span></span>  
  
 <span data-ttu-id="272b9-146">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="272b9-146">This is the result:</span></span>  
  
```  
<Translation>  
  <English xml:lang="en">food</English>  
  <German xml:lang="ger">Essen</German>  
</Translation>  
```  
  
## <a name="using-with-xmlnamespaces-with-the-xml-data-type-methods"></a><span data-ttu-id="272b9-147">Utilizar WITH XMLNAMESPACES con los métodos del tipo de datos xml</span><span class="sxs-lookup"><span data-stu-id="272b9-147">Using WITH XMLNAMESPACES with the xml Data Type Methods</span></span>  
 <span data-ttu-id="272b9-148">Los [métodos del tipo de datos xml](/sql/t-sql/xml/xml-data-type-methods) especificados en una consulta SELECT, o en UPDATE en el caso del método **modify()** , deben repetir la declaración del espacio de nombres en el prólogo.</span><span class="sxs-lookup"><span data-stu-id="272b9-148">The [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) specified in a SELECT query, or in UPDATE when it is the **modify()** method, all have to repeat the namespace declaration in their prolog.</span></span> <span data-ttu-id="272b9-149">Esto puede resultar lento.</span><span class="sxs-lookup"><span data-stu-id="272b9-149">This can be time-consuming.</span></span> <span data-ttu-id="272b9-150">Por ejemplo, la consulta siguiente recupera los identificadores de modelo de producto cuyas descripciones de catálogo no incluyen la especificación.</span><span class="sxs-lookup"><span data-stu-id="272b9-150">For example, the following query retrieves product model IDs whose catalog descriptions do include specification.</span></span> <span data-ttu-id="272b9-151">Es decir, el elemento <`Specifications`> existe.</span><span class="sxs-lookup"><span data-stu-id="272b9-151">That is, the <`Specifications`> element exists.</span></span>  
  
```  
SELECT ProductModelID, CatalogDescription.query('  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
    declare namespace  pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
```  
  
 <span data-ttu-id="272b9-152">En la consulta anterior, los métodos **query()** y **exist()** declaran el mismo espacio de nombres en el prólogo.</span><span class="sxs-lookup"><span data-stu-id="272b9-152">In the previous query, both the **query()** and **exist()** methods declare the same namespace in their prolog.</span></span> <span data-ttu-id="272b9-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="272b9-153">For example:</span></span>  
  
```  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
```  
  
 <span data-ttu-id="272b9-154">Alternativamente, se puede declarar primero WITH XMLNAMESPACES y utilizar los prefijos de espacio de nombres en la consulta.</span><span class="sxs-lookup"><span data-stu-id="272b9-154">Alternatively, you can declare WITH XMLNAMESPACES first and use the namespace prefixes in the query.</span></span> <span data-ttu-id="272b9-155">En este caso, los métodos **query()** y **exist()** no tienen que incluir las declaraciones de espacio de nombres en el prólogo.</span><span class="sxs-lookup"><span data-stu-id="272b9-155">In this case, the **query()** and **exist()** methods  do not have to include namespace declarations in their prolog.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' as pd)  
SELECT ProductModelID, CatalogDescription.query('  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
Go  
```  
  
 <span data-ttu-id="272b9-156">Debe tenerse en cuenta que una declaración explícita en el prólogo de una consulta XQuery reemplazará el prefijo de espacio de nombres y el espacio de nombres predeterminado del elemento definidos en la cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="272b9-156">Note that an explicit declaration in the XQuery prolog overrides the namespace prefix and the default element namespace that are defined in the WITH clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="272b9-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="272b9-157">See Also</span></span>  
 <span data-ttu-id="272b9-158">[métodos del tipo de datos xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="272b9-158">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="272b9-159">[Referencia del lenguaje XQuery &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span><span class="sxs-lookup"><span data-stu-id="272b9-159">[XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span></span>  
 <span data-ttu-id="272b9-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span><span class="sxs-lookup"><span data-stu-id="272b9-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span></span>  
 [<span data-ttu-id="272b9-161">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="272b9-161">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
