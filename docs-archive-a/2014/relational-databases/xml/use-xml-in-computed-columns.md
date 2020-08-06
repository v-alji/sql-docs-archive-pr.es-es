---
title: Usar XML en columnas calculadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- computed columns, XML
- XML [SQL Server], computed columns
ms.assetid: 1313b889-69b4-4018-9868-0496dd83bf44
author: rothja
ms.author: jroth
ms.openlocfilehash: 33a7549823dc3e4a23cecfa97d7345a6421cb1b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744001"
---
# <a name="use-xml-in-computed-columns"></a><span data-ttu-id="f6c81-102">Usar XML en columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="f6c81-102">Use XML in Computed Columns</span></span>
  <span data-ttu-id="f6c81-103">Pueden aparecer instancias XML como origen de una columna calculada o como un tipo de columna calculada.</span><span class="sxs-lookup"><span data-stu-id="f6c81-103">XML instances can appear as a source for a computed column, or as a type of computed column.</span></span> <span data-ttu-id="f6c81-104">Los ejemplos de este tema muestran cómo usar XML con columnas calculadas.</span><span class="sxs-lookup"><span data-stu-id="f6c81-104">The examples in this topic show how to use XML with computed columns.</span></span>  
  
## <a name="creating-computed-columns-from-xml-columns"></a><span data-ttu-id="f6c81-105">Crear columnas calculadas a partir de columnas XML</span><span class="sxs-lookup"><span data-stu-id="f6c81-105">Creating Computed Columns from XML Columns</span></span>  
 <span data-ttu-id="f6c81-106">En la siguiente instrucción `CREATE TABLE` , una columna de tipo `xml` (`col2`) se calcula a partir de `col1`:</span><span class="sxs-lookup"><span data-stu-id="f6c81-106">In the following `CREATE TABLE` statement, an `xml` type column (`col2`) is computed from `col1`:</span></span>  
  
```  
CREATE TABLE T(col1 varchar(max), col2 AS CAST(col1 AS xml) )    
```  
  
 <span data-ttu-id="f6c81-107">El tipo de datos `xml` también puede aparecer como origen en la creación de una columna calculada, tal como se muestra en la siguiente instrucción `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="f6c81-107">The `xml` data type can also appear as a source in creating a computed column, as shown in the following `CREATE TABLE` statement:</span></span>  
  
```  
CREATE TABLE T (col1 xml, col2 as cast(col1 as varchar(1000) ))   
```  
  
 <span data-ttu-id="f6c81-108">Puede crear una columna calculada extrayendo un valor de una columna de tipo `xml` , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6c81-108">You can create a computed column by extracting a value from an `xml` type column as shown in the following example.</span></span> <span data-ttu-id="f6c81-109">Puesto que los métodos de tipo de datos `xml` no se pueden utilizar directamente en la creación de columnas calculadas, en el ejemplo se define en primer lugar una función (`my_udf`) que devuelve un valor de una instancia XML.</span><span class="sxs-lookup"><span data-stu-id="f6c81-109">Because the `xml` data type methods cannot be used directly in creating computed columns, the example first defines a function (`my_udf`) that returns a value from an XML instance.</span></span> <span data-ttu-id="f6c81-110">La función ajusta el método `value()` del tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="f6c81-110">The function wraps the `value()` method of the `xml` type.</span></span> <span data-ttu-id="f6c81-111">A continuación se especifica el nombre de la función en la instrucción `CREATE TABLE` para la columna calculada.</span><span class="sxs-lookup"><span data-stu-id="f6c81-111">The function name is then specified in the `CREATE TABLE` statement for the computed column.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns int  
AS BEGIN   
RETURN @var.value('(/ProductDescription/@ProductModelID)[1]' , 'int')  
END  
GO  
-- Use the function in CREATE TABLE.  
CREATE TABLE T (col1 xml, col2 as dbo.my_udf(col1) )  
GO  
-- Try adding a row.   
INSERT INTO T values('<ProductDescription ProductModelID="1" />')  
GO  
-- Verify results.  
SELECT col2, col1  
FROM T  
  
```  
  
 <span data-ttu-id="f6c81-112">Al igual que en el ejemplo anterior, en el siguiente se define una función para devolver una instancia de tipo `xml` para una columna calculada.</span><span class="sxs-lookup"><span data-stu-id="f6c81-112">As in the previous example, the following example defines a function to return an `xml` type instance for a computed column.</span></span> <span data-ttu-id="f6c81-113">En la función, el método `query()` del tipo de datos `xml` recupera un valor de un parámetro de tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="f6c81-113">Inside the function, the `query()` method of the `xml` data type retrieves a value from an `xml` type parameter.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml)   
  RETURNS xml AS   
BEGIN   
   RETURN @var.query('ProductDescription/Features')  
END  
```  
  
 <span data-ttu-id="f6c81-114">En la siguiente instrucción `CREATE TABLE` , `Col2` es una columna calculada que usa los datos XML (elemento`<Features>` ) devueltos por la función:</span><span class="sxs-lookup"><span data-stu-id="f6c81-114">In the following `CREATE TABLE` statement, `Col2` is a computed column that uses the XML data (`<Features>` element) that is returned by the function:</span></span>  
  
```  
CREATE TABLE T (Col1 xml, Col2 as dbo.my_udf(Col1) )  
-- Insert a row in table T.  
INSERT INTO T VALUES('  
<ProductDescription ProductModelID="1" >  
  <Features>  
    <Feature1>description</Feature1>  
    <Feature2>description</Feature2>  
  </Features>  
</ProductDescription>')  
-- Verify the results.  
SELECT *  
FROM T  
```  
  
### <a name="in-this-section"></a><span data-ttu-id="f6c81-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f6c81-115">In This Section</span></span>  
  
|<span data-ttu-id="f6c81-116">Tema</span><span class="sxs-lookup"><span data-stu-id="f6c81-116">Topic</span></span>|<span data-ttu-id="f6c81-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6c81-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="f6c81-118">Promover los valores XML usados con frecuencia con columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="f6c81-118">Promote Frequently Used XML Values with Computed Columns</span></span>](promote-frequently-used-xml-values-with-computed-columns.md)|<span data-ttu-id="f6c81-119">Describe cómo usar la promoción de propiedades con columnas calculadas y tablas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="f6c81-119">Describes how to use property promotion with computed columns and property tables.</span></span>|  
  
  
