---
title: Sintaxis básica de la cláusula FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- BINARY BASE64 directive
- ROOT directive
- FOR XML clause, BINARY BASE64 directive
- FOR XML clause, syntax
- FOR XML clause, ROOT directive
ms.assetid: df19ecbf-d28e-4e9c-aaa3-700f8bbd3be4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc0410e7a54674673f64442d8a3cf9476d250033
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662713"
---
# <a name="basic-syntax-of-the-for-xml-clause"></a><span data-ttu-id="73c36-102">Sintaxis básica de la cláusula FOR XML</span><span class="sxs-lookup"><span data-stu-id="73c36-102">Basic Syntax of the FOR XML Clause</span></span>
  <span data-ttu-id="73c36-103">El modo de FOR XML puede ser RAW, AUTO, EXPLICIT o PATH.</span><span class="sxs-lookup"><span data-stu-id="73c36-103">The FOR XML mode can be RAW, AUTO, EXPLICIT, or PATH.</span></span> <span data-ttu-id="73c36-104">Determina la forma del XML resultante.</span><span class="sxs-lookup"><span data-stu-id="73c36-104">It determines the shape of the resulting XML.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="73c36-105">La directiva XMLDATA para la opción FOR XML ha quedado desusada.</span><span class="sxs-lookup"><span data-stu-id="73c36-105">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="73c36-106">Utilice la XSD generación en los modos RAW y AUTO.</span><span class="sxs-lookup"><span data-stu-id="73c36-106">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="73c36-107">No hay sustitución para la directiva XMLDATA en modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="73c36-107">There is no replacement for the XMLDATA directive in EXPLICT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="73c36-108">A continuación se indica la sintaxis básica que se describe en la [cláusula for (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span><span class="sxs-lookup"><span data-stu-id="73c36-108">Following is the basic syntax that is described in [FOR Clause (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span></span>  
  
```  
[ FOR { BROWSE | <XML> } ]  
<XML> ::=  
XML   
    {   
      { RAW [ ('ElementName') ] | AUTO }   
        [   
           <CommonDirectives>   
           [ , { XMLDATA | XMLSCHEMA [ ('TargetNameSpaceURI') ]} ]   
           [ , ELEMENTS [ XSINIL | ABSENT ]   
        ]  
      | EXPLICIT   
        [   
           <CommonDirectives>   
           [ , XMLDATA ]   
        ]  
      | PATH [ ('ElementName') ]   
        [   
           <CommonDirectives>   
           [ , ELEMENTS [ XSINIL | ABSENT ] ]  
        ]  
     }   
  
 <CommonDirectives> ::=   
   [ , BINARY BASE64 ]  
   [ , TYPE ]  
   [ , ROOT [ ('RootName') ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="73c36-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="73c36-109">Arguments</span></span>  
 <span data-ttu-id="73c36-110">RAW[('*ElementName*')]</span><span class="sxs-lookup"><span data-stu-id="73c36-110">RAW[('*ElementName*')]</span></span>  
 <span data-ttu-id="73c36-111">Obtiene el resultado de la consulta y transforma cada fila del conjunto de resultados en un elemento XML con un identificador genérico, \<row />, como etiqueta del elemento.</span><span class="sxs-lookup"><span data-stu-id="73c36-111">Takes the query result and transforms each row in the result set into an XML element that has a generic identifier, \<row />, as the element tag.</span></span> <span data-ttu-id="73c36-112">Opcionalmente, puede especificar un nombre para el elemento de fila cuando se utiliza esta directiva.</span><span class="sxs-lookup"><span data-stu-id="73c36-112">You can optionally specify a name for the row element when you use this directive.</span></span> <span data-ttu-id="73c36-113">El XML resultante utilizará el *ElementName* especificado como el elemento de fila generado para cada fila.</span><span class="sxs-lookup"><span data-stu-id="73c36-113">The resulting XML will use the specified *ElementName* as the row element generated for each row.</span></span> <span data-ttu-id="73c36-114">Para obtener más información, vea [Usar el modo RAW con FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-114">For more information, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="73c36-115">AUTO</span><span class="sxs-lookup"><span data-stu-id="73c36-115">AUTO</span></span>  
 <span data-ttu-id="73c36-116">Devuelve los resultados de la consulta en un árbol anidado XML sencillo.</span><span class="sxs-lookup"><span data-stu-id="73c36-116">Returns query results in a simple, nested XML tree.</span></span> <span data-ttu-id="73c36-117">Cada tabla en la cláusula FROM de la que al menos se presenta una columna en la cláusula SELECT se representa como un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="73c36-117">Each table in the FROM clause for which at least one column is listed in the SELECT clause is represented as an XML element.</span></span> <span data-ttu-id="73c36-118">A las columnas presentadas en la cláusula SELECT se les asignan los atributos de elemento apropiados.</span><span class="sxs-lookup"><span data-stu-id="73c36-118">The columns listed in the SELECT clause are mapped to the appropriate element attributes.</span></span> <span data-ttu-id="73c36-119">Para obtener más información, vea [Usar el modo AUTO con FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-119">For more information, see [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="73c36-120">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="73c36-120">EXPLICIT</span></span>  
 <span data-ttu-id="73c36-121">Especifica que la forma del árbol XML resultante está definida explícitamente.</span><span class="sxs-lookup"><span data-stu-id="73c36-121">Specifies that the shape of the resulting XML tree is defined explicitly.</span></span> <span data-ttu-id="73c36-122">Con este modo, es necesario escribir las consultas de una cierta manera, de modo que se pueda especificar explícitamente información adicional acerca de la anidación deseada.</span><span class="sxs-lookup"><span data-stu-id="73c36-122">By using this mode, queries must be written in a particular way so additional information about the nesting you want is specified explicitly.</span></span> <span data-ttu-id="73c36-123">Para obtener más información, vea [Usar el modo EXPLICIT con FOR XML](use-explicit-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-123">For more information, see [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="73c36-124">PATH</span><span class="sxs-lookup"><span data-stu-id="73c36-124">PATH</span></span>  
 <span data-ttu-id="73c36-125">Facilita la mezcla de elementos y atributos, así como la especificación de anidación adicional para representar propiedades complejas.</span><span class="sxs-lookup"><span data-stu-id="73c36-125">Provides a simpler way to mix elements and attributes, and to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="73c36-126">Puede utilizar consultas FOR XML de modo EXPLICIT para construir XML a partir de un conjunto de filas, pero el modo PATH supone una alternativa más simple a las consultas de modo EXPLICIT potencialmente complicadas.</span><span class="sxs-lookup"><span data-stu-id="73c36-126">You can use FOR XML EXPLICIT mode queries to construct this kind of XML from a rowset, but the PATH mode provides a simpler alternative to the possibly cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="73c36-127">El modo PATH, junto con la posibilidad de escribir consultas FOR XML anidadas y la directiva TYPE para devolver instancias de tipo **xml** , permite escribir consultas de forma más fácil.</span><span class="sxs-lookup"><span data-stu-id="73c36-127">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span> <span data-ttu-id="73c36-128">Ofrece una alternativa para escribir la mayoría de las consultas de modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="73c36-128">It provides an alternative to writing most EXPLICIT mode queries.</span></span> <span data-ttu-id="73c36-129">El modo PATH genera un contenedor de elementos \<row> de forma predeterminada por cada fila del conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="73c36-129">By default, PATH mode generates a \<row> element wrapper for each row in the result set.</span></span> <span data-ttu-id="73c36-130">También se puede especificar un nombre de elemento.</span><span class="sxs-lookup"><span data-stu-id="73c36-130">You can optionally specify an element name.</span></span> <span data-ttu-id="73c36-131">En este caso, el nombre especificado se utilizará como nombre del elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="73c36-131">If you do, the specified name is used as the wrapper element name.</span></span> <span data-ttu-id="73c36-132">Si se proporciona una cadena vacía (FOR XML PATH ('')), no se generará ningún elemento contenedor.</span><span class="sxs-lookup"><span data-stu-id="73c36-132">If you provide an empty string (FOR XML PATH ('')), no wrapper element is generated.</span></span> <span data-ttu-id="73c36-133">Para obtener más información, vea [Usar el modo PATH con FOR XML](use-path-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-133">For more information, see [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="73c36-134">XMLDATA</span><span class="sxs-lookup"><span data-stu-id="73c36-134">XMLDATA</span></span>  
 <span data-ttu-id="73c36-135">Especifica que se debe devolver un esquema XDR (XML-Data Reduced) insertado.</span><span class="sxs-lookup"><span data-stu-id="73c36-135">Specifies that an inline XML-Data Reduced (XDR) schema should be returned.</span></span> <span data-ttu-id="73c36-136">El esquema se antepone al documento como un esquema insertado.</span><span class="sxs-lookup"><span data-stu-id="73c36-136">The schema is prepended to the document as an inline schema.</span></span> <span data-ttu-id="73c36-137">Para obtener un ejemplo práctico, vea [Usar el modo RAW con FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-137">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="73c36-138">XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="73c36-138">XMLSCHEMA</span></span>  
 <span data-ttu-id="73c36-139">Devuelve un esquema XML W3C (XSD) insertado.</span><span class="sxs-lookup"><span data-stu-id="73c36-139">Returns an inline W3C XML Schema (XSD).</span></span> <span data-ttu-id="73c36-140">Opcionalmente, puede especificar un URI de espacio de nombres de destino al especificar esta directiva.</span><span class="sxs-lookup"><span data-stu-id="73c36-140">You can optionally specify a target namespace URI when specifying this directive.</span></span> <span data-ttu-id="73c36-141">De este modo, se devuelve el espacio de nombres especificado en el esquema.</span><span class="sxs-lookup"><span data-stu-id="73c36-141">This returns the specified namespace in the schema.</span></span> <span data-ttu-id="73c36-142">Para obtener más información, vea [Generar un esquema XSD insertado](generate-an-inline-xsd-schema.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-142">For more information, see [Generate an Inline XSD Schema](generate-an-inline-xsd-schema.md).</span></span> <span data-ttu-id="73c36-143">Para obtener un ejemplo práctico, vea [Usar el modo RAW con FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-143">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="73c36-144">ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="73c36-144">ELEMENTS</span></span>  
 <span data-ttu-id="73c36-145">Si se especifica la opción ELEMENTS, las columnas se devuelven como subelementos.</span><span class="sxs-lookup"><span data-stu-id="73c36-145">If the ELEMENTS option is specified, the columns are returned as subelements.</span></span> <span data-ttu-id="73c36-146">Sin embargo, se les asignan atributos XML.</span><span class="sxs-lookup"><span data-stu-id="73c36-146">Otherwise, they are mapped to XML attributes.</span></span> <span data-ttu-id="73c36-147">Esta opción solo se admite en los modos RAW, AUTO y PATH.</span><span class="sxs-lookup"><span data-stu-id="73c36-147">This option is supported in RAW, AUTO, and PATH modes only.</span></span> <span data-ttu-id="73c36-148">También puede especificar XSINIL o ABSENT cuando utilice esta directiva.</span><span class="sxs-lookup"><span data-stu-id="73c36-148">You can optionally specify XSINIL or ABSENT when you use this directive.</span></span> <span data-ttu-id="73c36-149">XSINIL especifica que se puede crear un elemento con un atributo **xsi:nil** establecido en True para los valores de columna NULL.</span><span class="sxs-lookup"><span data-stu-id="73c36-149">XSINIL specifies that an element that has an **xsi:nil** attribute set to True be created for NULL column values.</span></span> <span data-ttu-id="73c36-150">De forma predeterminada, o cuando se especifica ABSENT junto con ELEMENTS, no se crea ningún elemento para los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="73c36-150">By default or when ABSENT is specified together with ELEMENTS, no elements are created for NULL values.</span></span> <span data-ttu-id="73c36-151">Para obtener un ejemplo práctico, vea [Usar el modo RAW con FOR XML](use-raw-mode-with-for-xml.md) y [Usar el modo AUTO con FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-151">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) and [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="73c36-152">BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="73c36-152">BINARY BASE64</span></span>  
 <span data-ttu-id="73c36-153">Si se especifica la opción BINARY Base64, todos los datos binarios que devuelve la consulta se representan en formato codificado base64.</span><span class="sxs-lookup"><span data-stu-id="73c36-153">If the BINARY Base64 option is specified, any binary data returned by the query is represented in base64-encoded format.</span></span> <span data-ttu-id="73c36-154">Para recuperar datos binarios mediante el modo RAW y EXPLICIT, se debe especificar esta opción.</span><span class="sxs-lookup"><span data-stu-id="73c36-154">To retrieve binary data by using RAW and EXPLICIT mode, this option must be specified.</span></span> <span data-ttu-id="73c36-155">En modo AUTO, de forma predeterminada, se devuelven datos binarios como una referencia.</span><span class="sxs-lookup"><span data-stu-id="73c36-155">In AUTO mode, binary data is returned as a reference by default.</span></span> <span data-ttu-id="73c36-156">Para obtener un ejemplo práctico, vea [Usar el modo RAW con FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-156">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="73c36-157">TYPE</span><span class="sxs-lookup"><span data-stu-id="73c36-157">TYPE</span></span>  
 <span data-ttu-id="73c36-158">Especifica que la consulta devuelve los resultados como el tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="73c36-158">Specifies that the query returns the results as the **xml** type.</span></span> <span data-ttu-id="73c36-159">Para más información, consulte [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="73c36-159">For more information, see [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="73c36-160">ROOT [('*RootName*')]</span><span class="sxs-lookup"><span data-stu-id="73c36-160">ROOT [('*RootName*')]</span></span>  
 <span data-ttu-id="73c36-161">Especifica que se puede agregar un solo elemento de nivel superior al XML resultante.</span><span class="sxs-lookup"><span data-stu-id="73c36-161">Specifies that a single, top-level element be added to the resulting XML.</span></span> <span data-ttu-id="73c36-162">También se puede especificar el nombre del elemento raíz que se generará.</span><span class="sxs-lookup"><span data-stu-id="73c36-162">You can optionally specify the root element name to generate.</span></span> <span data-ttu-id="73c36-163">El valor predeterminado es "root".</span><span class="sxs-lookup"><span data-stu-id="73c36-163">The default value is "root".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c36-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73c36-164">See Also</span></span>  
 <span data-ttu-id="73c36-165">[Usar el modo RAW con FOR XML](use-raw-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="73c36-165">[Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="73c36-166">[Usar el modo AUTO con FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="73c36-166">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="73c36-167">[Usar el modo EXPLICIT con FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="73c36-167">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="73c36-168">[Usar el modo PATH con FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="73c36-168">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="73c36-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="73c36-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="73c36-170">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="73c36-170">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
