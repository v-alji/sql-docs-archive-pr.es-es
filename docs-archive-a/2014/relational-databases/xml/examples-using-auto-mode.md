---
title: 'Ejemplos: Uso del modo AUTO | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- AUTO FOR XML mode, examples
ms.assetid: 11e8d0e4-df8a-46f8-aa21-9602d4f26cad
author: rothja
ms.author: jroth
ms.openlocfilehash: b457bca6b7c25b9822e3dab2eba5f5cdb04b83e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662690"
---
# <a name="examples-using-auto-mode"></a><span data-ttu-id="02105-102">Ejemplos: Uso del modo AUTO</span><span class="sxs-lookup"><span data-stu-id="02105-102">Examples: Using AUTO Mode</span></span>
  <span data-ttu-id="02105-103">Los siguientes ejemplos ilustran el uso del modo AUTO.</span><span class="sxs-lookup"><span data-stu-id="02105-103">The following examples illustrate the use of AUTO mode.</span></span> <span data-ttu-id="02105-104">Muchas de estas consultas se especifican utilizando los documentos XML de instrucciones de fabricación de bicicletas almacenados en la columna Instructions de la tabla ProductModel en la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="02105-104">Many of these queries are specified against bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>  
  
## <a name="example-retrieving-customer-order-and-order-detail-information"></a><span data-ttu-id="02105-105">Ejemplo: Recuperación de información de cliente, pedido y detalle del pedido</span><span class="sxs-lookup"><span data-stu-id="02105-105">Example: Retrieving customer, order, and order detail information</span></span>  
 <span data-ttu-id="02105-106">Esta consulta recupera información del cliente, pedidos y pedidos detallados de un cliente específico.</span><span class="sxs-lookup"><span data-stu-id="02105-106">This query retrieves customer, order, and order detail information for a specific customer.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Cust.CustomerID,   
       OrderHeader.CustomerID,  
       OrderHeader.SalesOrderID,   
       Detail.SalesOrderID, Detail.LineTotal, Detail.ProductID,   
       Product.Name,  
       Detail.OrderQty  
FROM Sales.Customer AS Cust  
INNER JOIN Sales.SalesOrderHeader AS OrderHeader   
    ON Cust.CustomerID = OrderHeader.CustomerID  
INNER JOIN Sales.SalesOrderDetail AS Detail  
    ON OrderHeader.SalesOrderID = Detail.SalesOrderID  
INNER JOIN Production.Product AS Product  
    ON Product.ProductID = Detail.ProductID  
WHERE Cust.CustomerID IN (29672, 29734)  
ORDER BY OrderHeader.CustomerID,  
         OrderHeader.SalesOrderID  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="02105-107">Dado que la consulta identifica los alias de tabla `Cust`, `OrderHeader`, `Detail`y `Product` , el modo `AUTO` genera los elementos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="02105-107">Because the query identifies, `Cust`, `OrderHeader`, `Detail`, and `Product` table aliases, corresponding elements are generated by the `AUTO` mode.</span></span> <span data-ttu-id="02105-108">De nuevo, el orden en que se identifican las tablas mediante las columnas especificadas en la cláusula `SELECT` determina la jerarquía de estos elementos.</span><span class="sxs-lookup"><span data-stu-id="02105-108">Again, the order in which tables are identified by the columns specified in the `SELECT` clause determine the hierarchy of these elements.</span></span>  
  
 <span data-ttu-id="02105-109">El resultado parcial es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="02105-109">This is the partial result.</span></span>  
  
 `<Cust CustomerID="29672">`  
  
 `<OrderHeader CustomerID="29672" SalesOrderID="43660">`  
  
 `<Detail SalesOrderID="43660" LineTotal="874.794000" ProductID="758" OrderQty="1">`  
  
 `<Product Name="Road-450 Red, 52" />`  
  
 `</Detail>`  
  
 `<Detail SalesOrderID="43660" LineTotal="419.458900" ProductID="762" OrderQty="1">`  
  
 `<Product Name="Road-650 Red, 44" />`  
  
 `</Detail>`  
  
 `</OrderHeader>`  
  
 `<OrderHeader CustomerID="29672" SalesOrderID="47660">`  
  
 `<Detail SalesOrderID="47660" LineTotal="469.794000" ProductID="765" OrderQty="1">`  
  
 `<Product Name="Road-650 Black, 58" />`  
  
 `</Detail>`  
  
 `</OrderHeader>`  
  
 `<OrderHeader CustomerID="29672" SalesOrderID="49857">`  
  
 `<Detail SalesOrderID="49857" LineTotal="44.994000" ProductID="852" OrderQty="1">`  
  
 `<Product Name="Women's Tights, S" />`  
  
 `</Detail>`  
  
 `</OrderHeader>`  
  
 `...`  
  
 `</Cust>`  
  
## <a name="example-specifying-group-by-and-aggregate-functions"></a><span data-ttu-id="02105-110">Ejemplo: Especificación de GROUP BY y funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="02105-110">Example: Specifying GROUP BY and aggregate functions</span></span>  
 <span data-ttu-id="02105-111">La consulta siguiente devuelve los identificadores de cliente individuales y el número de pedidos que ha solicitado el cliente.</span><span class="sxs-lookup"><span data-stu-id="02105-111">The following query returns individual customer IDs and the number of orders that the customer has requested.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT C.CustomerID, COUNT(*) AS NoOfOrders  
FROM Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
On C.CustomerID = SOH.CustomerID  
GROUP BY C.CustomerID  
FOR XML AUTO;This is the partial result:  
```  
  
 `<I CustomerID="11000" NoOfOrders="3" />`  
  
 `<I CustomerID="11001" NoOfOrders="3" />`  
  
 `...`  
  
## <a name="example-specifying-computed-columns-in-auto-mode"></a><span data-ttu-id="02105-112">Ejemplo: Especificación de columnas calculadas en el modo AUTO</span><span class="sxs-lookup"><span data-stu-id="02105-112">Example: Specifying computed columns in AUTO mode</span></span>  
 <span data-ttu-id="02105-113">Esta consulta devuelve nombres de cliente individuales concatenados y la información de los pedidos.</span><span class="sxs-lookup"><span data-stu-id="02105-113">This query returns concatenated individual customer names and the order information.</span></span> <span data-ttu-id="02105-114">La columna calculada se asigna al nivel más interno de ese punto, el elemento <`SOH`> en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02105-114">Because the computed column is assigned to the innermost level encountered at that point, the <`SOH`> element in this example.</span></span> <span data-ttu-id="02105-115">Los nombres de cliente concatenados se agregan como atributos del elemento <`SOH`> en el resultado.</span><span class="sxs-lookup"><span data-stu-id="02105-115">The concatenated customer names are added as attributes of the <`SOH`> element in the result.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT P.FirstName + ' ' + P.LastName AS Name,  
       SOH.SalesOrderID  
FROM Sales.Customer AS C  
INNER JOIN Sales.SalesOrderHeader AS SOH  
    ON  C.CustomerID = SOH.CustomerID  
INNER JOIN Person.Person AS P  
    ON P.BusinessEntityID = C.PersonID  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="02105-116">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="02105-116">This is the partial result:</span></span>  
  
```  
<SOH Name="Jon Yang" SalesOrderID="43793" />  
<SOH Name="Eugene Huang" SalesOrderID="43767" />  
```  
  
 <span data-ttu-id="02105-117">Para recuperar los elementos <`IndividualCustomer`> que tienen el atributo `Name` que contiene la información de encabezado de cada pedido de ventas como un subelemento, la consulta se escribe de nuevo utilizando una instrucción sub select.</span><span class="sxs-lookup"><span data-stu-id="02105-117">To retrieve the <`IndividualCustomer`> elements having the `Name` attribute that contains each sales order header information as a subelement, the query is rewritten using a sub select.</span></span> <span data-ttu-id="02105-118">La selección interna crea una tabla `IndividualCustomer` temporal con la columna calculada que contiene los nombres de los clientes individuales.</span><span class="sxs-lookup"><span data-stu-id="02105-118">The inner select creates a temporary `IndividualCustomer` table with the computed column that contains the names of the individual customers.</span></span> <span data-ttu-id="02105-119">Esta tabla se combina después con la tabla `SalesOrderHeader` para obtener el resultado.</span><span class="sxs-lookup"><span data-stu-id="02105-119">This table is then joined to the `SalesOrderHeader` table to obtain the result.</span></span>  
  
 <span data-ttu-id="02105-120">Observe que la tabla `Sales.Customer` almacena información de clientes individuales, incluido el valor `PersonID` del cliente.</span><span class="sxs-lookup"><span data-stu-id="02105-120">Note that the `Sales.Customer` table stores individual customer information, including the `PersonID` value for that customer.</span></span> <span data-ttu-id="02105-121">Este `PersonID` se utiliza después para buscar el nombre de contacto en la tabla `Person.Person` .</span><span class="sxs-lookup"><span data-stu-id="02105-121">This `PersonID` is then used to find the contact name from the `Person.Person` table.</span></span>  
  
```  
SELECT IndividualCustomer.Name, SOH.SalesOrderID  
FROM (SELECT FirstName+ ' '+LastName AS Name, C.PersonID, C.CustomerID  
      FROM Sales.Customer AS C, Person.Person AS P  
      WHERE C.PersonID = P.BusinessEntityID) AS IndividualCustomer  
LEFT OUTER JOIN  Sales.SalesOrderHeader AS SOH  
   ON IndividualCustomer.CustomerID = SOH.CustomerID  
ORDER BY IndividualCustomer.CustomerID, SOH.CustomerIDFOR XML AUTO;  
```  
  
 <span data-ttu-id="02105-122">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="02105-122">This is the partial result:</span></span>  
  
 `<IndividualCustomer Name="Jon Yang">`  
  
 `<SOH SalesOrderID="43793" />`  
  
 `<SOH SalesOrderID="51522" />`  
  
 `<SOH SalesOrderID="57418" />`  
  
 `</IndividualCustomer>`  
  
 `...`  
  
 `...`  
  
## <a name="example-returning-binary-data"></a><span data-ttu-id="02105-123">Ejemplo: Devolución de datos binarios</span><span class="sxs-lookup"><span data-stu-id="02105-123">Example: Returning binary data</span></span>  
 <span data-ttu-id="02105-124">Esta consulta devuelve una fotografía del producto de la tabla `ProductPhoto` .</span><span class="sxs-lookup"><span data-stu-id="02105-124">This query returns a product photo from the `ProductPhoto` table.</span></span> <span data-ttu-id="02105-125">`ThumbNailPhoto` es una columna `varbinary(max)` de la tabla `ProductPhoto`.</span><span class="sxs-lookup"><span data-stu-id="02105-125">`ThumbNailPhoto` is an `varbinary(max)` column in the `ProductPhoto` table.</span></span> <span data-ttu-id="02105-126">De manera predeterminada, el modo `AUTO` devuelve a los datos binarios una referencia que es una dirección URL relativa de la raíz virtual de la base de datos donde se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="02105-126">By default, `AUTO` mode returns to the binary data a reference that is a relative URL to the virtual root of the database where the query is executed.</span></span> <span data-ttu-id="02105-127">Se debe especificar el atributo clave `ProductPhotoID` para identificar la imagen.</span><span class="sxs-lookup"><span data-stu-id="02105-127">The `ProductPhotoID` key attribute must be specified to identify the image.</span></span> <span data-ttu-id="02105-128">Al recuperar la referencia de una imagen como se muestra en este ejemplo, también debe especificarse la clave principal en la cláusula `SELECT` para identificar una fila de forma única.</span><span class="sxs-lookup"><span data-stu-id="02105-128">In retrieving an image reference as illustrated in this example, the primary key of the table must also be specified in the `SELECT` clause to uniquely identify a row.</span></span>  
  
```  
SELECT ProductPhotoID, ThumbNailPhoto  
FROM   Production.ProductPhoto   
WHERE ProductPhotoID=70  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="02105-129">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="02105-129">This is the result:</span></span>  
  
 `-- result`  
  
 `<Production.ProductPhoto`  
  
 `ProductPhotoID="70"`  
  
 `ThumbNailPhoto= "dbobject/Production.ProductPhoto[@ProductPhotoID='70']/@ThumbNailPhoto" />`  
  
 <span data-ttu-id="02105-130">La misma consulta se ejecuta con la opción `BINARY BASE64` .</span><span class="sxs-lookup"><span data-stu-id="02105-130">The same query is executed with the `BINARY BASE64` option.</span></span> <span data-ttu-id="02105-131">La consulta devuelve los datos binarios en formato codificado en base64.</span><span class="sxs-lookup"><span data-stu-id="02105-131">The query returns the binary data in base64-encoded format.</span></span>  
  
```  
SELECT ProductPhotoID, ThumbNailPhoto  
FROM   Production.ProductPhoto   
WHERE ProductPhotoID=70  
FOR XML AUTO, BINARY BASE64;  
```  
  
 <span data-ttu-id="02105-132">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="02105-132">This is the result:</span></span>  
  
 `-- result`  
  
 `<Production.ProductPhoto ProductPhotoID="70" ThumbNailPhoto="Base64 encoded photo" />`  
  
 <span data-ttu-id="02105-133">De forma predeterminada, cuando se utiliza el modo AUTO para recuperar datos binarios, se devuelve una referencia a una dirección URL relativa a la raíz virtual de la base de datos donde se ejecutó la consulta en lugar de datos binarios.</span><span class="sxs-lookup"><span data-stu-id="02105-133">By default, when you use AUTO mode to retrieve binary data, a reference to a relative URL to the virtual root of the database where the query was executed will be returned instead of the binary data.</span></span> <span data-ttu-id="02105-134">Esto ocurre si no se especifica la opción BINARY BASE64.</span><span class="sxs-lookup"><span data-stu-id="02105-134">This will occur if the BINARY BASE64 option is not specified.</span></span>  
  
 <span data-ttu-id="02105-135">Cuando el modo AUTO devuelve una referencia de URL a los datos binarios de bases de datos que no distinguen mayúsculas y minúsculas y donde un nombre de tabla o columna especificado en la consulta no coincide con el nombre de tabla o columna de la base de datos, se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="02105-135">When AUTO mode returns a URL reference to the binary data in case-insensitive databases where a table or column name specified in the query does not match the table or column name in the database, the query executes.</span></span> <span data-ttu-id="02105-136">Sin embargo, las mayúsculas o minúsculas devueltas en la referencia no serán coherentes.</span><span class="sxs-lookup"><span data-stu-id="02105-136">However, the case returned in the reference will not be consistent.</span></span> <span data-ttu-id="02105-137">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="02105-137">For example:</span></span>  
  
```  
SELECT ProductPhotoID, ThumbnailPhoto  
FROM   Production.ProductPhoto   
WHERE  ProductPhotoID=70  
FOR XML AUTO;  
```  
  
 <span data-ttu-id="02105-138">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="02105-138">This is the result:</span></span>  
  
 `<Production.PRODUCTPHOTO`  
  
 `PRODUCTPHOTOID="70"`  
  
 `THUMBNAILPHOTO= "dbobject/Production.PRODUCTPHOTO[@ProductPhotoID='70']/@ThumbNailPhoto" />`  
  
 <span data-ttu-id="02105-139">Eso puede ser un problema especialmente cuando se ejecutan consultas dbobject en una base de datos que distingue mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="02105-139">This can be a problem particularly when dbobject queries are executed against a case sensitive database.</span></span> <span data-ttu-id="02105-140">Para evitarlo, el formato de mayúsculas y minúsculas del nombre de tabla o columna especificado en las consultas debe coincidir con el formato de mayúsculas y minúsculas del nombre de tabla o columna de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="02105-140">To avoid this, the case of the table or column name that is specified in the queries should match the case of the table or column name in the database.</span></span>  
  
## <a name="example-understanding-the-encoding"></a><span data-ttu-id="02105-141">Ejemplo: Descripción de la codificación</span><span class="sxs-lookup"><span data-stu-id="02105-141">Example: Understanding the encoding</span></span>  
 <span data-ttu-id="02105-142">Este ejemplo muestra varias codificaciones que tienen lugar en el resultado.</span><span class="sxs-lookup"><span data-stu-id="02105-142">This example shows the various encoding that occurs in the result.</span></span>  
  
 <span data-ttu-id="02105-143">Cree esta tabla:</span><span class="sxs-lookup"><span data-stu-id="02105-143">Create this table:</span></span>  
  
```  
CREATE TABLE [Special Chars] (Col1 char(1) primary key, [Col#&2] varbinary(50));  
```  
  
 <span data-ttu-id="02105-144">Agregue los siguientes datos a la tabla:</span><span class="sxs-lookup"><span data-stu-id="02105-144">Add the following data to the table:</span></span>  
  
```  
INSERT INTO [Special Chars] VALUES ('&', 0x20), ('#', 0x20);  
```  
  
 <span data-ttu-id="02105-145">Esta consulta devuelve los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="02105-145">This query returns the data from the table.</span></span> <span data-ttu-id="02105-146">El modo FOR XML AUTO está especificado.</span><span class="sxs-lookup"><span data-stu-id="02105-146">The FOR XML AUTO mode is specified.</span></span> <span data-ttu-id="02105-147">Los datos binarios se devuelven como una referencia.</span><span class="sxs-lookup"><span data-stu-id="02105-147">Binary data is returned as a reference.</span></span>  
  
```  
SELECT * FROM [Special Chars] FOR XML AUTO;  
```  
  
 <span data-ttu-id="02105-148">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="02105-148">This is the result:</span></span>  
  
 `<Special_x0020_Chars`  
  
 `Col1="#"`  
  
 `Col_x0023__x0026_2="dbobject/Special_x0020_Chars[@Col1='#']/@Col_x0023__x0026_2"`  
  
 `/>`  
  
 `<Special_x0020_Chars`  
  
 `Col1="&"`  
  
 `Col_x0023__x0026_2="dbobject/Special_x0020_Chars[@Col1='&']/@Col_x0023__x0026_2"`  
  
 `/>`  
  
 <span data-ttu-id="02105-149">Éste es el proceso para codificar caracteres especiales en el resultado:</span><span class="sxs-lookup"><span data-stu-id="02105-149">This is the process for encoding special characters in the result:</span></span>  
  
-   <span data-ttu-id="02105-150">En el de resultado de la consulta, los caracteres especiales XML y URL de los nombres del elemento y atributo devueltos se codifican mediante el valor hexadecimal del carácter Unicode correspondiente.</span><span class="sxs-lookup"><span data-stu-id="02105-150">In the query result, the special XML and URL characters in the element and attribute names that are returned are encoded by using the hexadecimal value of the corresponding Unicode character.</span></span> <span data-ttu-id="02105-151">En el resultado anterior, el nombre de elemento <`Special Chars`> se devuelve como <`Special_x0020_Chars`>.</span><span class="sxs-lookup"><span data-stu-id="02105-151">In the previous result, the element name <`Special Chars`> is returned as <`Special_x0020_Chars`>.</span></span> <span data-ttu-id="02105-152">El nombre del atributo <`Col#&2`> se devuelve como <`Col_x0023__x0026_2`>.</span><span class="sxs-lookup"><span data-stu-id="02105-152">The attribute name <`Col#&2`> is returned as <`Col_x0023__x0026_2`>.</span></span> <span data-ttu-id="02105-153">Los caracteres especiales XML y URL están codificados.</span><span class="sxs-lookup"><span data-stu-id="02105-153">Both XML and URL special characters are encoded.</span></span>  
  
-   <span data-ttu-id="02105-154">Si los valores de los elementos o atributos contienen alguna de las cinco entidades de carácter XML estándar (', "", \<, > y &), estos caracteres XML especiales se codifican siempre mediante la codificación de caracteres XML.</span><span class="sxs-lookup"><span data-stu-id="02105-154">If the values of the elements or attribute contain any of the five standard XML character entities (', "", \<, >, and &), these special XML characters are always encoded using XML character encoding.</span></span> <span data-ttu-id="02105-155">En el resultado anterior, el valor `&` del valor de atributo <`Col1`> está codificado como `&`.</span><span class="sxs-lookup"><span data-stu-id="02105-155">In the previous result, the value `&` in the value of attribute <`Col1`> is encoded as `&`.</span></span> <span data-ttu-id="02105-156">Sin embargo, el carácter # permanece como #, porque es un carácter XML válido y no un carácter XML especial.</span><span class="sxs-lookup"><span data-stu-id="02105-156">However, the # character remains #, because it is a valid XML character and not a special XML character.</span></span>  
  
-   <span data-ttu-id="02105-157">Si los valores de los elementos o atributos contienen caracteres especiales de dirección URL que tienen un significado especial en la dirección URL, solo se codifican en el valor DBOBJECT de la dirección URL y únicamente cuando el carácter especial forma parte de un nombre de columna o tabla.</span><span class="sxs-lookup"><span data-stu-id="02105-157">If the values of the elements or attributes contain any special URL characters that have special meaning in the URL, they are encoded only in the DBOBJECT URL value and are encoded only when the special character is part of a table or column name.</span></span> <span data-ttu-id="02105-158">En el resultado, el carácter `#` que forma parte del nombre de la tabla `Col#&2` se codifica como `_x0023_ in the DBOJBECT URL`.</span><span class="sxs-lookup"><span data-stu-id="02105-158">In the result, the character `#` that is part of table name `Col#&2` is encoded as `_x0023_ in the DBOJBECT URL`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02105-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="02105-159">See Also</span></span>  
 [<span data-ttu-id="02105-160">Usar el modo AUTO con FOR XML</span><span class="sxs-lookup"><span data-stu-id="02105-160">Use AUTO Mode with FOR XML</span></span>](use-auto-mode-with-for-xml.md)  
  
  