---
title: Dar forma a XML con consultas FOR XML anidadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], nested FOR XML
- XML [SQL Server], FOR XML queries
ms.assetid: 8dc42c05-16e8-4b7b-a5d3-550b55acae26
author: rothja
ms.author: jroth
ms.openlocfilehash: 738b5b3ec67dada90c851d284ccc8b3009a51aa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674671"
---
# <a name="shape-xml-with-nested-for-xml-queries"></a><span data-ttu-id="83176-102">Dar forma a XML con consultas FOR XML anidadas</span><span class="sxs-lookup"><span data-stu-id="83176-102">Shape XML with Nested FOR XML Queries</span></span>
  <span data-ttu-id="83176-103">En el ejemplo siguiente se consulta la tabla `Production.Product` para recuperar los valores `ListPrice` y `StandardCost` de un producto específico.</span><span class="sxs-lookup"><span data-stu-id="83176-103">The following example queries the `Production.Product` table to retrieve the `ListPrice` and `StandardCost` values of a specific product.</span></span> <span data-ttu-id="83176-104">Para hacer interesante la consulta, se devuelven ambos precios en un elemento <`Price`>, y cada elemento <`Price`> tiene un atributo `PriceType`.</span><span class="sxs-lookup"><span data-stu-id="83176-104">To make the query interesting, both prices are returned in a <`Price`> element, and each <`Price`> element has a `PriceType` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83176-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83176-105">Example</span></span>  
 <span data-ttu-id="83176-106">Ésta es la forma esperada del XML:</span><span class="sxs-lookup"><span data-stu-id="83176-106">This is the expected shape of the XML:</span></span>  
  
```  
<xsd:schema xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet2" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet2" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.Product" type="xsd:anyType" />  
</xsd:schema>  
<Production.Product xmlns="urn:schemas-microsoft-com:sql:SqlRowSet2" ProductID="520">  
  <Price xmlns="" PriceType="ListPrice">133.34</Price>  
  <Price xmlns="" PriceType="StandardCost">98.77</Price>  
</Production.Product>  
```  
  
 <span data-ttu-id="83176-107">Esta es la consulta FOR XML anidada:</span><span class="sxs-lookup"><span data-stu-id="83176-107">This is the nested FOR XML query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Product.ProductID,   
          (SELECT 'ListPrice' as PriceType,   
                   CAST(CAST(ListPrice as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE),  
          (SELECT  'StandardCost' as PriceType,   
                   CAST(CAST(StandardCost as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE)  
FROM Production.Product  
WHERE ProductID=520  
for XML AUTO, TYPE, XMLSCHEMA  
```  
  
 <span data-ttu-id="83176-108">Observe lo siguiente en la consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="83176-108">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="83176-109">La instrucción SELECT externa construye el elemento <`Product`> que tiene un atributo **ProductID** y dos secundarios <`Price`>.</span><span class="sxs-lookup"><span data-stu-id="83176-109">The outer SELECT statement constructs the <`Product`> element that has a **ProductID** attribute and two <`Price`> child elements.</span></span>  
  
-   <span data-ttu-id="83176-110">Las dos instrucciones SELECT internas construyen dos elementos <`Price`>, cada uno con un atributo **PriceType** y XML que devuelve el precio del producto.</span><span class="sxs-lookup"><span data-stu-id="83176-110">The two inner SELECT statements construct two <`Price`> elements, each with a **PriceType** attribute and XML that returns the product price.</span></span>  
  
-   <span data-ttu-id="83176-111">La directiva XMLSCHEMA de la instrucción SELECT externa genera el esquema XSD insertado que describe la forma del XML resultante.</span><span class="sxs-lookup"><span data-stu-id="83176-111">The XMLSCHEMA directive in the outer SELECT statement generates the inline XSD schema that describes the shape of the resulting XML.</span></span>  
  
 <span data-ttu-id="83176-112">Para hacer interesante la consulta, puede escribir la consulta FOR XML y después escribir una consulta XQuery para el resultado con el fin de cambiar la forma del XML, como se muestra en la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="83176-112">To make the query interesting, you can write the FOR XML query and then write an XQuery against the result to reshape the XML, as shown in the following query:</span></span>  
  
```  
SELECT ProductID,   
 ( SELECT p2.ListPrice, p2.StandardCost  
   FROM Production.Product p2   
   WHERE Product.ProductID = p2.ProductID  
   FOR XML AUTO, ELEMENTS XSINIL, type ).query('  
                                   for $p in /p2/*  
                                   return   
                                    <Price PriceType = "{local-name($p)}">  
                                     { data($p) }  
                                    </Price>  
                                  ')  
FROM Production.Product  
WHERE ProductID = 520  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="83176-113">En el ejemplo anterior se utiliza el método `query()` del tipo de datos `xml` para consultar el XML devuelto por la consulta FOR XML interna y construir el resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="83176-113">The previous example uses the `query()` method of the `xml` data type to query the XML returned by the inner FOR XML query and construct the expected result.</span></span>  
  
 <span data-ttu-id="83176-114">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="83176-114">This is the result:</span></span>  
  
```  
<Production.Product ProductID="520">  
  <Price PriceType="ListPrice">133.3400</Price>  
  <Price PriceType="StandardCost">98.7700</Price>  
</Production.Product>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83176-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83176-115">See Also</span></span>  
 [<span data-ttu-id="83176-116">Usar consultas FOR XML anidadas</span><span class="sxs-lookup"><span data-stu-id="83176-116">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
