---
title: Definición de la serialización de datos XML | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- entitization rules [XML in SQL Server]
- serialization
- reparsing serialized XML structures
- encoding [XML in SQL Server]
- XML [SQL Server], serialization
- xml data type [SQL Server], serialization
- typed XML
ms.assetid: 42b0b5a4-bdd6-4a60-b451-c87f14758d4b
author: rothja
ms.author: jroth
ms.openlocfilehash: df87dddd9fd4cf067125314c9d798eaa42523576
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677450"
---
# <a name="define-the-serialization-of-xml-data"></a><span data-ttu-id="c9d00-102">Definir la serialización de datos XML</span><span class="sxs-lookup"><span data-stu-id="c9d00-102">Define the Serialization of XML Data</span></span>
  <span data-ttu-id="c9d00-103">Cuando el tipo de datos xml se convierte de manera explícita o implícita a un tipo SQL binario o de cadena, el contenido del tipo de datos xml se serializa de acuerdo con las reglas que se describen en este tema.</span><span class="sxs-lookup"><span data-stu-id="c9d00-103">When casting the xml data type explicitly or implicitly to a SQL string or binary type, the content of the xml data type will be serialized according to the rules outlined in this topic.</span></span>  
  
## <a name="serialization-encoding"></a><span data-ttu-id="c9d00-104">Codificación de la serialización</span><span class="sxs-lookup"><span data-stu-id="c9d00-104">Serialization Encoding</span></span>  
 <span data-ttu-id="c9d00-105">Si el tipo SQL de destino es VARBINARY, el resultado se serializa en UTF-16 con una marca de orden de bytes UTF-16 delante, pero sin una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="c9d00-105">If the SQL target type is VARBINARY, the result is serialized in UTF-16 with a UTF-16-byte order mark in front, but without an XML declaration.</span></span> <span data-ttu-id="c9d00-106">Si el tipo de destino es demasiado pequeño, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="c9d00-106">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="c9d00-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9d00-107">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARBINARY(MAX))  
```  
  
 <span data-ttu-id="c9d00-108">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9d00-108">This is the result:</span></span>  
  
```  
0xFFFE3C0094032F003E00  
```  
  
 <span data-ttu-id="c9d00-109">Si el tipo SQL de destino es NVARCHAR o NCHAR, el resultado se serializa en UTF-16 sin una marca de orden de bytes y sin una declaración XML.</span><span class="sxs-lookup"><span data-stu-id="c9d00-109">If the SQL target type is NVARCHAR or NCHAR, the result is serialized in UTF-16 without the byte order mark in front and without an XML declaration.</span></span> <span data-ttu-id="c9d00-110">Si el tipo de destino es demasiado pequeño, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="c9d00-110">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="c9d00-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9d00-111">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as NVARCHAR(MAX))  
```  
  
 <span data-ttu-id="c9d00-112">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9d00-112">This is the result:</span></span>  
  
```  
<Δ/>  
```  
  
 <span data-ttu-id="c9d00-113">Si el tipo SQL de destino es VARCHAR o NCHAR, el resultado se serializa en la codificación que corresponda a la página de códigos de intercalación de la base de datos, sin marca de orden de bytes ni declaración XML.</span><span class="sxs-lookup"><span data-stu-id="c9d00-113">If the SQL target type is VARCHAR or NCHAR, the result is serialized in the encoding that corresponds to the database's collation code page without a byte order mark or XML declaration.</span></span> <span data-ttu-id="c9d00-114">Si el tipo de destino es demasiado pequeño o el valor no se puede asignar a la página de códigos de intercalación de destino, se genera un error.</span><span class="sxs-lookup"><span data-stu-id="c9d00-114">If the target type is too small or the value cannot be mapped to the target collation code page, an error is raised.</span></span>  
  
 <span data-ttu-id="c9d00-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9d00-115">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARCHAR(MAX))  
```  
  
 <span data-ttu-id="c9d00-116">Esto puede producir un error si la página de códigos de la intercalación actual no puede representar el carácter Unicode & # x10300;, o lo representará en la codificación específica.</span><span class="sxs-lookup"><span data-stu-id="c9d00-116">This may result in an error, if the current collation's code page cannot represent the Unicode character &#x10300;, or it will represent it in the specific encoding.</span></span>  
  
 <span data-ttu-id="c9d00-117">Cuando se devuelven los resultados XML al cliente, los datos se envían codificados como UTF-16.</span><span class="sxs-lookup"><span data-stu-id="c9d00-117">When returning XML results to the client side, the data will be sent in UTF-16 encoding.</span></span> <span data-ttu-id="c9d00-118">Después, el proveedor del lado cliente expondrá los datos de acuerdo con sus reglas de API.</span><span class="sxs-lookup"><span data-stu-id="c9d00-118">The client-side provider will then expose the data according to its API rules.</span></span>  
  
## <a name="serialization-of-the-xml-structures"></a><span data-ttu-id="c9d00-119">Serialización de las estructuras XML</span><span class="sxs-lookup"><span data-stu-id="c9d00-119">Serialization of the XML Structures</span></span>  
 <span data-ttu-id="c9d00-120">El contenido de un tipo de datos **xml** se serializa de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="c9d00-120">The content of an **xml** data type is serialized in the usual way.</span></span> <span data-ttu-id="c9d00-121">Concretamente, los nodos de elementos se asignan a marcado de elemento y los nodos de texto se asignan a contenido de texto.</span><span class="sxs-lookup"><span data-stu-id="c9d00-121">Specifically, element nodes are mapped to element markup, and text nodes are mapped to text content.</span></span> <span data-ttu-id="c9d00-122">No obstante, en las siguientes secciones se describen las circunstancias en las que se crean entidades para los caracteres y cómo se serializan los valores atómicos con tipo.</span><span class="sxs-lookup"><span data-stu-id="c9d00-122">However, the circumstances under which characters are entitized and how typed atomic values are serialized are described in the following sections.</span></span>  
  
## <a name="entitization-of-xml-characters-during-serialization"></a><span data-ttu-id="c9d00-123">Creación de entidades para caracteres XML durante la serialización</span><span class="sxs-lookup"><span data-stu-id="c9d00-123">Entitization of XML Characters During Serialization</span></span>  
 <span data-ttu-id="c9d00-124">Todas las estructuras XML serializadas deberían poder analizarse de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c9d00-124">Every serialized XML structure should be capable of being reparsed.</span></span> <span data-ttu-id="c9d00-125">Por tanto, algunos caracteres deben serializarse como entidades para que conserven su funcionalidad de ida y vuelta durante la fase de normalización del analizador XML.</span><span class="sxs-lookup"><span data-stu-id="c9d00-125">Therefore, some characters have to be serialized in an entitized way to preserve the round-trip capability of the characters through the XML parser's normalization phase .</span></span> <span data-ttu-id="c9d00-126">Sin embargo, deben crearse entidades para algunos caracteres con el fin de que el formato del documento sea correcto, y, por tanto, se pueda analizar.</span><span class="sxs-lookup"><span data-stu-id="c9d00-126">However, some characters have to be entitized so that the document is well-formed and, therefore, able to be parsed.</span></span> <span data-ttu-id="c9d00-127">A continuación se exponen las reglas de creación de entidades que se aplican durante la serialización:</span><span class="sxs-lookup"><span data-stu-id="c9d00-127">Following are the entitization rules that apply during serialization:</span></span>  
  
-   <span data-ttu-id="c9d00-128">Para los caracteres &, \<, and > siempre se crean las entidades &amp;, &lt; y &gt;, respectivamente, si aparecen en valores de atributos o en el contenido de elementos.</span><span class="sxs-lookup"><span data-stu-id="c9d00-128">The characters &, \<, and > are always entitized to &amp;, &lt;, and &gt; respectively, if they occur inside an attribute value or element content.</span></span>  
  
-   <span data-ttu-id="c9d00-129">Dado que SQL Server usa comillas (U+0022) para incluir los valores de los atributos, para las comillas de los valores de atributo se crea la entidad &quot;.</span><span class="sxs-lookup"><span data-stu-id="c9d00-129">Because SQL Server uses a quotation mark (U+0022) for enclosing attribute values, the quotation mark in attribute values is entitized as &quot;.</span></span>  
  
-   <span data-ttu-id="c9d00-130">La entidad que se crea para un par suplente es una única referencia de carácter numérico, solo cuando la conversión se realiza en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c9d00-130">A surrogate pair is entitized as a single numeric character reference, when casting on the server only.</span></span> <span data-ttu-id="c9d00-131">Por ejemplo, el par suplente U+D800 U+DF00 pasa a ser la entidad de referencia de carácter numérico &\#x00010300;.</span><span class="sxs-lookup"><span data-stu-id="c9d00-131">For example the surrogate pair U+D800 U+DF00 is entitized to the numeric character reference &\#x00010300;.</span></span>  
  
-   <span data-ttu-id="c9d00-132">Para evitar que un carácter de tabulación (U+0009) o avance de línea (LF, U+000A) se normalice durante el análisis, tendrán como entidades sus referencias de carácter numérico (&\#x9; y &\#xA;, respectivamente) en los valores de atributos.</span><span class="sxs-lookup"><span data-stu-id="c9d00-132">To protect a TAB (U+0009) and a linefeed (LF, U+000A) from being normalized during parsing, they are entitized to their numeric character references &\#x9; and &\#xA; respectively, inside attribute values.</span></span>  
  
-   <span data-ttu-id="c9d00-133">Para evitar que un carácter de retorno de carro (CR, U+000D) se normalice durante el análisis, tendrá como entidad su referencia de carácter numérico (&\#xD;) en los valores de atributos y en el contenido de elementos.</span><span class="sxs-lookup"><span data-stu-id="c9d00-133">To prevent a carriage return (CR, U+000D) from being normalized during parsing, it is entitized to its numeric character reference, &\#xD; inside both attribute values and element content.</span></span>  
  
-   <span data-ttu-id="c9d00-134">Para proteger los nodos de texto que solo contienen espacios en blanco, se crea una entidad para uno de los caracteres de espacio en blanco, generalmente el último, que se corresponde con su referencia de carácter numérico.</span><span class="sxs-lookup"><span data-stu-id="c9d00-134">To protect text nodes that only contain white space, one of the white-space characters, generally the last one, is entitized as its numeric character reference.</span></span> <span data-ttu-id="c9d00-135">De esta manera, cuando se vuelve a realizar el análisis, se conserva el nodo de texto de espacio en blanco independientemente de la configuración del control de espacios en blanco durante el análisis.</span><span class="sxs-lookup"><span data-stu-id="c9d00-135">In this way, reparsing preserves the white-space text node, regardless of the setting of the white-space handling during parsing.</span></span>  
  
 <span data-ttu-id="c9d00-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9d00-136">For example:</span></span>  
  
```sql
declare @u NVARCHAR(50)  
set @u = N'<a a="  
    '+NCHAR(0xD800)+NCHAR(0xDF00)+N'>">   '+NCHAR(0xA)+N'</a>'  
select CAST(CONVERT(XML,@u,1) as NVARCHAR(50))  
```  
  
 <span data-ttu-id="c9d00-137">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9d00-137">This is the result:</span></span>  
  
```  
<a a="  
    𐌀>">     
</a>  
```  
  
 <span data-ttu-id="c9d00-138">Si no quiere aplicar la regla de protección del último espacio en blanco, puede usar la opción explícita de CONVERT 1 al convertir el tipo **xml** en un tipo de cadena o binario.</span><span class="sxs-lookup"><span data-stu-id="c9d00-138">If you do not want to apply the last white-space protection rule, you can use the explicit CONVERT option 1 when casting from **xml** to a string or binary type.</span></span> <span data-ttu-id="c9d00-139">Por ejemplo, para evitar la creación de entidades, tiene las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c9d00-139">For example, to avoid entitization, you can do the following:</span></span>  
  
```sql
select CONVERT(NVARCHAR(50), CONVERT(XML, '<a>   </a>', 1), 1)  
```  
  
 <span data-ttu-id="c9d00-140">Tenga en cuenta que [query() (método de tipo de datos xml)](/sql/t-sql/xml/query-method-xml-data-type) genera una instancia de tipo de datos xml.</span><span class="sxs-lookup"><span data-stu-id="c9d00-140">Note that, the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) results in an xml data type instance.</span></span> <span data-ttu-id="c9d00-141">Por tanto, se crearán entidades para cualquier resultado del método **query()** que se convierta en un tipo binario o de cadena de acuerdo con las reglas previamente descritas.</span><span class="sxs-lookup"><span data-stu-id="c9d00-141">Therefore, any result of the **query()** method that is cast to a string or binary type is entitized according to the previously described rules.</span></span> <span data-ttu-id="c9d00-142">Si se quieren obtener los valores de cadena sin creación de entidades, en su lugar debe usarse [value() (método del tipo de datos xml)](/sql/t-sql/xml/value-method-xml-data-type) .</span><span class="sxs-lookup"><span data-stu-id="c9d00-142">If you want to obtain the string values that are not entitized, you should use the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) instead.</span></span> <span data-ttu-id="c9d00-143">A continuación se ofrece un ejemplo de uso del método **query()** :</span><span class="sxs-lookup"><span data-stu-id="c9d00-143">Following is an example of using the **query()** method:</span></span>  
  
```sql
declare @x xml  
set @x = N'<a>This example contains an entitized char: <.</a>'  
select @x.query('/a/text()')  
```  
  
 <span data-ttu-id="c9d00-144">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9d00-144">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
 <span data-ttu-id="c9d00-145">A continuación se ofrece un ejemplo de uso del método **value()** :</span><span class="sxs-lookup"><span data-stu-id="c9d00-145">Following is an example of using the **value()** method:</span></span>  
  
```sql
select @x.value('(/a/text())[1]', 'nvarchar(100)')  
```  
  
 <span data-ttu-id="c9d00-146">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9d00-146">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
## <a name="serializing-a-typed-xml-data-type"></a><span data-ttu-id="c9d00-147">Serializar un tipo de datos xml con tipo</span><span class="sxs-lookup"><span data-stu-id="c9d00-147">Serializing a Typed xml Data Type</span></span>  
 <span data-ttu-id="c9d00-148">Una instancia de tipo de datos **xml** con tipo contiene valores cuyos tipos se corresponden con los tipos de su esquema XML.</span><span class="sxs-lookup"><span data-stu-id="c9d00-148">A typed **xml** data type instance contains values that are typed according to their XML schema types.</span></span> <span data-ttu-id="c9d00-149">Estos valores se serializan según su tipo de esquema XML, en el mismo formato que genera la conversión XQuery a xs:string.</span><span class="sxs-lookup"><span data-stu-id="c9d00-149">These values are serialized according to their XML schema type in the same format as the XQuery cast to xs:string produces.</span></span> <span data-ttu-id="c9d00-150">Para obtener más información, vea [Reglas de conversión de tipos en XQuery](/sql/xquery/type-casting-rules-in-xquery).</span><span class="sxs-lookup"><span data-stu-id="c9d00-150">For more information, see [Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery).</span></span>  
  
 <span data-ttu-id="c9d00-151">Por ejemplo, el valor 1.34e1 de tipo xs:double se serializa como 13.4, como se observa en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9d00-151">For example, the xs:double value 1.34e1 is serialized to 13.4 as shown in the following example:</span></span>  
  
```sql
declare @x xml  
set @x =''  
select CAST(@x.query('1.34e1') as nvarchar(50))  
```  
  
 <span data-ttu-id="c9d00-152">Se obtiene el valor de cadena 13.4.</span><span class="sxs-lookup"><span data-stu-id="c9d00-152">This returns the string value 13.4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d00-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9d00-153">See Also</span></span>  
 <span data-ttu-id="c9d00-154">[Reglas de conversión de tipos en XQuery](/sql/xquery/type-casting-rules-in-xquery) </span><span class="sxs-lookup"><span data-stu-id="c9d00-154">[Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery) </span></span>  
 [<span data-ttu-id="c9d00-155">CAST y CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c9d00-155">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
