---
title: Creación de instancias de datos XML | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- type casting string instances [XML in SQL Server]
- XML [SQL Server], typed
- xml data type [SQL Server], generating instances
- casting string instances [XML in SQL Server]
- typed XML
- generating XML instances [SQL Server]
- XML [SQL Server], generating instances
- white space [XML in SQL Server]
ms.assetid: dbd6c06f-db6e-44a7-855a-6a55bf374907
author: rothja
ms.author: jroth
ms.openlocfilehash: c857b9ebbe559de34fdac925642f9270d9cbf936
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752013"
---
# <a name="create-instances-of-xml-data"></a><span data-ttu-id="9302f-102">Crear instancias de datos XML</span><span class="sxs-lookup"><span data-stu-id="9302f-102">Create Instances of XML Data</span></span>
  <span data-ttu-id="9302f-103">En este tema se describe cómo generar las instancias XML.</span><span class="sxs-lookup"><span data-stu-id="9302f-103">This topic describes how to generate XML instances.</span></span>  
  
 <span data-ttu-id="9302f-104">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], podrá generar instancias XML de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9302f-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can generate XML instances in the following ways:</span></span>  
  
-   <span data-ttu-id="9302f-105">Instancias de cadenas de conversión de tipo.</span><span class="sxs-lookup"><span data-stu-id="9302f-105">Type casting string instances.</span></span>  
  
-   <span data-ttu-id="9302f-106">Usar la instrucción SELECT con la cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="9302f-106">Using the SELECT statement with the FOR XML clause.</span></span>  
  
-   <span data-ttu-id="9302f-107">Usar asignaciones de constantes.</span><span class="sxs-lookup"><span data-stu-id="9302f-107">Using constant assignments.</span></span>  
  
-   <span data-ttu-id="9302f-108">Usar la carga masiva.</span><span class="sxs-lookup"><span data-stu-id="9302f-108">Using bulk load.</span></span>  
  
## <a name="type-casting-string-and-binary-instances"></a><span data-ttu-id="9302f-109">Instancias de cadenas de conversión de tipo e instancias binarias</span><span class="sxs-lookup"><span data-stu-id="9302f-109">Type Casting String and Binary Instances</span></span>  
 <span data-ttu-id="9302f-110">Puede analizar cualquiera de los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos de cadena, como [**n**] [**var**]**Char**, **[n] Text**, **varbinary**e **Image**, en el `xml` tipo de datos mediante la conversión (conversión) o la conversión (conversión) de la cadena en el `xml` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9302f-110">You can parse any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] string data types, such as [**n**][**var**]**char**, **[n]text**, **varbinary**,and **image**, into the `xml` data type by casting (CAST) or converting (CONVERT) the string to the `xml` data type.</span></span> <span data-ttu-id="9302f-111">Se comprueba el XML sin tipo para confirmar que su formato es correcto.</span><span class="sxs-lookup"><span data-stu-id="9302f-111">Untyped XML is checked to confirm that it is well formed.</span></span> <span data-ttu-id="9302f-112">Si hay un esquema asociado al `xml` tipo, también se realiza la validación.</span><span class="sxs-lookup"><span data-stu-id="9302f-112">If there is a schema associated with the `xml` type, validation is also performed.</span></span> <span data-ttu-id="9302f-113">Para obtener más información, vea [Comparar XML con tipo y XML sin tipo](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9302f-113">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
 <span data-ttu-id="9302f-114">Los documentos XML pueden codificarse con distintas codificaciones (por ejemplo, UTF-8, UTF-16, windows-1252).</span><span class="sxs-lookup"><span data-stu-id="9302f-114">XML documents can be encoded with different encodings (for example, UTF-8, UTF-16, windows-1252).</span></span> <span data-ttu-id="9302f-115">A continuación se describen de forma resumida las reglas que establecen el modo en que los tipos de origen de cadena y binarios interactúan con la codificación del documento XML y cómo se comporta el analizador.</span><span class="sxs-lookup"><span data-stu-id="9302f-115">The following outlines the rules on how the string and binary source types interact with the XML document encoding and how the parser behaves.</span></span>  
  
 <span data-ttu-id="9302f-116">Puesto que **nvarchar** asume una codificación Unicode de dos bytes como UTF-16 o UCS-2, el analizador de XML tratará el valor de cadena como un documento o fragmento XML codificado con Unicode de dos bytes.</span><span class="sxs-lookup"><span data-stu-id="9302f-116">Since **nvarchar** assumes a two-byte unicode encoding such as UTF-16 or UCS-2, the XML parser will treat the string value as a two-byte Unicode encoded XML document or fragment.</span></span> <span data-ttu-id="9302f-117">Esto significa que el documento XML también debe codificarse con codificación Unicode de dos bytes para que sea compatible con el tipo de datos de origen.</span><span class="sxs-lookup"><span data-stu-id="9302f-117">This means that the XML document needs to be encoded in a two-byte Unicode encoding as well to be compatible with the source data type.</span></span> <span data-ttu-id="9302f-118">Un documento XML con codificación UTF-16 puede tener una marca de orden de bytes (BOM) UTF-16, pero no es necesario que la tenga ya que el contexto del tipo de origen indica claramente que solo puede tratarse de un documento con codificación Unicode de dos bytes.</span><span class="sxs-lookup"><span data-stu-id="9302f-118">A UTF-16 encoded XML document can have a UTF-16 byte order mark (BOM), but it does not need to, since the context of the source type makes it clear that it can only be a two-byte Unicode encoded document.</span></span>  
  
 <span data-ttu-id="9302f-119">El analizador de XML trata el contenido de una cadena **varchar** como un documento o fragmento XML con codificación de un byte.</span><span class="sxs-lookup"><span data-stu-id="9302f-119">The content of a **varchar** string is treated as a one-byte encoded XML document/fragment by the XML parser.</span></span> <span data-ttu-id="9302f-120">Puesto que la cadena de origen **varchar** tiene una página de códigos asociada, el analizador utilizará dicha página de códigos para la codificación si no se especifica ninguna codificación explícita en el XML. Si una instancia de XML tiene una marca BOM o una declaración de codificación, éstas deben ser coherentes con la página de códigos, de lo contrario el analizador notificará un error.</span><span class="sxs-lookup"><span data-stu-id="9302f-120">Since the **varchar** source string has a code page associated, the parser will use that code page for the encoding if no explicit encoding is specified in the XML itself If an XML instance has a BOM or an encoding declaration, the BOM or declaration needs to be consistent with the code page, otherwise the parser will report an error.</span></span>  
  
 <span data-ttu-id="9302f-121">El contenido de **varbinary** se trata como un flujo de puntos de código que se pasa directamente al analizador de XML.</span><span class="sxs-lookup"><span data-stu-id="9302f-121">The content of **varbinary** is treated as a codepoint stream that is passed directly to the XML parser.</span></span> <span data-ttu-id="9302f-122">Por consiguiente, el documento o fragmento XML debe proporcionar la marca BOM u otro tipo de información de codificación insertada.</span><span class="sxs-lookup"><span data-stu-id="9302f-122">Thus, the XML document or fragment needs to provide the BOM or other encoding information inline.</span></span> <span data-ttu-id="9302f-123">Para determinar la codificación, el analizador solo consultará el flujo.</span><span class="sxs-lookup"><span data-stu-id="9302f-123">The parser will only look at the stream to determine the encoding.</span></span> <span data-ttu-id="9302f-124">Esto significa que el XML con codificación UTF-16 debe proporcionar la marca BOM UTF-16 y que una instancia sin marca BOM y sin una codificación de declaración se interpretará como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="9302f-124">This means that UTF-16 encoded XML needs to provide the UTF-16 BOM and an instance without BOM and without a declaration encoding will be interpreted as UTF-8.</span></span>  
  
 <span data-ttu-id="9302f-125">Si la codificación del documento XML no se conoce de antemano y los datos se pasan como datos de cadena o datos binarios en lugar de pasarse como datos XML antes de realizar su conversión a XML, es recomendable tratar los datos como **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="9302f-125">If the encoding of the XML document is not known in advance and the data is passed as string or binary data instead of XML data before casting to XML, it is recommended to treat the data as **varbinary**.</span></span> <span data-ttu-id="9302f-126">Por ejemplo, si se leen datos de un archivo XML usando OpenRowset(), es necesario especificar los datos que deben leerse como un valor **varbinary(max)** :</span><span class="sxs-lookup"><span data-stu-id="9302f-126">For example, when reading data from an XML file using OpenRowset(), one should specify the data to be read as a **varbinary(max)** value:</span></span>  
  
```  
select CAST(x as XML)   
from OpenRowset(BULK 'filename.xml', SINGLE_BLOB) R(x)  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9302f-127">representa internamente XML en una representación binaria eficaz que usa la codificación UTF-16.</span><span class="sxs-lookup"><span data-stu-id="9302f-127">internally represents XML in an efficient binary representation that uses UTF-16 encoding.</span></span> <span data-ttu-id="9302f-128">La codificación proporcionada por el usuario no se mantiene, pero se tiene en cuenta durante el proceso de análisis.</span><span class="sxs-lookup"><span data-stu-id="9302f-128">User-provided encoding is not preserved, but is considered during the parse process.</span></span>  
  
### <a name="type-casting-clr-user-defined-types"></a><span data-ttu-id="9302f-129">Conversión de tipos definidos por el usuario CLR</span><span class="sxs-lookup"><span data-stu-id="9302f-129">Type Casting CLR user-defined types</span></span>  
 <span data-ttu-id="9302f-130">Si un tipo definido por el usuario CLR tiene una serialización XML, las instancias de dicho tipo pueden convertirse explícitamente a un tipo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="9302f-130">If a CLR user-defined type has an XML Serialization, instances of that type can be explicitly cast to an XML datatype.</span></span> <span data-ttu-id="9302f-131">Para obtener más información sobre la serialización XML de un tipo de datos definido por el usuario CLR, vea [Serialización XML de objetos de base de datos de CLR](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="9302f-131">For more details about the XML serialization of a CLR user-defined typed, see [XML Serialization from CLR Database Objects](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span></span>  
  
### <a name="white-space-handling-in-typed-xml"></a><span data-ttu-id="9302f-132">Control de los espacios en blanco en XML con tipo</span><span class="sxs-lookup"><span data-stu-id="9302f-132">White Space Handling in Typed XML</span></span>  
 <span data-ttu-id="9302f-133">En [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], los espacios en blanco en el contenido de los elementos se consideran no significativos si aparecen en una secuencia de datos de caracteres únicamente de espacios en blanco delimitados por caracteres de marcado, como etiquetas iniciales o finales, y no se crea una entidad para los mismos.</span><span class="sxs-lookup"><span data-stu-id="9302f-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], white space inside element content is considered insignificant if it occurs inside a sequence of white-space-only character data delimited by markup, such as begin or end tags, and is not entitized.</span></span> <span data-ttu-id="9302f-134">Las secciones CDATA se omiten. Este control de los espacios en blanco es distinto de lo que se describe en la especificación XML 1.0 publicada por el World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="9302f-134">(CDATA sections are ignored.) This handling of white space handling is different from how white space is described in the XML 1.0 specification published by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="9302f-135">Esto se debe a que el analizador de XML de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solo reconoce un número limitado de subconjuntos de DTD, tal como se define en XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="9302f-135">This is because the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recognizes only a limited number of DTD subsets, as defined in XML 1.0.</span></span> <span data-ttu-id="9302f-136">Para obtener más información sobre los subconjuntos de DTD limitados que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite, vea [CAST y CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9302f-136">For more information about the limited DTD subsets supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
 <span data-ttu-id="9302f-137">De forma predeterminada, el analizador de XML descarta los espacios en blanco insignificantes cuando convierte datos de cadena a XML si se da alguna de las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9302f-137">By default, the XML parser discards insignificant white space when it converts string data to XML if either of the following is true:</span></span>  
  
-   <span data-ttu-id="9302f-138">`The xml:space` en un elemento o en sus elementos antecesores.</span><span class="sxs-lookup"><span data-stu-id="9302f-138">`The xml:space` attribute is not defined on an element or its ancestor elements.</span></span>  
  
-   <span data-ttu-id="9302f-139">El atributo `xml:space` activo en un elemento, o uno de sus elementos antecesores, tiene el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9302f-139">The `xml:space` attribute in effect on an element, or one of its ancestor elements, has the value of default.</span></span>  
  
 <span data-ttu-id="9302f-140">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9302f-140">For example:</span></span>  
  
```  
declare @x xml  
set @x = '<root>      <child/>     </root>'  
select @x   
```  
  
 <span data-ttu-id="9302f-141">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9302f-141">This is the result:</span></span>  
  
```  
<root><child/></root>  
```  
  
 <span data-ttu-id="9302f-142">No obstante, puede cambiar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="9302f-142">However, you can change this behavior.</span></span> <span data-ttu-id="9302f-143">Para mantener los espacios en blanco de una instancia DT xml, utilice el operador CONVERT y su parámetro *style* opcional establecido en el valor 1.</span><span class="sxs-lookup"><span data-stu-id="9302f-143">To preserve white space for an xml DT instance, use the CONVERT operator and its optional *style* parameter set to a value of 1.</span></span> <span data-ttu-id="9302f-144">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9302f-144">For example:</span></span>  
  
```  
SELECT CONVERT(xml, N'<root>      <child/>     </root>', 1)  
```  
  
 <span data-ttu-id="9302f-145">Si no se utiliza el parámetro *style* o su valor es 0, no se mantendrán los espacios en blanco insignificantes para la conversión de la instancia DT xml.</span><span class="sxs-lookup"><span data-stu-id="9302f-145">If the *style* parameter is either not used or its value is set to 0, insignificant white space is not preserved for the conversion of the xml DT instance.</span></span> <span data-ttu-id="9302f-146">Para obtener más información sobre cómo usar el operador CONVERT y su parámetro *style* al convertir datos de cadena a instancias DT xml, vea [CAST y CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9302f-146">For more information about how to use the CONVERT operator and its *style* parameter when converting string data to xml DT instances, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
### <a name="example-cast-a-string-value-to-typed-xml-and-assign-it-to-a-column"></a><span data-ttu-id="9302f-147">Ejemplo: Conversión de un valor de cadena a XML con tipo y asignación a una columna</span><span class="sxs-lookup"><span data-stu-id="9302f-147">Example: Cast a string value to typed xml and assign it to a column</span></span>  
 <span data-ttu-id="9302f-148">En el ejemplo siguiente se convierte una variable de cadena que contiene un fragmento XML en el `xml` tipo de datos y, a continuación, se almacena en la `xml` columna de tipo:</span><span class="sxs-lookup"><span data-stu-id="9302f-148">The following example casts a string variable that contains an XML fragment to the `xml` data type and then stores it in the `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
go  
DECLARE  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
```  
  
 <span data-ttu-id="9302f-149">La siguiente operación de inserción convierte implícitamente de una cadena al `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="9302f-149">The following insert operation implicitly converts from a string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, @s)   
```  
  
 <span data-ttu-id="9302f-150">Puede convertir explícitamente () la cadena al `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="9302f-150">You can explicitly cast() the string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, cast (@s as xml))  
```  
  
 <span data-ttu-id="9302f-151">También se puede utilizar convert(), tal como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="9302f-151">Or you can use convert(), as shown in the following:</span></span>  
  
```  
INSERT INTO T VALUES (3, convert (xml, @s))   
```  
  
### <a name="example-convert-a-string-to-typed-xml-and-assign-it-to-a-variable"></a><span data-ttu-id="9302f-152">Ejemplo: Conversión de una cadena a XML con tipo y asignación a una variable</span><span class="sxs-lookup"><span data-stu-id="9302f-152">Example: Convert a string to typed xml and assign it to a variable</span></span>  
 <span data-ttu-id="9302f-153">En el ejemplo siguiente, una cadena se convierte al `xml` tipo y se asigna a una variable del `xml` tipo de datos:</span><span class="sxs-lookup"><span data-stu-id="9302f-153">In the following example, a string is converted to `xml` type and assigned to a variable of the `xml` data type:</span></span>  
  
```  
declare @x xml  
declare  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
set @x =convert (xml, @s)  
select @x  
```  
  
## <a name="using-the-select-statement-with-a-for-xml-clause"></a><span data-ttu-id="9302f-154">Usar la instrucción SELECT con la cláusula FOR XML</span><span class="sxs-lookup"><span data-stu-id="9302f-154">Using the SELECT Statement with a FOR XML Clause</span></span>  
 <span data-ttu-id="9302f-155">Se puede utilizar la cláusula FOR XML en una instrucción SELECT para devolver resultados como XML.</span><span class="sxs-lookup"><span data-stu-id="9302f-155">You can use the FOR XML clause in a SELECT statement to return results as XML.</span></span> <span data-ttu-id="9302f-156">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9302f-156">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = (SELECT Column1, Column2  
               FROM   Table1, Table2  
               WHERE   Some condition  
               FOR XML AUTO)  
 ...  
```  
  
 <span data-ttu-id="9302f-157">La instrucción SELECT devuelve un fragmento XML de texto que se analiza durante la asignación a la `xml` variable de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9302f-157">The SELECT statement returns a textual XML fragment that is then parsed during the assignment to the `xml` data type variable.</span></span>  
  
 <span data-ttu-id="9302f-158">También puede utilizar la [Directiva Type](type-directive-in-for-xml-queries.md) en la cláusula for XML que devuelve directamente un resultado de consulta for XML como `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="9302f-158">You can also use the [TYPE directive](type-directive-in-for-xml-queries.md) in the FOR XML clause that directly returns a FOR XML query result as `xml` type:</span></span>  
  
```  
Declare @xmlDoc xml  
SET @xmlDoc = (SELECT ProductModelID, Name  
               FROM   Production.ProductModel  
               WHERE  ProductModelID=19  
               FOR XML AUTO, TYPE)  
SELECT @xmlDoc  
```  
  
 <span data-ttu-id="9302f-159">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="9302f-159">This is the result:</span></span>  
  
```  
<Production.ProductModel ProductModelID="19" Name="Mountain-100" />...  
```  
  
 <span data-ttu-id="9302f-160">En el ejemplo siguiente, el resultado con tipo `xml` de una consulta for XML se inserta en una `xml` columna de tipo:</span><span class="sxs-lookup"><span data-stu-id="9302f-160">In the following example, the typed `xml` result of a FOR XML query is inserted into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T1 (c1 int, c2 xml)  
go  
INSERT T1(c1, c2)  
SELECT 1, (SELECT ProductModelID, Name  
           FROM Production.ProductModel  
           WHERE ProductModelID=19  
           FOR XML AUTO, TYPE)  
SELECT * FROM T1  
go  
```  
  
 <span data-ttu-id="9302f-161">Para obtener más información sobre FOR XML, vea [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9302f-161">For more information about FOR XML, see [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9302f-162">devuelve instancias de tipo de datos `xml` al cliente como resultado de las distintas construcciones del servidor, como consultas FOR XML que utilizan la directiva TYPE, o donde se utiliza el tipo de datos `xml` para devolver XML a partir de parámetros de salida, variables y columnas SQL.</span><span class="sxs-lookup"><span data-stu-id="9302f-162">returns `xml` data type instances to the client as a result of different server constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML from SQL columns, variables, and output parameters.</span></span> <span data-ttu-id="9302f-163">En el código de la aplicación cliente, el proveedor ADO.NET solicita que la información de tipos de datos `xml` se envíe en una codificación binaria desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="9302f-163">In client application code, the ADO.NET provider requests that this `xml` data type information be sent in a binary encoding from the server.</span></span> <span data-ttu-id="9302f-164">No obstante, si se está utilizando FOR XML sin la directiva TYPE, los datos XML se devuelven como un tipo de cadena.</span><span class="sxs-lookup"><span data-stu-id="9302f-164">However, if you are using FOR XML without the TYPE directive, the XML data returns as a string type.</span></span> <span data-ttu-id="9302f-165">En cualquier caso, el proveedor del cliente siempre podrá controlar cualquier formato de tipo XML.</span><span class="sxs-lookup"><span data-stu-id="9302f-165">In any case, the client provider will always be able to handle either form of XML.</span></span>  
  
## <a name="using-constant-assignments"></a><span data-ttu-id="9302f-166">Usar asignaciones de constantes</span><span class="sxs-lookup"><span data-stu-id="9302f-166">Using Constant Assignments</span></span>  
 <span data-ttu-id="9302f-167">Se puede utilizar una constante de cadena cuando se espera una instancia del `xml` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="9302f-167">A string constant can be used where an instance of the `xml` data type is expected.</span></span> <span data-ttu-id="9302f-168">Es lo mismo que una conversión (CAST) implícita de cadena a XML.</span><span class="sxs-lookup"><span data-stu-id="9302f-168">This is the same as an implied CAST of string to XML.</span></span> <span data-ttu-id="9302f-169">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9302f-169">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
-- Or  
SET @xmlDoc = N'<?xml version="1.0" encoding="ucs-2"?><doc/>'  
```  
  
 <span data-ttu-id="9302f-170">En el ejemplo anterior se convierte implícitamente la cadena al `xml` tipo de datos y se asigna a una `xml` variable de tipo.</span><span class="sxs-lookup"><span data-stu-id="9302f-170">The previous example implicitly converts the string to the `xml` data type and assigns it to an `xml` type variable.</span></span>  
  
 <span data-ttu-id="9302f-171">En el ejemplo siguiente se inserta una cadena de constante en una `xml` columna de tipo:</span><span class="sxs-lookup"><span data-stu-id="9302f-171">The following example inserts a constant string into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
INSERT INTO T VALUES (3, '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>')   
```  
  
> [!NOTE]  
>  <span data-ttu-id="9302f-172">El XML con tipo se valida con el esquema especificado.</span><span class="sxs-lookup"><span data-stu-id="9302f-172">For typed XML, the XML is validated against the specified schema.</span></span> <span data-ttu-id="9302f-173">Para obtener más información, vea [Comparar XML con tipo y XML sin tipo](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="9302f-173">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
## <a name="using-bulk-load"></a><span data-ttu-id="9302f-174">Usar la carga masiva</span><span class="sxs-lookup"><span data-stu-id="9302f-174">Using Bulk Load</span></span>  
 <span data-ttu-id="9302f-175">La funcionalidad mejorada [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) permite la carga masiva de documentos XML en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9302f-175">The enhanced [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) functionality allows you to bulk load XML documents in the database.</span></span> <span data-ttu-id="9302f-176">Puede cargar de forma masiva instancias XML desde archivos en las `xml` columnas de tipo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9302f-176">You can bulk load XML instances from files into the `xml` type columns in the database.</span></span> <span data-ttu-id="9302f-177">Para obtener ejemplos prácticos, vea [Ejemplos de importación y exportación en bloque documentos XML &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9302f-177">For working samples, see [Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span></span> <span data-ttu-id="9302f-178">Para obtener más información sobre cómo cargar documentos XML, vea [Cargar datos XML](load-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="9302f-178">For more information about loading XML documents, see [Load XML Data](load-xml-data.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9302f-179">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9302f-179">In This Section</span></span>  
  
|<span data-ttu-id="9302f-180">Tema</span><span class="sxs-lookup"><span data-stu-id="9302f-180">Topic</span></span>|<span data-ttu-id="9302f-181">Descripción</span><span class="sxs-lookup"><span data-stu-id="9302f-181">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="9302f-182">Recuperar y consultar datos XML</span><span class="sxs-lookup"><span data-stu-id="9302f-182">Retrieve and Query XML Data</span></span>](retrieve-and-query-xml-data.md)|<span data-ttu-id="9302f-183">Describe las partes de las instancias XML que no se conservan cuando se almacenan en bases de datos.</span><span class="sxs-lookup"><span data-stu-id="9302f-183">Describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9302f-184">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9302f-184">See Also</span></span>  
 <span data-ttu-id="9302f-185">[Comparar XML con tipo y XML sin tipo](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="9302f-185">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="9302f-186">[métodos del tipo de datos xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="9302f-186">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="9302f-187">[Lenguaje de manipulación de datos XML &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="9302f-187">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="9302f-188">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9302f-188">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
