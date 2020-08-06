---
title: Comparar XML con tipo y XML sin tipo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- parameters [XML in SQL Server]
- facets [XML in SQL Server]
- xml data type [SQL Server], columns
- untyped XML
- xml data type [SQL Server], typed xml
- XML [SQL Server], typed
- variables [XML in SQL Server], creating
- xml data type [SQL Server], untyped xml
- columns [XML in SQL Server], creating
- typed XML
- document mode processing [SQL Server]
- XML [SQL Server], untyped
- xml data type [SQL Server], parameters
ms.assetid: 4bc50af9-2f7d-49df-bb01-854d080c72c7
author: rothja
ms.author: jroth
ms.openlocfilehash: fae9ca930bd8741a1332b61c8272f2133590483e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745086"
---
# <a name="compare-typed-xml-to-untyped-xml"></a><span data-ttu-id="1d12d-102">Comparar XML con tipo y XML sin tipo</span><span class="sxs-lookup"><span data-stu-id="1d12d-102">Compare Typed XML to Untyped XML</span></span>
  <span data-ttu-id="1d12d-103">Se pueden crear variables, parámetros y columnas del tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="1d12d-103">You can create variables, parameters, and columns of the `xml` type.</span></span> <span data-ttu-id="1d12d-104">Opcionalmente, se puede asociar una colección de esquemas XML a una variable, a un parámetro o a una columna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="1d12d-104">You can optionally associate a collection of XML schemas with a variable, parameter, or column of `xml` type.</span></span> <span data-ttu-id="1d12d-105">En este caso, `xml` se llama a la instancia de tipo de datos *con tipo*.</span><span class="sxs-lookup"><span data-stu-id="1d12d-105">In this case, the `xml` data type instance is called *typed*.</span></span> <span data-ttu-id="1d12d-106">En los demás casos, se dice que la instancia XML es una instancia *sin tipo*.</span><span class="sxs-lookup"><span data-stu-id="1d12d-106">Otherwise, the XML instance is called *untyped*.</span></span>  
  
## <a name="well-formed-xml-and-the-xml-data-type"></a><span data-ttu-id="1d12d-107">XML correcto y tipo de datos XML</span><span class="sxs-lookup"><span data-stu-id="1d12d-107">Well-formed XML and the xml Data Type</span></span>  
 <span data-ttu-id="1d12d-108">El tipo de datos `xml` implementa el tipo de datos `xml` del estándar ISO.</span><span class="sxs-lookup"><span data-stu-id="1d12d-108">The `xml` data type implements the ISO standard `xml` data type.</span></span> <span data-ttu-id="1d12d-109">Por lo tanto, puede almacenar documentos XML versión 1.0 correctos, así como los denominados fragmentos de contenido XML con nodos de texto y un número arbitrario de elementos de nivel superior en una columna XML sin tipo.</span><span class="sxs-lookup"><span data-stu-id="1d12d-109">Therefore, it can store well-formed XML version 1.0 documents and also so-called XML content fragments with text nodes and an arbitrary number of top-level elements in an untyped XML column.</span></span> <span data-ttu-id="1d12d-110">El sistema comprueba que todos los datos tienen un formato correcto, no requiere que la columna esté enlazada a esquemas XML y rechaza los datos que no tienen un formato correcto en sentido amplio.</span><span class="sxs-lookup"><span data-stu-id="1d12d-110">The system checks that the data is well-formed, does not require the column to be bound to XML schemas, and rejects data that is not well-formed in the extended sense.</span></span> <span data-ttu-id="1d12d-111">Esto también se cumple para parámetros y variables XML sin tipo.</span><span class="sxs-lookup"><span data-stu-id="1d12d-111">This is true also of untyped XML variables and parameters.</span></span>  
  
## <a name="xml-schemas"></a><span data-ttu-id="1d12d-112">Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="1d12d-112">XML Schemas</span></span>  
 <span data-ttu-id="1d12d-113">Un esquema XML proporciona lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d12d-113">An XML schema provides the following:</span></span>  
  
-   <span data-ttu-id="1d12d-114">**Restricciones de validación.**</span><span class="sxs-lookup"><span data-stu-id="1d12d-114">**Validation constraints.**</span></span> <span data-ttu-id="1d12d-115">Siempre que se asigna o modifica una instancia XML con tipo, SQL Server valida la instancia.</span><span class="sxs-lookup"><span data-stu-id="1d12d-115">Whenever a typed xml instance is assigned to or modified, SQL Server validates the instance.</span></span>  
  
-   <span data-ttu-id="1d12d-116">**Información sobre el tipo de datos.**</span><span class="sxs-lookup"><span data-stu-id="1d12d-116">**Data type information.**</span></span> <span data-ttu-id="1d12d-117">Los esquemas proporcionan información sobre los tipos de atributos y elementos de la instancia de tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="1d12d-117">Schemas provide information about the types of attributes and elements in the `xml` data type instance.</span></span> <span data-ttu-id="1d12d-118">La información de tipo proporciona una semántica operacional más precisa para los valores contenidos en la instancia que es posible con `xml` sin tipo.</span><span class="sxs-lookup"><span data-stu-id="1d12d-118">The type information provides more precise operational semantics to the values contained in the instance than is possible with untyped `xml`.</span></span> <span data-ttu-id="1d12d-119">Por ejemplo, se pueden realizar operaciones aritméticas con decimales en un valor decimal, pero no en un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="1d12d-119">For example, decimal arithmetic operations can be performed on a decimal value, but not on a string value.</span></span> <span data-ttu-id="1d12d-120">Por este motivo, el almacenamiento de XML con tipo puede ser mucho más compacto que el de XML sin tipo.</span><span class="sxs-lookup"><span data-stu-id="1d12d-120">Because of this, typed XML storage can be made significantly more compact than untyped XML.</span></span>  
  
## <a name="choosing-typed-or-untyped-xml"></a><span data-ttu-id="1d12d-121">Elegir XML con tipo o sin tipo</span><span class="sxs-lookup"><span data-stu-id="1d12d-121">Choosing Typed or Untyped XML</span></span>  
 <span data-ttu-id="1d12d-122">El tipo de datos `xml` sin tipo se emplea en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="1d12d-122">Use untyped `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="1d12d-123">No tiene un esquema para los datos XML.</span><span class="sxs-lookup"><span data-stu-id="1d12d-123">You do not have a schema for your XML data.</span></span>  
  
-   <span data-ttu-id="1d12d-124">Tiene esquemas pero no desea que el servidor valide los datos.</span><span class="sxs-lookup"><span data-stu-id="1d12d-124">You have schemas, but you do not want the server to validate the data.</span></span> <span data-ttu-id="1d12d-125">Esto a veces ocurre cuando una aplicación realiza la validación del lado cliente antes de almacenar los datos en el servidor, almacena temporalmente datos XML que no son válidos según el esquema, o usa componentes del esquema que no son compatibles con el servidor.</span><span class="sxs-lookup"><span data-stu-id="1d12d-125">This is sometimes the case when an application performs client-side validation before storing the data at the server, or temporarily stores XML data that is invalid according to the schema, or uses schema components that are not supported at the server.</span></span>  
  
 <span data-ttu-id="1d12d-126">Utilice `xml` el tipo de datos con tipo en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="1d12d-126">Use typed `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="1d12d-127">Tiene esquemas para los datos XML y desea que el servidor valide estos datos según los esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="1d12d-127">You have schemas for your XML data and you want the server to validate your XML data according to the XML schemas.</span></span>  
  
-   <span data-ttu-id="1d12d-128">Desea aprovechar las optimizaciones del almacenamiento y de las consultas en función de la información del tipo.</span><span class="sxs-lookup"><span data-stu-id="1d12d-128">You want to take advantage of storage and query optimizations based on type information.</span></span>  
  
-   <span data-ttu-id="1d12d-129">Desea aprovechar mejor la información del tipo durante la compilación de las consultas.</span><span class="sxs-lookup"><span data-stu-id="1d12d-129">You want to take better advantage of type information during compilation of your queries.</span></span>  
  
 <span data-ttu-id="1d12d-130">Columnas, parámetros y variables XML con tipo pueden almacenar documentos o contenido XML.</span><span class="sxs-lookup"><span data-stu-id="1d12d-130">Typed XML columns, parameters, and variables can store XML documents or content.</span></span> <span data-ttu-id="1d12d-131">No obstante, hay que especificar con una marca si se va a almacenar un documento o contenido en el momento de la declaración.</span><span class="sxs-lookup"><span data-stu-id="1d12d-131">However, you have to specify with a flag whether you are storing a document or content at the time of declaration.</span></span> <span data-ttu-id="1d12d-132">Además, hay que proporcionar la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="1d12d-132">Additionally, you have to provide the collection of XML schemas.</span></span> <span data-ttu-id="1d12d-133">Especifique DOCUMENT si cada instancia XML tiene exactamente un elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="1d12d-133">Specify DOCUMENT if each XML instance has exactly one top-level element.</span></span> <span data-ttu-id="1d12d-134">En caso contrario, use CONTENT.</span><span class="sxs-lookup"><span data-stu-id="1d12d-134">Otherwise, use CONTENT.</span></span> <span data-ttu-id="1d12d-135">El compilador de consultas usa la marca DOCUMENT en comprobaciones de tipo durante la compilación de consultas para inferir elementos singleton de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="1d12d-135">The query compiler uses the DOCUMENT flag in type checks during query compilation to infer singleton top-level elements.</span></span>  
  
## <a name="creating-typed-xml"></a><span data-ttu-id="1d12d-136">Crear XML con tipo</span><span class="sxs-lookup"><span data-stu-id="1d12d-136">Creating Typed XML</span></span>  
 <span data-ttu-id="1d12d-137">Para poder crear `xml` variables, parámetros o columnas con tipo, primero debe registrar la colección de esquemas XML mediante [Create XML schema Collection &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1d12d-137">Before you can create typed `xml` variables, parameters, or columns, you must first register the XML schema collection by using [CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span> <span data-ttu-id="1d12d-138">Después, se puede asociar la colección de esquemas XML a variables, parámetros o columnas del tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="1d12d-138">You can then associate the XML schema collection with variables, parameters, or columns of the `xml` data type.</span></span>  
  
 <span data-ttu-id="1d12d-139">En los ejemplos siguientes se usa una convención de nomenclatura de dos partes para especificar el nombre de la recopilación de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="1d12d-139">In the following examples, a two-part naming convention is used for specifying the XML schema collection name.</span></span> <span data-ttu-id="1d12d-140">La primera parte corresponde al nombre de esquema y la segunda al nombre de la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="1d12d-140">The first part is the schema name, and the second part is the XML schema collection name.</span></span>  
  
### <a name="example-associating-a-schema-collection-with-an-xml-type-variable"></a><span data-ttu-id="1d12d-141">Ejemplo: Asociación de una colección de esquemas con una variable de tipo XML</span><span class="sxs-lookup"><span data-stu-id="1d12d-141">Example: Associating a Schema Collection with an xml Type Variable</span></span>  
 <span data-ttu-id="1d12d-142">En el ejemplo siguiente se crea una `xml` variable de tipo y se le asocia una colección de esquemas.</span><span class="sxs-lookup"><span data-stu-id="1d12d-142">The following example creates an`xml` type variable and associates a schema collection with it.</span></span> <span data-ttu-id="1d12d-143">La colección de esquemas especificada en el ejemplo ya se ha importado a la base de datos **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="1d12d-143">The schema collection specified in the example is already imported in the **AdventureWorks** database.</span></span>  
  
```  
DECLARE @x xml (Production.ProductDescriptionSchemaCollection);   
```  
  
### <a name="example-specifying-a-schema-for-an-xml-type-column"></a><span data-ttu-id="1d12d-144">Ejemplo: Especificación de un esquema para una columna de tipo XML</span><span class="sxs-lookup"><span data-stu-id="1d12d-144">Example: Specifying a Schema for an xml Type Column</span></span>  
 <span data-ttu-id="1d12d-145">En el ejemplo siguiente se crea una tabla con una columna de tipo `xml` y se especifica un esquema para la columna:</span><span class="sxs-lookup"><span data-stu-id="1d12d-145">The following example creates a table with an `xml` type column and specifies a schema for the column:</span></span>  
  
```  
CREATE TABLE T1(  
 Col1 int,   
 Col2 xml (Production.ProductDescriptionSchemaCollection)) ;  
```  
  
### <a name="example-passing-an-xml-type-parameter-to-a-stored-procedure"></a><span data-ttu-id="1d12d-146">Ejemplo: Cómo pasar un parámetro de tipo XML a un procedimiento almacenado</span><span class="sxs-lookup"><span data-stu-id="1d12d-146">Example: Passing an xml Type Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="1d12d-147">En el ejemplo siguiente se pasa un parámetro de tipo `xml` a un procedimiento almacenado y se especifica un esquema para la variable:</span><span class="sxs-lookup"><span data-stu-id="1d12d-147">The following example passes an `xml` type parameter to a stored procedure and specifies a schema for the variable:</span></span>  
  
```  
CREATE PROCEDURE SampleProc   
  @ProdDescription xml (Production.ProductDescriptionSchemaCollection)   
AS   
...  
```  
  
 <span data-ttu-id="1d12d-148">Tenga en cuenta lo siguiente sobre la colección de esquemas XML:</span><span class="sxs-lookup"><span data-stu-id="1d12d-148">Note the following about the XML schema collection:</span></span>  
  
-   <span data-ttu-id="1d12d-149">Una colección de esquemas XML solo está disponible en la base de datos en la que se ha registrado mediante [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1d12d-149">An XML schema collection is available only in the database in which it was registered by using [Creating an XML Schema Collection](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span>  
  
-   <span data-ttu-id="1d12d-150">Si se realiza la conversión de una cadena a un tipo de datos `xml` con tipo, el análisis también realiza la validación y la conversión de tipos, de acuerdo con los espacios de nombres de los esquemas XML de la colección especificada.</span><span class="sxs-lookup"><span data-stu-id="1d12d-150">If you cast from a string to a typed `xml` data type, the parsing also performs validation and typing, based on the XML schema namespaces in the collection specified.</span></span>  
  
-   <span data-ttu-id="1d12d-151">Es posible convertir un tipo de datos `xml` con tipo en un tipo de datos `xml` sin tipo, y viceversa.</span><span class="sxs-lookup"><span data-stu-id="1d12d-151">You can cast from a typed `xml` data type to an untyped `xml` data type, and vice versa.</span></span>  
  
 <span data-ttu-id="1d12d-152">Para obtener más información sobre otras maneras de generar XML en SQL Server, vea [Crear instancias de datos XML](create-instances-of-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="1d12d-152">For more information about other ways to generate XML in SQL Server, see [Create Instances of XML Data](create-instances-of-xml-data.md).</span></span> <span data-ttu-id="1d12d-153">Una vez generado el XML, se puede asignar a una variable del tipo de datos `xml` o se puede almacenar en columnas de tipo `xml` para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="1d12d-153">After XML is generated, it can be assigned either to an `xml` data type variable or stored in `xml` type columns for additional processing.</span></span>  
  
 <span data-ttu-id="1d12d-154">En la jerarquía de tipos de datos, el tipo de datos `xml` aparece por debajo de `sql_variant` y los tipos definidos por el usuario, pero por encima de los tipos integrados.</span><span class="sxs-lookup"><span data-stu-id="1d12d-154">In the data type hierarchy, the `xml` data type appears below `sql_variant` and user-defined types, but above any of the built-in types.</span></span>  
  
### <a name="example-specifying-facets-to-constrain-a-typed-xml-column"></a><span data-ttu-id="1d12d-155">Ejemplo: Especificación de facetas para restringir una columna XML con tipo</span><span class="sxs-lookup"><span data-stu-id="1d12d-155">Example: Specifying Facets to Constrain a Typed xml Column</span></span>  
 <span data-ttu-id="1d12d-156">En las columnas `xml` con tipo se puede restringir la columna para permitir que solo se almacene en ella un único elemento de nivel superior para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="1d12d-156">For typed `xml` columns, you can constrain the column to allow only single, top-level elements for each instance stored in it.</span></span> <span data-ttu-id="1d12d-157">Para ello, se especifica la faceta opcional `DOCUMENT` cuando se crea una tabla, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d12d-157">You do this by specifying the optional `DOCUMENT` facet when a table is created, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml   
   (DOCUMENT Production.ProductDescriptionSchemaCollection));  
GO  
DROP TABLE T;  
GO  
```  
  
 <span data-ttu-id="1d12d-158">De manera predeterminada, las instancias se almacenan en la columna `xml` con tipo como contenido XML y no como documentos XML.</span><span class="sxs-lookup"><span data-stu-id="1d12d-158">By default, instances stored in the typed `xml` column are stored as XML content and not as XML documents.</span></span> <span data-ttu-id="1d12d-159">Esto permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d12d-159">This allows for the following:</span></span>  
  
-   <span data-ttu-id="1d12d-160">Cero o varios elementos de nivel superior</span><span class="sxs-lookup"><span data-stu-id="1d12d-160">Zero or many top-level elements</span></span>  
  
-   <span data-ttu-id="1d12d-161">Nodos de texto en elementos de nivel superior</span><span class="sxs-lookup"><span data-stu-id="1d12d-161">Text nodes in top-level elements</span></span>  
  
 <span data-ttu-id="1d12d-162">Este comportamiento también se puede especificar explícitamente, agregando la faceta `CONTENT` , tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d12d-162">You can also explicitly specify this behavior by adding `CONTENT` facet, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml(CONTENT Production.ProductDescriptionSchemaCollection));  
GO -- Default  
```  
  
 <span data-ttu-id="1d12d-163">Tenga en cuenta que puede especificar las facetas de DOCUMENT/CONTENT opcionales en cualquier lugar donde defina un tipo el `xml` (XML con tipo).</span><span class="sxs-lookup"><span data-stu-id="1d12d-163">Note that you can specify the optional DOCUMENT/CONTENT facets anywhere you define `xml` type (typed xml).</span></span> <span data-ttu-id="1d12d-164">Por ejemplo, cuando se crea una variable `xml` con tipo, se puede agregar la faceta DOCUMENT/CONTENT, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="1d12d-164">For example, when you create a typed `xml` variable, you can add the DOCUMENT/CONTENT facet, as shown in the following:</span></span>  
  
```  
declare @x xml (DOCUMENT Production.ProductDescriptionSchemaCollection);  
```  
  
## <a name="document-type-definition-dtd"></a><span data-ttu-id="1d12d-165">Definición de tipo de documento (DTD)</span><span class="sxs-lookup"><span data-stu-id="1d12d-165">Document Type Definition (DTD)</span></span>  
 <span data-ttu-id="1d12d-166">Las columnas de tipo de datos `xml`, las variables y los parámetros pueden obtener tipos utilizando un esquema XML, pero no mediante DTD.</span><span class="sxs-lookup"><span data-stu-id="1d12d-166">The `xml` data type columns, variables, and parameters can be typed by using XML schema, but not by using DTD.</span></span> <span data-ttu-id="1d12d-167">Sin embargo, se puede usar DTD insertado para XML con o sin tipo, para suministrar valores predeterminados y reemplazar referencias a entidades por su forma expandida.</span><span class="sxs-lookup"><span data-stu-id="1d12d-167">However, inline DTD can be used for both untyped and typed XML to supply default values and to replace entity references with their expanded form.</span></span>  
  
 <span data-ttu-id="1d12d-168">Puede convertir las DTD en documentos de esquemas XML mediante herramientas de otros fabricantes y cargar los esquemas XML en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d12d-168">You can convert DTDs to XML schema documents by using third-party tools, and load the XML schemas into the database.</span></span>  
  
## <a name="upgrading-typed-xml-from-sql-server-2005"></a><span data-ttu-id="1d12d-169">Actualizar XML con tipos desde SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="1d12d-169">Upgrading Typed XML from SQL Server 2005</span></span>  
 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="1d12d-170">ha realizado varias extensiones a la compatibilidad con esquemas XML, incluyendo la compatibilidad para la validación lax, el control mejorado de **xs:date**, **xs:time** y datos de instancia **xs:dateTime** , y compatibilidad agregada para tipos de lista y tipos de unión.</span><span class="sxs-lookup"><span data-stu-id="1d12d-170">made several extensions to the XML Schema support, including support for lax validation, improved handling of **xs:date**, **xs:time** and **xs:dateTime** instance data, and added support for list and union types.</span></span> <span data-ttu-id="1d12d-171">En la mayoría de los casos, los cambios no afectan a la experiencia de actualización.</span><span class="sxs-lookup"><span data-stu-id="1d12d-171">In most cases the changes do not affect the upgrade experience.</span></span> <span data-ttu-id="1d12d-172">Pero si usó una colección de esquemas XML en [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] que permitía valores del tipo **xs:date**, **xs:time**o **xs:dateTime** (o cualquier subtipo), los pasos de actualización siguientes se producen al adjuntar la base de datos de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o una versión posterior de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1d12d-172">However if you used an XML Schema collection in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] that allowed values of type **xs:date**, **xs:time**, or **xs:dateTime** (or any subtype) then the following upgrade steps occur when you attach your [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database to a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="1d12d-173">Para cada columna XML, que se escribe con una Colección de esquemas XML que contiene elementos o atributos escritos como **xs:anyType**, **xs:anySimpleType**, **xs:date** o cualquiera de sus subtipos, **xs:time** o cualquier subtipo, o **xs:dateTime** o cualquiera de sus subtipos ,o son tipos de unión o de lista que contienen cualquiera de estos tipos, se produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d12d-173">For every XML column, that is typed with an XML Schema Collection that contains elements or attributes that are typed as either **xs:anyType**, **xs:anySimpleType**, **xs:date** or any of its subtypes, **xs:time** or any subtype thereof, or **xs:dateTime** or any of its subtypes, or are union or list types containing any of these types the following occurs:</span></span>  
  
    1.  <span data-ttu-id="1d12d-174">Se deshabilitarán todos los índices XML de la columna.</span><span class="sxs-lookup"><span data-stu-id="1d12d-174">All XML indices on the column will be disabled.</span></span>  
  
    2.  <span data-ttu-id="1d12d-175">Todos los valores de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] continuarán representándose en la zona horaria Z porque se han normalizado a dicha zona horaria.</span><span class="sxs-lookup"><span data-stu-id="1d12d-175">All [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] values will continue to be represented in the Z timezone, because they have been normalized to the Z timezone.</span></span>  
  
    3.  <span data-ttu-id="1d12d-176">Cualquier valor **xs:date** o **xs:dateTime** que sea menor que el 1 de enero del año 1 llevará a un error en tiempo de ejecución cuando el índice se regenere o se ejecute una XQuery, o instrucciones XML-DML, con el tipo de datos XML que contiene dicho valor.</span><span class="sxs-lookup"><span data-stu-id="1d12d-176">Any **xs:date** or **xs:dateTime** values that are smaller than January 1st of year 1 will lead to a runtime error when the index gets rebuild or an XQuery or XML-DML statements gets executed against the XML data type containing that value.</span></span>  
  
2.  <span data-ttu-id="1d12d-177">Cualquier año negativo en las facetas o valores predeterminados **xs:date** o **xs:dateTime** de una colección de esquemas XML se actualizará automáticamente al valor más pequeño permitido por el tipo base **xs:date** o **xs:dateTime** (por ejemplo, 0001-01-01T00:00:00.0000000Z para **xs:dateTime**).</span><span class="sxs-lookup"><span data-stu-id="1d12d-177">Any negative years in **xs:date** or **xs:dateTime** facets or default values in an XML Schema collection will automatically be updated to the smallest value allowed by the base **xs:date** or **xs:dateTime** type (e.g., 0001-01-01T00:00:00.0000000Z for **xs:dateTime**).</span></span>  
  
 <span data-ttu-id="1d12d-178">Observe que todavía puede usar una instrucción SELECT de SQL para recuperar todo el tipo de datos XML, aun cuando contiene años negativos.</span><span class="sxs-lookup"><span data-stu-id="1d12d-178">Note that you can still use a simple SQL select statement to retrieve the whole XML data type, even if it contains negative years.</span></span> <span data-ttu-id="1d12d-179">Se recomienda que reemplace los años negativos por un año dentro del intervalo recientemente admitido o cambie el tipo del elemento o atributo a **xs:string**.</span><span class="sxs-lookup"><span data-stu-id="1d12d-179">It is recommended that you replace negative years with a year within the newly supported range or change the type of the element or attribute to **xs:string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d12d-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1d12d-180">See Also</span></span>  
 <span data-ttu-id="1d12d-181">[Crear instancias de datos XML](create-instances-of-xml-data.md) </span><span class="sxs-lookup"><span data-stu-id="1d12d-181">[Create Instances of XML Data](create-instances-of-xml-data.md) </span></span>  
 <span data-ttu-id="1d12d-182">[métodos del tipo de datos xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="1d12d-182">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="1d12d-183">[Lenguaje de manipulación de datos XML &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="1d12d-183">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="1d12d-184">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="1d12d-184">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
