---
title: Creación de variables y columnas del tipo de datos XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- xml data type [SQL Server], columns
ms.assetid: 8994ab6e-5519-4ba2-97a1-fac8af6f72db
author: rothja
ms.author: jroth
ms.openlocfilehash: 08b79888eb47634deaccc910b2ea3c93800b7c78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748687"
---
# <a name="create-xml-data-type-variables-and-columns"></a><span data-ttu-id="2a1f0-102">Crear variables y columnas del tipo de datos XML</span><span class="sxs-lookup"><span data-stu-id="2a1f0-102">Create XML Data Type Variables and Columns</span></span>
  <span data-ttu-id="2a1f0-103">El tipo de datos `xml` es un tipo de datos integrado de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y es similar a otros tipos integrados como `int` y `varchar`.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-103">The `xml` data type is a built-in data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is somewhat similar to other built-in types such as `int` and `varchar`.</span></span> <span data-ttu-id="2a1f0-104">Como con otros tipos integrados, puede usar el `xml` tipo de datos como un tipo de columna al crear una tabla como un tipo de variable, un tipo de parámetro, un tipo de valor devuelto de función o en [CAST y Convert](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2a1f0-104">As with other built-in types, you can use the `xml` data type as a column type when you create a table as a variable type, a parameter type, a function-return type, or in [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
## <a name="creating-columns-and-variables"></a><span data-ttu-id="2a1f0-105">Crear columnas y variables</span><span class="sxs-lookup"><span data-stu-id="2a1f0-105">Creating Columns and Variables</span></span>  
 <span data-ttu-id="2a1f0-106">Para crear una columna de tipo `xml` como parte de una tabla, utilice una instrucción `CREATE TABLE` , como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-106">To create an `xml` type column as part of a table, use a `CREATE TABLE` statement, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T1(Col1 int primary key, Col2 xml)   
```  
  
 <span data-ttu-id="2a1f0-107">Puede utilizar una instrucción `DECLARE statement` para crear una variable de tipo `xml` , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-107">You can use a `DECLARE statement` to create a variable of `xml` type, as the following example shows.</span></span>  
  
```  
DECLARE @x xml   
```  
  
 <span data-ttu-id="2a1f0-108">Para crear una variable de tipo `xml` , especifique una colección de esquemas XML, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-108">Create a typed `xml` variable by specifying an XML schema collection, as shown in the following example.</span></span>  
  
```  
DECLARE @x xml (Sales.StoreSurveySchemaCollection)  
```  
  
 <span data-ttu-id="2a1f0-109">Para pasar un parámetro de tipo `xml` a un procedimiento almacenado, utilice una instrucción `CREATE PROCEDURE` , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-109">To pass an `xml` type parameter to a stored procedure, use a `CREATE PROCEDURE` statement, as shown in the following example.</span></span>  
  
```  
CREATE PROCEDURE SampleProc(@XmlDoc xml) AS ...   
```  
  
 <span data-ttu-id="2a1f0-110">Puede utilizar XQuery para consultar instancias XML almacenadas en columnas, parámetros o variables.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-110">You can use XQuery to query XML instances stored in columns, parameters, or variables.</span></span> <span data-ttu-id="2a1f0-111">También puede utilizar el Lenguaje de manipulación de datos XML (XML DML) para aplicar actualizaciones a las instancias XML.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-111">You can also use the XML Data Manipulation Language (XML DML) to apply updates to the XML instances.</span></span> <span data-ttu-id="2a1f0-112">Puesto que el estándar XQuery no definió el DML de XQuery cuando se desarrolló, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] incluye las extensiones del [Lenguaje de manipulación de datos XML (XML DML)](/sql/t-sql/xml/xml-data-modification-language-xml-dml) en XQuery.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-112">Because the XQuery standard did not define XQuery DML at the time of development, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduces [XML Data Modification Language](/sql/t-sql/xml/xml-data-modification-language-xml-dml) extensions to XQuery.</span></span> <span data-ttu-id="2a1f0-113">Estas extensiones permiten realizar operaciones de inserción, actualización y eliminación.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-113">These extensions allow you to perform insert, update, and delete operations.</span></span>  
  
## <a name="assigning-defaults"></a><span data-ttu-id="2a1f0-114">Asignar valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="2a1f0-114">Assigning Defaults</span></span>  
 <span data-ttu-id="2a1f0-115">En una tabla, puede asignar una instancia XML predeterminada a una columna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-115">In a table, you can assign a default XML instance to a column of `xml` type.</span></span> <span data-ttu-id="2a1f0-116">Puede proporcionar el XML predeterminado de una de estas dos maneras: con una constante XML o con una conversión explícita al tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-116">You can provide the default XML in one of two ways: by using an XML constant, or by using an explicit cast to the `xml` type.</span></span>  
  
 <span data-ttu-id="2a1f0-117">Para proporcionar el XML predeterminado como una constante XML, utilice la sintaxis como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-117">To provide the default XML as an XML constant, use syntax as shown in the following example.</span></span> <span data-ttu-id="2a1f0-118">Observe que la cadena se convierte implícitamente al tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-118">Note that the string is implicitly CAST to `xml` type.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml default N'<element1/><element2/>')  
```  
  
 <span data-ttu-id="2a1f0-119">Para proporcionar el XML predeterminado mediante una operación de conversión ( `CAST` ) explícita a `xml`, utilice la sintaxis como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-119">To provide the default XML as an explicit `CAST` to `xml`, use syntax as shown in the following example.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml   
                  default CAST(N'<element1/><element2/>' AS xml))  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2a1f0-120">también admite restricciones NULL y NOT NULL en columnas de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-120">also supports NULL and NOT NULL constraints on columns of `xml` type.</span></span> <span data-ttu-id="2a1f0-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-121">For example:</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml NOT NULL)  
```  
  
## <a name="specifying-constraints"></a><span data-ttu-id="2a1f0-122">Especificar restricciones</span><span class="sxs-lookup"><span data-stu-id="2a1f0-122">Specifying Constraints</span></span>  
 <span data-ttu-id="2a1f0-123">Al crear columnas de tipo `xml`, puede definir restricciones de nivel de columna o de nivel de tabla.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-123">When you create columns of `xml` type, you can define column-level or table-level constraints.</span></span> <span data-ttu-id="2a1f0-124">Las restricciones se emplean en estas situaciones:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-124">Use constraints in the following situations:</span></span>  
  
-   <span data-ttu-id="2a1f0-125">Sus reglas de negocios no se pueden expresar en esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-125">Your business rules cannot be expressed in XML schemas.</span></span> <span data-ttu-id="2a1f0-126">Por ejemplo, la dirección de entrega de una floristería debe estar a menos de 75 kilómetros de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-126">For example, the delivery address of a flower shop must be within 50 miles of its business location.</span></span> <span data-ttu-id="2a1f0-127">Esto se puede escribir como una restricción en la columna XML.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-127">This can be written as a constraint on the XML column.</span></span> <span data-ttu-id="2a1f0-128">La restricción puede afectar a métodos de tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-128">The constraint may involve `xml` data type methods.</span></span>  
  
-   <span data-ttu-id="2a1f0-129">La restricción afecta a otras columnas XML o no XML de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-129">Your constraint involves other XML or non-XML columns in the table.</span></span> <span data-ttu-id="2a1f0-130">Un ejemplo puede ser obligar a que el Id. de un cliente (`/Customer/@CustId`) existente en una instancia XML coincida con el valor de una columna relacional CustomerID.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-130">An example is the enforcement of the ID of a Customer (`/Customer/@CustId`) found in an XML instance to match the value in a relational CustomerID column.</span></span>  
  
 <span data-ttu-id="2a1f0-131">Puede especificar restricciones para columnas de tipo de datos `xml` con o sin tipo.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-131">You can specify constraints for typed or untyped `xml` data type columns.</span></span> <span data-ttu-id="2a1f0-132">Sin embargo, no puede usar los [métodos de tipo de datos XML](/sql/t-sql/xml/xml-data-type-methods) al especificar restricciones.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-132">However, you cannot use the [XML data type methods](/sql/t-sql/xml/xml-data-type-methods) when you specify constraints.</span></span> <span data-ttu-id="2a1f0-133">También debe tener en cuenta que el tipo de datos `xml` no admite las restricciones de columna y de tabla siguientes:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-133">Also, note that the `xml` data type does not support the following column and table constraints:</span></span>  
  
-   <span data-ttu-id="2a1f0-134">PRIMARY KEY / FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="2a1f0-134">PRIMARY KEY/ FOREIGN KEY</span></span>  
  
-   <span data-ttu-id="2a1f0-135">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2a1f0-135">UNIQUE</span></span>  
  
-   <span data-ttu-id="2a1f0-136">COLLATE</span><span class="sxs-lookup"><span data-stu-id="2a1f0-136">COLLATE</span></span>  
  
     <span data-ttu-id="2a1f0-137">XML proporciona su propia codificación.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-137">XML provides its own encoding.</span></span> <span data-ttu-id="2a1f0-138">Las intercalaciones solo se aplican a los tipos de cadena.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-138">Collations apply to string types only.</span></span> <span data-ttu-id="2a1f0-139">El tipo de datos `xml` no es un tipo de cadena.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-139">The `xml` data type is not a string type.</span></span> <span data-ttu-id="2a1f0-140">No obstante, tiene una representación de cadena y permite la conversión a tipos de datos de cadena y desde tipos de datos de cadena.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-140">However, it does have string representation and allows casting to and from string data types.</span></span>  
  
-   <span data-ttu-id="2a1f0-141">RULE</span><span class="sxs-lookup"><span data-stu-id="2a1f0-141">RULE</span></span>  
  
 <span data-ttu-id="2a1f0-142">Una alternativa al uso de restricciones consiste en crear una función de contenedor definida por el usuario para ajustar el método de tipo de datos `xml` y especificar una función definida por el usuario en la restricción CHECK, como se muestra a continuación.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-142">An alternative to using constraints is to create a wrapper, user-defined function to wrap the `xml` data type method and specify user-defined function in the check constraint as shown in the following example.</span></span>  
  
 <span data-ttu-id="2a1f0-143">En el siguiente ejemplo, la restricción de `Col2` especifica que cada instancia XML almacenada en esta columna debe tener un elemento `<ProductDescription>` con un atributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="2a1f0-143">In the following example, the constraint on `Col2` specifies that each XML instance stored in this column must have a `<ProductDescription>` element that contains a `ProductID` attribute.</span></span> <span data-ttu-id="2a1f0-144">Esta restricción se exige mediante la siguiente función definida por el usuario:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-144">This constraint is enforced by this user-defined function:</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns bit  
AS BEGIN   
RETURN @var.exist('/ProductDescription/@ProductID')  
END  
GO  
```  
  
 <span data-ttu-id="2a1f0-145">Observe que el método `exist()` del tipo de datos `xml` devuelve `1` si el elemento `<ProductDescription>` de la instancia contiene el atributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="2a1f0-145">Note that the `exist()` method of the `xml` data type returns `1` if the `<ProductDescription>` element in the instance contains the `ProductID` attribute.</span></span> <span data-ttu-id="2a1f0-146">En caso contrario, devuelve `0`.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-146">Otherwise, it returns `0`.</span></span>  
  
 <span data-ttu-id="2a1f0-147">En este momento, puede crear una tabla con una restricción de columna del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-147">Now, you can create a table with a column-level constraint as follows:</span></span>  
  
```  
CREATE TABLE T (  
    Col1 int primary key,   
    Col2 xml check(dbo.my_udf(Col2)=1))  
GO  
```  
  
 <span data-ttu-id="2a1f0-148">La inserción siguiente se realiza correctamente:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-148">The following insert succeeds:</span></span>  
  
```  
INSERT INTO T values(1,'<ProductDescription ProductID="1" />')  
```  
  
 <span data-ttu-id="2a1f0-149">La inserción siguiente no se realiza correctamente a causa de la restricción:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-149">Because of the constraint, the following insert fails:</span></span>  
  
```  
INSERT INTO T values(1,'<Product />')  
```  
  
## <a name="same-or-different-table"></a><span data-ttu-id="2a1f0-150">La misma tabla o una tabla diferente</span><span class="sxs-lookup"><span data-stu-id="2a1f0-150">Same or Different Table</span></span>  
 <span data-ttu-id="2a1f0-151">Una `xml` columna de tipo de datos se puede crear en una tabla que contenga otras columnas relacionales o en una tabla independiente con una relación de clave externa con una tabla principal.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-151">An `xml` data type column can be created in a table that contains other relational columns, or in a separate table with a foreign key relationship to a main table.</span></span>  
  
 <span data-ttu-id="2a1f0-152">Cree una `xml` columna de tipo de datos en la misma tabla cuando se cumpla una de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-152">Create an `xml` data type column in the same table when one of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="2a1f0-153">La aplicación efectúa una recuperación de datos en la columna XML y no requiere un índice XML en la columna XML.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-153">Your application performs data retrieval on the XML column and does not require an XML index on the XML column.</span></span>  
  
-   <span data-ttu-id="2a1f0-154">Desea generar un índice XML en la columna de tipo de datos `xml` y la clave principal de la tabla principal es la misma que su clave de agrupación en clústeres.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-154">You want to build an XML index on the `xml` data type column and the primary key of the main table is the same as its clustering key.</span></span> <span data-ttu-id="2a1f0-155">Para obtener más información, consulte [Índices XML &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2a1f0-155">For more information, see [XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span></span>  
  
 <span data-ttu-id="2a1f0-156">Puede crear la columna de tipo de datos `xml` en otra tabla si se cumplen las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="2a1f0-156">Create the `xml` data type column in a separate table if the following conditions are true:</span></span>  
  
-   <span data-ttu-id="2a1f0-157">Desea generar un índice XML en la columna de tipo de datos `xml`, pero la clave principal de la tabla principal es distinta de su clave de agrupación en clústeres, la tabla principal no tiene una clave principal, o la tabla principal es un montón (sin clave de agrupación en clústeres).</span><span class="sxs-lookup"><span data-stu-id="2a1f0-157">You want to build an XML index on the `xml` data type column, but the primary key of the main table is different from its clustering key, or the main table does not have a primary key, or the main table is a heap (no clustering key).</span></span> <span data-ttu-id="2a1f0-158">Esto puede ser cierto si la tabla principal ya existe.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-158">This may be true if the main table already exists.</span></span>  
  
-   <span data-ttu-id="2a1f0-159">No desea que se ralenticen los recorridos de las tablas por la presencia de la columna XML en la tabla.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-159">You do not want table scans to slow down because of the presence of the XML column in the table.</span></span> <span data-ttu-id="2a1f0-160">Ésta usa espacio independientemente de si está o no almacenada de manera consecutiva.</span><span class="sxs-lookup"><span data-stu-id="2a1f0-160">This uses space whether it is stored in-row or out-of-row.</span></span>  
  
  
