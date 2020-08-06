---
title: Directiva TYPE en consultas FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, TYPE directive
- TYPE directive
ms.assetid: a3df6c30-1f25-45dc-b5a9-bd0e41921293
author: rothja
ms.author: jroth
ms.openlocfilehash: cddce90718ef5edfcf161ddc6cc52b617825a2e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677445"
---
# <a name="type-directive-in-for-xml-queries"></a><span data-ttu-id="6a40f-102">Directiva TYPE en consultas FOR XML</span><span class="sxs-lookup"><span data-stu-id="6a40f-102">TYPE Directive in FOR XML Queries</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="6a40f-103">la compatibilidad con [xml &#40;&#41;de Transact-SQL](/sql/t-sql/xml/xml-transact-sql) permite solicitar opcionalmente que el resultado de una consulta for XML se devuelva como `xml` tipo de datos especificando la Directiva Type.</span><span class="sxs-lookup"><span data-stu-id="6a40f-103">support for the [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) enables you to optionally request that the result of a FOR XML query be returned as `xml` data type by specifying the TYPE directive.</span></span> <span data-ttu-id="6a40f-104">Esto permite procesar el resultado de una consulta FOR XML en el servidor.</span><span class="sxs-lookup"><span data-stu-id="6a40f-104">This allows you to process the result of a FOR XML query on the server.</span></span> <span data-ttu-id="6a40f-105">Por ejemplo, puede especificar una expresión XQuery en ella, asignar el resultado a una `xml` variable de tipo o escribir [consultas for XML anidadas](use-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6a40f-105">For example, you can specify an XQuery against it, assign the result to an `xml` type variable, or write [Nested FOR XML queries](use-nested-for-xml-queries.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6a40f-106">devuelve al cliente datos de instancia de tipo XML como resultado de distintas construcciones de servidor, como por ejemplo consultas FOR XML que utilizan la directiva TYPE o en las que se utiliza el tipo de datos `xml` para devolver valores de datos de instancia XML procedentes de columnas de tablas SQL y parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="6a40f-106">returns XML data type instance data to the client as a result of different server-constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML instance data values from SQL table columns and output parameters.</span></span> <span data-ttu-id="6a40f-107">En el código de las aplicaciones cliente, el proveedor ADO.NET solicita que se envíe esta información de tipo de datos XML con una codificación binaria desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="6a40f-107">In client application code, the ADO.NET provider requests this XML data type information to be sent in a binary encoding from the server.</span></span> <span data-ttu-id="6a40f-108">Sin embargo, si utiliza FOR XML sin la directiva TYPE, se devolverán los datos XML en forma de cadena.</span><span class="sxs-lookup"><span data-stu-id="6a40f-108">However, if you are using FOR XML without the TYPE directive, the XML data comes back as a string type.</span></span> <span data-ttu-id="6a40f-109">En cualquier caso, el proveedor del cliente siempre podrá controlar cualquier formato de tipo XML.</span><span class="sxs-lookup"><span data-stu-id="6a40f-109">In any case, the client provider will always be able to handle either form of XML.</span></span> <span data-ttu-id="6a40f-110">Tenga en cuenta que la cláusula FOR XML de nivel superior sin la directiva TYPE no puede utilizarse con cursores.</span><span class="sxs-lookup"><span data-stu-id="6a40f-110">Note that top-level FOR XML without the TYPE directive cannot be used with cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6a40f-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6a40f-111">Examples</span></span>  
 <span data-ttu-id="6a40f-112">En los ejemplos siguientes se muestra el uso de la directiva TYPE con consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="6a40f-112">The following examples illustrate the use of the TYPE directive with FOR XML queries.</span></span>  
  
### <a name="retrieving-for-xml-query-results-as-xml-type"></a><span data-ttu-id="6a40f-113">Recuperar resultados de consultas FOR XML en forma de xml</span><span class="sxs-lookup"><span data-stu-id="6a40f-113">Retrieving FOR XML query results as xml type</span></span>  
 <span data-ttu-id="6a40f-114">En la consulta siguiente se recupera información de contacto de clientes de la tabla `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="6a40f-114">The following query retrieves customer contact information from the `Contacts` table.</span></span> <span data-ttu-id="6a40f-115">Puesto que se especifica la directiva `TYPE` en `FOR XML`, el resultado se devuelve como de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6a40f-115">Because the `TYPE` directive is specified in `FOR XML`, the result is returned as `xml` type.</span></span>  
  
```  
USE AdventureWorks2012;  
Go  
SELECT BusinessEntityID, FirstName, LastName  
FROM Person.Person  
ORDER BY BusinessEntityID  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="6a40f-116">Éste es el resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="6a40f-116">This is the partial result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez"/>`  
  
 `<Person.Person BusinessEntityID="2" FirstName="Terri" LastName="Duffy"/>`  
  
 `...`  
  
### <a name="assigning-for-xml-query-results-to-an-xml-type-variable"></a><span data-ttu-id="6a40f-117">Asignar resultados de consultas FOR XML a una variable de tipo xml</span><span class="sxs-lookup"><span data-stu-id="6a40f-117">Assigning FOR XML query results to an xml type variable</span></span>  
 <span data-ttu-id="6a40f-118">En el ejemplo siguiente, se asigna un resultado de FOR XML a una variable de tipo `xml`, `@x`.</span><span class="sxs-lookup"><span data-stu-id="6a40f-118">In the following example, a FOR XML result is assigned to an `xml` type variable, `@x`.</span></span> <span data-ttu-id="6a40f-119">La consulta recupera información de contacto, como `BusinessEntityID` , `FirstName` , `LastName` y números de teléfono adicionales, de la `AdditionalContactInfo` columna de `xml``TYPE` .</span><span class="sxs-lookup"><span data-stu-id="6a40f-119">The query retrieves contact information, such as the `BusinessEntityID`, `FirstName`, `LastName`, and additional telephone numbers, from the `AdditionalContactInfo` column of `xml``TYPE`.</span></span> <span data-ttu-id="6a40f-120">Puesto que la cláusula `FOR XML` especifica la directiva `TYPE`, se devuelve XML en forma de tipo `xml` y se asigna a una variable.</span><span class="sxs-lookup"><span data-stu-id="6a40f-120">Because the `FOR XML` clause specifies `TYPE` directive, the XML is returned as `xml` type and is assigned to a variable.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @x xml;  
SET @x = (  
   SELECT BusinessEntityID,   
          FirstName,   
          LastName,   
          AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
              //act:telephoneNumber/act:number') as MorePhoneNumbers  
   FROM Person.Person  
   FOR XML AUTO, TYPE);  
SELECT @x;  
GO  
```  
  
### <a name="querying-results-of-a-for-xml-query"></a><span data-ttu-id="6a40f-121">Consultar los resultados de una consulta FOR XML</span><span class="sxs-lookup"><span data-stu-id="6a40f-121">Querying results of a FOR XML query</span></span>  
 <span data-ttu-id="6a40f-122">Las consultas FOR XML devuelven XML.</span><span class="sxs-lookup"><span data-stu-id="6a40f-122">The FOR XML queries return XML.</span></span> <span data-ttu-id="6a40f-123">Por tanto, puede aplicar métodos del tipo `xml`, como `query()` y `value()`, al resultado XML devuelto por las consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="6a40f-123">Therefore, you can apply `xml` type methods, such as `query()` and `value()`, to the XML result returned by FOR XML queries.</span></span>  
  
 <span data-ttu-id="6a40f-124">En la consulta siguiente, se utiliza el método `query()` del tipo de datos `xml` para consultar el resultado de la consulta `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="6a40f-124">In the following query, the `query()` method of the `xml` data type is used to query the result of the `FOR XML` query.</span></span> <span data-ttu-id="6a40f-125">Para obtener más información, vea [query&#40;&#41; &#40;método de tipo de datos xml&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="6a40f-125">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT (SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
DECLARE namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
DECLARE namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
 //act:telephoneNumber/act:number  
') AS PhoneNumbers  
FROM Person.Person  
FOR XML AUTO, TYPE).query('/Person.Person[1]');  
```  
  
 <span data-ttu-id="6a40f-126">La consulta `SELECT ... FOR XML` interna devuelve un resultado de tipo `xml` al que la instrucción `SELECT` externa aplica el método `query()` al tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6a40f-126">The inner `SELECT ... FOR XML` query returns an `xml` type result to which the outer `SELECT` applies the `query()` method to the `xml` type.</span></span> <span data-ttu-id="6a40f-127">Observe la directiva `TYPE` especificada.</span><span class="sxs-lookup"><span data-stu-id="6a40f-127">Note the `TYPE` directive specified.</span></span>  
  
 <span data-ttu-id="6a40f-128">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="6a40f-128">This is the result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez">`  
  
 `<PhoneNumbers>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">111-111-1111</act:number>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">112-111-1111</act:number>`  
  
 `</PhoneNumbers>`  
  
 `</Person.Person>`  
  
 <span data-ttu-id="6a40f-129">En la consulta siguiente, el método `value()` del tipo de datos `xml` se utiliza para recuperar un valor del resultado XML devuelto por la consulta `SELECT...FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="6a40f-129">In the following query, the `value()` method of the `xml` data type is used to retrieve a value from the XML result returned by the `SELECT...FOR XML` query.</span></span> <span data-ttu-id="6a40f-130">Para obtener más información, vea [value&#40;&#41; &#40;método de tipo de datos xml&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="6a40f-130">For more information, see [value&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @FirstPhoneFromAdditionalContactInfo varchar(40);  
SELECT @FirstPhoneFromAdditionalContactInfo =   
 ( SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
   //act:telephoneNumber/act:number  
   ') AS PhoneNumbers  
   FROM Person.Person Contact  
   FOR XML AUTO, TYPE).value('  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
  /Contact[@BusinessEntityID="1"][1]/PhoneNumbers[1]/act:number[1]', 'varchar(40)'  
 )  
SELECT @FirstPhoneFromAdditionalContactInfo;  
```  
  
 <span data-ttu-id="6a40f-131">La expresión de ruta de acceso XQuery del método `value()` recupera el primer número de teléfono de un contacto de cliente cuyo `BusinessEntityID` es `1`.</span><span class="sxs-lookup"><span data-stu-id="6a40f-131">The XQuery path expression in the `value()` method retrieves the first telephone number of a customer contact whose `BusinessEntityID` is `1`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6a40f-132">Si no se especifica la directiva TYPE, se devolverá el resultado de la consulta FOR XML con el tipo `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="6a40f-132">If the TYPE directive is not specified, the FOR XML query result is returned as type `nvarchar(max)`.</span></span>  
  
### <a name="using-for-xml-query-results-in-insert-update-and-delete-transact-sql-dml"></a><span data-ttu-id="6a40f-133">Utilizar resultados de consultas FOR XML en INSERT, UPDATE y DELETE (DML de Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6a40f-133">Using FOR XML query results in INSERT, UPDATE, and DELETE (Transact-SQL DML)</span></span>  
 <span data-ttu-id="6a40f-134">En el ejemplo siguiente se muestra el modo en el que se pueden utilizar las consultas FOR XML en instrucciones del lenguaje de manipulación de datos (DML).</span><span class="sxs-lookup"><span data-stu-id="6a40f-134">The following example demonstrates how FOR XML queries can be used in Data Manipulation Language (DML) statements.</span></span> <span data-ttu-id="6a40f-135">En este ejemplo, `FOR XML` devuelve una instancia del tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6a40f-135">In the example, the `FOR XML` returns an instance of `xml` type.</span></span> <span data-ttu-id="6a40f-136">La instrucción `INSERT` inserta esta instancia de tipo XML en una tabla.</span><span class="sxs-lookup"><span data-stu-id="6a40f-136">The `INSERT` statement inserts this XML into a table.</span></span>  
  
```  
CREATE TABLE T1(intCol int, XmlCol xml);  
GO  
INSERT INTO T1   
VALUES(1, '<Root><ProductDescription ProductModelID="1" /></Root>');  
GO  
  
CREATE TABLE T2(XmlCol xml)  
GO  
INSERT INTO T2(XmlCol)   
SELECT (SELECT XmlCol.query('/Root')   
        FROM T1   
        FOR XML AUTO,TYPE);   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a40f-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a40f-137">See Also</span></span>  
 [<span data-ttu-id="6a40f-138">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6a40f-138">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
