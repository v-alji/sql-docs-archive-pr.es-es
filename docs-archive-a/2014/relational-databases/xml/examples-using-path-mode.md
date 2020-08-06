---
title: 'Ejemplos: Uso del modo PATH | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, examples
ms.assetid: 3564e13b-9b97-49ef-8cf9-6a78677b09a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0876d93ffe246b6129a3838f8dbae47f3be7ffaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752001"
---
# <a name="examples-using-path-mode"></a><span data-ttu-id="10362-102">Ejemplos: Uso del modo PATH</span><span class="sxs-lookup"><span data-stu-id="10362-102">Examples: Using PATH Mode</span></span>
  <span data-ttu-id="10362-103">El ejemplo siguiente ilustra el uso del modo PATH en la creación de XML a partir de una consulta SELECT.</span><span class="sxs-lookup"><span data-stu-id="10362-103">The following examples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="10362-104">Muchas de estas consultas se especifican usando los documentos XML de instrucciones de fabricación de bicicletas almacenados en la columna Instructions de la tabla ProductModel.</span><span class="sxs-lookup"><span data-stu-id="10362-104">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="specifying-a-simple-path-mode-query"></a><span data-ttu-id="10362-105">Especificar una consulta sencilla de modo PATH</span><span class="sxs-lookup"><span data-stu-id="10362-105">Specifying a simple PATH mode query</span></span>  
 <span data-ttu-id="10362-106">Esta consulta especifica un modo FOR XML PATH.</span><span class="sxs-lookup"><span data-stu-id="10362-106">This query specifies a FOR XML PATH mode.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   
       ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH;  
GO  
```  
  
 <span data-ttu-id="10362-107">El resultado siguiente es XML centrado en elementos en el que cada valor de columna del conjunto de filas resultante se agrupa en un elemento.</span><span class="sxs-lookup"><span data-stu-id="10362-107">The following result is element-centric XML where each column value in the resulting rowset is wrapped in an element.</span></span> <span data-ttu-id="10362-108">Puesto que la cláusula `SELECT` no especifica ningún alias para los nombres de columna, los nombres de elemento secundario generados son los mismos que los nombres de columna correspondientes de la cláusula `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="10362-108">Because the `SELECT` clause does not specify any aliases for the column names, the child element names generated are the same as the corresponding column names in the `SELECT` clause.</span></span> <span data-ttu-id="10362-109">Para cada fila del conjunto de filas se agrega una etiqueta <`row`>.</span><span class="sxs-lookup"><span data-stu-id="10362-109">For each row in the rowset a <`row`> tag is added.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</row>`  
  
 `<row>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</row>`  
  
 <span data-ttu-id="10362-110">El resultado siguiente es el mismo que el de la consulta de modo `RAW` con la opción `ELEMENTS` especificada.</span><span class="sxs-lookup"><span data-stu-id="10362-110">The following result is the same as the `RAW` mode query with the `ELEMENTS` option specified.</span></span> <span data-ttu-id="10362-111">Devuelve XML centrado en elementos con un elemento <`row`> predeterminado para cada fila del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="10362-111">It returns element-centric XML with a default <`row`> element for each row in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML RAW, ELEMENTS;  
```  
  
 <span data-ttu-id="10362-112">También puede especificar el nombre del elemento de fila para sobrescribir el valor <`row`> predeterminado.</span><span class="sxs-lookup"><span data-stu-id="10362-112">You can optionally specify the row element name to overwrite the default <`row`>.</span></span> <span data-ttu-id="10362-113">Por ejemplo, la consulta siguiente devuelve el elemento <`ProductModel`> para cada fila del conjunto de filas.</span><span class="sxs-lookup"><span data-stu-id="10362-113">For example, the following query returns the <`ProductModel`> element for each row in the rowset.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModel');  
GO  
```  
  
 <span data-ttu-id="10362-114">El XML resultante tendrá un nombre de elemento de fila especificado.</span><span class="sxs-lookup"><span data-stu-id="10362-114">The resulting XML will have a specified row element name.</span></span>  
  
 `<ProductModel>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ProductModel>`  
  
 `<ProductModel>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ProductModel>`  
  
 <span data-ttu-id="10362-115">Si especifica una cadena de longitud cero, no se generará el elemento de ajuste.</span><span class="sxs-lookup"><span data-stu-id="10362-115">If you specify a zero-length string, the wrapping element is not produced.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('');  
GO  
```  
  
 <span data-ttu-id="10362-116">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="10362-116">This is the result:</span></span>  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
## <a name="specifying-xpath-like-column-names"></a><span data-ttu-id="10362-117">Especificar nombres de columna de tipo XPath</span><span class="sxs-lookup"><span data-stu-id="10362-117">Specifying XPath-like column names</span></span>  
 <span data-ttu-id="10362-118">En la consulta siguiente, el nombre de columna `ProductModelID` especificado empieza por "\@" y no incluye una marca de barra diagonal ("/").</span><span class="sxs-lookup"><span data-stu-id="10362-118">In the following query the `ProductModelID` column name specified starts with '\@' and does not contain a slash mark ('/').</span></span> <span data-ttu-id="10362-119">Por tanto, se creará en el XML resultante un atributo del elemento <`row`> que tenga el valor de columna correspondiente.</span><span class="sxs-lookup"><span data-stu-id="10362-119">Therefore, an attribute of the <`row`> element that has the corresponding column value is created in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('ProductModelData');  
GO  
```  
  
 <span data-ttu-id="10362-120">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="10362-120">This is the result:</span></span>  
  
 `< ProductModelData id="122">`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ ProductModelData >`  
  
 `< ProductModelData id="119">`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ ProductModelData >`  
  
 <span data-ttu-id="10362-121">Puede agregar un solo elemento de nivel superior especificando la opción `root` en `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="10362-121">You can add a single top-level element by specifying the `root` option in `FOR XML`.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="10362-122">Para generar una jerarquía, puede incluir sintaxis del tipo PATH.</span><span class="sxs-lookup"><span data-stu-id="10362-122">To generate a hierarchy, you can include PATH-like syntax.</span></span> <span data-ttu-id="10362-123">Por ejemplo, si cambia el nombre de la columna `Name` por "SomeChild/ModelName", obtendrá XML con una jerarquía, tal y como se muestra en este resultado:</span><span class="sxs-lookup"><span data-stu-id="10362-123">For example, change the column name for the `Name` column to "SomeChild/ModelName" and you will obtain XML with hierarchy, as shown in this result:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="122">`  
  
 `<SomeChild>`  
  
 `<ModelName>All-Purpose Bike Stand</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData id="119">`  
  
 `<SomeChild>`  
  
 `<ModelName>Bike Wash</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="10362-124">Además del identificador y el nombre del modelo de producto, la consulta siguiente recupera las ubicaciones con instrucciones de fabricación para el modelo de producto.</span><span class="sxs-lookup"><span data-stu-id="10362-124">Besides the product model ID and name, the following query retrieves the manufacturing instruction locations for the product model.</span></span> <span data-ttu-id="10362-125">Puesto que la columna Instructions es de tipo `xml`, se especifica el método `query()` del tipo de datos `xml` para recuperar la ubicación.</span><span class="sxs-lookup"><span data-stu-id="10362-125">Because the Instructions column is of `xml` type, the `query()` method of `xml` data type is specified to retrieve the location.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') AS ManuInstr  
FROM Production.ProductModel  
WHERE ProductModelID = 7  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="10362-126">El resultado parcial es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="10362-126">This is the partial result.</span></span> <span data-ttu-id="10362-127">Dado que la consulta especifica ManuInstr como nombre de columna, el XML devuelto por el `query()` método se ajusta en una <`ManuInstr`> etiqueta como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="10362-127">Because the query specifies ManuInstr as the column name, the XML returned by the `query()` method is wrapped in a <`ManuInstr`> tag as shown in the following:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="7">`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<ManuInstr>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `<MI:step>...</MI:step>...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ManuInstr>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="10362-128">En la consulta FOR XML anterior, puede incluir espacios de nombres para los elementos <`Root`> y <`ProductModelData`>.</span><span class="sxs-lookup"><span data-stu-id="10362-128">In the previous FOR XML query, you may want to include namespaces for the <`Root`> and <`ProductModelData`> elements.</span></span> <span data-ttu-id="10362-129">Para ello, defina en primer lugar el prefijo de enlace de espacios de nombres mediante WITH XMLNAMESPACES y prefijos en la consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="10362-129">You can do this by first defining the prefix to namespace binding by using WITH XMLNAMESPACES and using prefixes in the FOR XML query.</span></span> <span data-ttu-id="10362-130">Para obtener más información, vea [Agregar espacios de nombres a consultas con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="10362-130">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES (  
   'uri1' AS ns1,    
   'uri2' AS ns2,  
   'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions' as MI)  
SELECT ProductModelID AS "ns1:ProductModelID",  
       Name           AS "ns1:Name",  
       Instructions.query('  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ('ns2:ProductInfo'), root('ns1:root');  
GO  
```  
  
 <span data-ttu-id="10362-131">Observe que el prefijo `MI` también se define en `WITH XMLNAMESPACES`.</span><span class="sxs-lookup"><span data-stu-id="10362-131">Note that the `MI` prefix is also defined in the `WITH XMLNAMESPACES`.</span></span> <span data-ttu-id="10362-132">Como resultado, el método `query()` del tipo `xml` especificado no define el prefijo en el prólogo de la consulta.</span><span class="sxs-lookup"><span data-stu-id="10362-132">As a result, the `query()` method of the `xml` type specified does not define the prefix in the query prolog.</span></span> <span data-ttu-id="10362-133">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="10362-133">This is the result:</span></span>  
  
 `<ns1:root xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">`  
  
 `<ns2:ProductInfo>`  
  
 `<ns1:ProductModelID>7</ns1:ProductModelID>`  
  
 `<ns1:Name>HL Touring Frame</ns1:Name>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `LaborHours="2.5" LotSize="100" MachineHours="3" SetupHours="0.5" LocationID="10" xmlns="">`  
  
 `<MI:step>`  
  
 `Insert <MI:material>aluminum sheet MS-2341</MI:material> into the <MI:tool>T-85A framing tool</MI:tool>.`  
  
 `</MI:step>`  
  
 `...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ns2:ProductInfo>`  
  
 `</ns1:root>`  
  
## <a name="generating-a-value-list-using-path-mode"></a><span data-ttu-id="10362-134">Generar una lista de valores con el modo PATH</span><span class="sxs-lookup"><span data-stu-id="10362-134">Generating a value list using PATH mode</span></span>  
 <span data-ttu-id="10362-135">Esta consulta crea una lista de valores de Id. de productos para cada modelo de producto.</span><span class="sxs-lookup"><span data-stu-id="10362-135">For each product model, this query constructs a value list of product IDs.</span></span> <span data-ttu-id="10362-136">Además, crea elementos anidados <`ProductName`> para cada Id. de producto, tal y como se muestra en este fragmento de XML:</span><span class="sxs-lookup"><span data-stu-id="10362-136">For each product ID, the query also constructs <`ProductName`> nested elements, as shown in this XML fragment:</span></span>  
  
 `<ProductModelData ProductModelID="7" ProductModelName="..."`  
  
 `ProductIDs="product id list in the product model" >`  
  
 `<ProductName>...</ProductName>`  
  
 `<ProductName>...</ProductName>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="10362-137">Esta es la consulta que crea el XML deseado:</span><span class="sxs-lookup"><span data-stu-id="10362-137">This is the query that produces the XML you want:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID     AS "@ProductModelID",  
       Name               S "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')) S "@ProductIDs",  
       (SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
        FOR XML PATH ('')) as "ProductNames"  
FROM   Production.ProductModel  
WHERE  ProductModelID= 7 or ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="10362-138">Observe lo siguiente en la consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="10362-138">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="10362-139">El primer `SELECT` anidado devuelve una lista de ProductID usando `data()` como nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="10362-139">The first nested `SELECT` returns a list of ProductIDs by using `data()` as the column name.</span></span> <span data-ttu-id="10362-140">La consulta especifica una cadena vacía como nombre del elemento de fila en `FOR XML PATH`, por lo que no se generará ningún elemento.</span><span class="sxs-lookup"><span data-stu-id="10362-140">Because the query specifies an empty string as the row element name in `FOR XML PATH`, no element is generated.</span></span> <span data-ttu-id="10362-141">En su lugar, se asignará la lista de valores al atributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="10362-141">Instead, the value list is assigned to the `ProductID` attribute.</span></span>  
  
-   <span data-ttu-id="10362-142">El segundo `SELECT` anidado recupera nombres para los productos del modelo de producto.</span><span class="sxs-lookup"><span data-stu-id="10362-142">The second nested `SELECT` retrieves product names for products in the product model.</span></span> <span data-ttu-id="10362-143">Genera elementos <`ProductName`> que se devuelven ajustados en el elemento <`ProductNames`>, puesto que la consulta especifica `ProductNames` como nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="10362-143">It generates <`ProductName`> elements that are returned wrapped in the <`ProductNames`> element, because the query specifies `ProductNames` as the column name.</span></span>  
  
 <span data-ttu-id="10362-144">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="10362-144">This is the partial result:</span></span>  
  
 `<ProductModelData PId="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>HL Touring Frame - Yellow, 60</ProductName>`  
  
 `<ProductName>HL Touring Frame - Yellow, 46</ProductName></ProductNames>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 `<ProductModelData PId="9"`  
  
 `ProductModelName="LL Road Frame"`  
  
 `ProductIDs="722 723 724 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>LL Road Frame - Black, 58</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 60</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 62</ProductName>`  
  
 `...`  
  
 `</ProductNames>`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="10362-145">La subconsulta que crea los nombres de producto devuelve el resultado como una cadena para la que se crea una entidad y que a continuación se agrega al XML.</span><span class="sxs-lookup"><span data-stu-id="10362-145">The subquery constructing the product names returns the result as a string that is entitized and then added to the XML.</span></span> <span data-ttu-id="10362-146">Si agrega la directiva de tipo, `FOR XML PATH (''), type`, la subconsulta devolverá el resultado como un tipo `xml` y no se creará ninguna entidad.</span><span class="sxs-lookup"><span data-stu-id="10362-146">If you add the type directive, `FOR XML PATH (''), type`, the subquery returns the result as `xml` type and no entitization occurs.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@ProductModelID",  
      Name AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ProductIDs",  
       (  
       SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH (''), type  
       ) AS "ProductNames"  
  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
## <a name="adding-namespaces-in-the-resulting-xml"></a><span data-ttu-id="10362-147">Agregar espacios de nombres en el XML resultante</span><span class="sxs-lookup"><span data-stu-id="10362-147">Adding namespaces in the resulting XML</span></span>  
 <span data-ttu-id="10362-148">Tal y como se describe en el tema [Agregar espacios de nombres mediante WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), puede usar WITH XMLNAMESPACES para incluir espacios de nombres en las consultas de modo PATH.</span><span class="sxs-lookup"><span data-stu-id="10362-148">As described in [Adding Namespaces Using WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), you can use WITH XMLNAMESPACES to include namespaces in the PATH mode queries.</span></span> <span data-ttu-id="10362-149">Por ejemplo, los nombres especificados en la cláusula SELECT incluyen prefijos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="10362-149">For example, names specified in the SELECT clause include namespace prefixes.</span></span> <span data-ttu-id="10362-150">La siguiente consulta de modo `PATH` crea XML con espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="10362-150">The following `PATH` mode query constructs XML with namespaces.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
GO  
```  
  
 <span data-ttu-id="10362-151">El atributo `@xml:lang` agregado al elemento <`English`> se define en el espacio de nombres xml predefinido.</span><span class="sxs-lookup"><span data-stu-id="10362-151">The `@xml:lang` attribute added to the <`English`> element is defined in the predefined xml namespace.</span></span>  
  
 <span data-ttu-id="10362-152">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="10362-152">This is the result:</span></span>  
  
 `<Translation>`  
  
 `<English xml:lang="en">food</English>`  
  
 `<German xml:lang="ger">Essen</German>`  
  
 `</Translation>`  
  
 <span data-ttu-id="10362-153">La consulta siguiente es parecida al ejemplo C, con la diferencia de que usa `WITH XMLNAMESPACES` para incluir espacios de nombres en el XML resultante.</span><span class="sxs-lookup"><span data-stu-id="10362-153">The following query is similar to example C, except that it uses `WITH XMLNAMESPACES` to include namespaces in the XML result.</span></span> <span data-ttu-id="10362-154">Para obtener más información, vea [Agregar espacios de nombres a consultas con WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="10362-154">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES ('uri1' AS ns1,  DEFAULT 'uri2')  
SELECT ProductModelID AS "@ns1:ProductModelID",  
      Name AS "@ns1:ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ns1:ProductIDs",  
       (  
       SELECT ProductID AS "@ns1:ProductID",   
              Name AS "@ns1:ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH , type   
       ) AS "ns1:ProductNames"  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData'), root('root');  
```  
  
 <span data-ttu-id="10362-155">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="10362-155">This is the result:</span></span>  
  
 `<root xmlns="uri2" xmlns:ns1="uri1">`  
  
 `<ProductModelData ns1:ProductModelID="7" ns1:ProductModelName="HL Touring Frame" ns1:ProductIDs="885 887 888 889 890 891 892 893">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="885" ns1:ProductName="HL Touring Frame - Yellow, 60" />`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="887" ns1:ProductName="HL Touring Frame - Yellow, 46" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData ns1:ProductModelID="9" ns1:ProductModelName="LL Road Frame" ns1:ProductIDs="722 723 724 725 726 727 728 729 730 736 737 738">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="722" ns1:ProductName="LL Road Frame - Black, 58" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `</root>`  
  
## <a name="see-also"></a><span data-ttu-id="10362-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10362-156">See Also</span></span>  
 [<span data-ttu-id="10362-157">Usar el modo PATH con FOR XML</span><span class="sxs-lookup"><span data-stu-id="10362-157">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
