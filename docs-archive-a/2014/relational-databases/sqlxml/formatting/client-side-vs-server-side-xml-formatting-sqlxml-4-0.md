---
title: Formato XML del lado cliente y de servidor (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- FOR XML clause, formatting
- client-side XML formatting
- server-side XPath
- server-side XML formatting
- AUTO mode
- client-side XPath
ms.assetid: f807ab7a-c5f8-4e61-9b00-23aebfabc47e
author: rothja
ms.author: jroth
ms.openlocfilehash: fa155fc6d346cb90de54e5599aca1c296623faa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674706"
---
# <a name="client-side-vs-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="8e742-102">Lado cliente y Aplicación de formato XML en el servidor (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="8e742-102">Client-side vs. Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="8e742-103">En este tema se describen las diferencias generales que existen entre la aplicación de formato XML del lado cliente y del lado servidor en SQLXML.</span><span class="sxs-lookup"><span data-stu-id="8e742-103">This topic describes the general differences between client-side and server-side XML formatting in SQLXML.</span></span>  
  
## <a name="multiple-rowset-queries-not-supported-in-client-side-formatting"></a><span data-ttu-id="8e742-104">En el formato del cliente, no se admiten consultas de varios conjuntos de filas</span><span class="sxs-lookup"><span data-stu-id="8e742-104">Multiple Rowset Queries Not Supported in Client-side Formatting</span></span>  
 <span data-ttu-id="8e742-105">Cuando la aplicación de formato XML es del lado cliente, no se admiten consultas que generen varios conjuntos de filas.</span><span class="sxs-lookup"><span data-stu-id="8e742-105">Queries that generate multiple rowsets are not supported when you use client-side XML formatting.</span></span> <span data-ttu-id="8e742-106">Supongamos, por ejemplo, que tiene un directorio virtual en el que ha especificado que la aplicación formato se realice del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="8e742-106">For example, assume you have a virtual directory in which you have client-side formatting specified.</span></span> <span data-ttu-id="8e742-107">Considere esta plantilla de ejemplo, que tiene dos instrucciones SELECT en un **\<sql:query>** bloque:</span><span class="sxs-lookup"><span data-stu-id="8e742-107">Consider this sample template, which has two SELECT statements in a **\<sql:query>** block:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
     SELECT FirstName FROM Person.Contact FOR XML Nested;   
     SELECT LastName FROM Person.Contact FOR XML Nested    
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-108">Si ejecuta esta plantilla en el código de la aplicación, se devolverá un error, puesto que el formato XML del lado cliente no admite el formato de varios conjuntos de filas.</span><span class="sxs-lookup"><span data-stu-id="8e742-108">You can execute this template in application code and an error is returned, because client-side XML formatting does not support formatting of multiple rowsets.</span></span> <span data-ttu-id="8e742-109">Si especifica las consultas en dos bloques independientes **\<sql:query>** , obtendrá los resultados deseados.</span><span class="sxs-lookup"><span data-stu-id="8e742-109">If you specify the queries in two separate **\<sql:query>** blocks, you will get the desired results.</span></span>  
  
## <a name="timestamp-maps-differently-in-client--vs-server-side-formatting"></a><span data-ttu-id="8e742-110">timestamp se asigna de distinto modo cuando la aplicación de formato se realiza en el cliente o en el servidor</span><span class="sxs-lookup"><span data-stu-id="8e742-110">timestamp Maps Differently in Client- vs. Server-side Formatting</span></span>  
 <span data-ttu-id="8e742-111">Cuando la aplicación de formato XML se realiza en el servidor, la columna de base de datos de tipo `timestamp` se asigna al tipo XDR i8 (cuando se ha especificado en la consulta la opción XMLDATA).</span><span class="sxs-lookup"><span data-stu-id="8e742-111">In server-side XML formatting, the database column of `timestamp` type maps to the i8 XDR type (when the XMLDATA option is specified in the query).</span></span>  
  
 <span data-ttu-id="8e742-112">Cuando la aplicación de formato XML se realiza del lado cliente, la columna de base de datos de tipo `timestamp` se asigna al tipo XDR `uri` o `bin.base64` (en función de si se ha especificado en la consulta la opción binary base64).</span><span class="sxs-lookup"><span data-stu-id="8e742-112">In client-side XML formatting, the database column of `timestamp` type maps to either the `uri` or the `bin.base64` XDR type (depending on whether the binary base64 option is specified in the query).</span></span> <span data-ttu-id="8e742-113">El `bin.base64` tipo XDR es útil si usa las características diagrama y de carga masiva, ya que este tipo se convierte al [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` tipo.</span><span class="sxs-lookup"><span data-stu-id="8e742-113">The `bin.base64` XDR type is useful if you use the updategram and bulkload features, because this type is converted to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` type.</span></span> <span data-ttu-id="8e742-114">De esta forma, las operaciones de inserción, actualización o eliminación se realizan correctamente.</span><span class="sxs-lookup"><span data-stu-id="8e742-114">This way, the insert, update, or delete operation succeeds.</span></span>  
  
## <a name="deep-variants-are-used-in-server-side-formatting"></a><span data-ttu-id="8e742-115">En el formato del servidor se usan tipos VARIANT profundos</span><span class="sxs-lookup"><span data-stu-id="8e742-115">Deep VARIANTs Are Used in Server-side Formatting</span></span>  
 <span data-ttu-id="8e742-116">En la aplicación de formato XML en el servidor, se usan los tipos profundos de un tipo VARIANT.</span><span class="sxs-lookup"><span data-stu-id="8e742-116">In server-side XML formatting, the deep types of a VARIANT type are used.</span></span> <span data-ttu-id="8e742-117">Si aplica el formato XML del lado cliente, los datos VARIANT se convierten en una cadena Unicode y no se usan los subtipos de VARIANT.</span><span class="sxs-lookup"><span data-stu-id="8e742-117">If you use client-side XML formatting, the variants are converted to Unicode string, and the subtypes of VARIANT are not used.</span></span>  
  
## <a name="nested-mode-vs-auto-mode"></a><span data-ttu-id="8e742-118">Diferencias entre el modo NESTED y el modo AUTO</span><span class="sxs-lookup"><span data-stu-id="8e742-118">NESTED Mode vs. AUTO Mode</span></span>  
 <span data-ttu-id="8e742-119">El modo NESTED de la instrucción FOR XML del lado cliente es similar al modo AUTO de la instrucción FOR XML del servidor, con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="8e742-119">The NESTED mode of the client-side FOR XML is similar to the AUTO mode of server-side FOR XML, with the following exceptions:</span></span>  
  
### <a name="when-you-query-views-using-auto-mode-on-the-server-side-the-view-name-is-returned-as-the-element-name-in-the-resulting-xml"></a><span data-ttu-id="8e742-120">Al consultar vistas utilizando el modo AUTO en el servidor, el nombre de la vista se devuelve como el nombre del elemento en el código XML resultante.</span><span class="sxs-lookup"><span data-stu-id="8e742-120">When you query views using AUTO mode on the server-side, the view name is returned as the element name in the resulting XML.</span></span>  
 <span data-ttu-id="8e742-121">Por ejemplo, suponga que se crea la vista siguiente en la tabla person. contact de AdventureWorksdatabase:</span><span class="sxs-lookup"><span data-stu-id="8e742-121">For example, assume that the following view is created on the Person.Contact table in the AdventureWorksdatabase:</span></span>  
  
```  
CREATE VIEW ContactView AS (SELECT ContactID as CID,  
                               FirstName  as FName,  
                               LastName  as LName  
                        FROM Person.Contact)  
```  
  
 <span data-ttu-id="8e742-122">La plantilla siguiente especifica una consulta en la vista ContactView y especifica también que la aplicación de formato XML se realice en el servidor:</span><span class="sxs-lookup"><span data-stu-id="8e742-122">The following template specifies a query against the ContactView view, and also specifies server-side XML formatting:</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT *  
    FROM   ContactView  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-123">Al ejecutar la plantilla, se devuelve el código XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="8e742-123">When you execute the template, the following XML is returned.</span></span> <span data-ttu-id="8e742-124">(Solo se muestran resultados parciales). Tenga en cuenta que los nombres de elemento son los nombres de las vistas en las que se ejecuta la consulta.</span><span class="sxs-lookup"><span data-stu-id="8e742-124">(Only partial results are shown.) Note that the element names are the names of the views against which the query is executed.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ContactView CID="1" FName="Gustavo" LName="Achong" />   
  <ContactView CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-125">Al especificar el formato XML del lado cliente utilizando el modo NESTED correspondiente, los nombres de la tabla base se devuelven como los nombres de elemento en el código XML resultante.</span><span class="sxs-lookup"><span data-stu-id="8e742-125">When you specify client-side XML formatting by using the corresponding NESTED mode, the base table name(s) are returned as the element name(s) in the resulting XML.</span></span> <span data-ttu-id="8e742-126">Por ejemplo, la siguiente plantilla revisada ejecuta la misma instrucción SELECT, pero el formato XML se realiza en el lado cliente (es decir, **Client-Side-XML** se establece en true en la plantilla):</span><span class="sxs-lookup"><span data-stu-id="8e742-126">For example, the following revised template executes the same SELECT statement, but the XML formatting is performed on the client-side (that is, **client-side-xml** is set to true in the template):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT *  
    FROM   ContactView  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-127">Al ejecutar esta plantilla, se genera el código XML siguiente.</span><span class="sxs-lookup"><span data-stu-id="8e742-127">Executing this template produces the following XML.</span></span> <span data-ttu-id="8e742-128">Observe que, en este caso, el nombre del elemento es el nombre de la tabla base.</span><span class="sxs-lookup"><span data-stu-id="8e742-128">Note that the element name is the base table name in this case.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact CID="1" FName="Gustavo" LName="Achong" />   
  <Person.Contact CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
### <a name="when-you-use-auto-mode-of-the-server-side-for-xml-the-table-aliases-specified-in-the-query-are-returned-as-element-names-in-the-resulting-xml"></a><span data-ttu-id="8e742-129">Cuando se utiliza el modo AUTO de la instrucción FOR XML del servidor, los alias de tabla especificados en la consulta se devuelven como nombres de elemento en el código XML resultante.</span><span class="sxs-lookup"><span data-stu-id="8e742-129">When you use AUTO mode of the server-side FOR XML, the table aliases specified in the query are returned as element names in the resulting XML.</span></span>  
 <span data-ttu-id="8e742-130">Por ejemplo, fíjese en esta plantilla:</span><span class="sxs-lookup"><span data-stu-id="8e742-130">For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-131">Al ejecutar la plantilla, se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e742-131">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <C fname="Gustavo" lname="Achong" />   
  <C fname="Catherine" lname="Abel" />   
...  
</ROOT>   
```  
  
 <span data-ttu-id="8e742-132">Cuando se utiliza el modo NESTED de la instrucción FOR XML del lado cliente, los nombres de tabla se devuelven como nombres de elemento en el código XML resultante.</span><span class="sxs-lookup"><span data-stu-id="8e742-132">When you use the NESTED mode of the client-side FOR XML, the table names are returned as element names in the resulting XML.</span></span> <span data-ttu-id="8e742-133">(No se utilizan los alias de tabla especificados en la consulta). Por ejemplo, considere esta plantilla:</span><span class="sxs-lookup"><span data-stu-id="8e742-133">(Table aliases that are specified in the query are not used.) For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-134">Al ejecutar la plantilla, se genera el código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="8e742-134">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact fname="Gustavo" lname="Achong" />   
  <Person.Contact fname="Catherine" lname="Abel" />   
...  
</ROOT>  
```  
  
### <a name="if-you-have-a-query-that-returns-columns-as-dbobject-queries-you-cannot-use-aliases-for-these-columns"></a><span data-ttu-id="8e742-135">Si tiene una consulta que devuelve las columnas como consultas dbobject, no puede utilizar alias para estas columnas.</span><span class="sxs-lookup"><span data-stu-id="8e742-135">If you have a query that returns columns as dbobject queries, you cannot use aliases for these columns.</span></span>  
 <span data-ttu-id="8e742-136">Por ejemplo, fíjese en la plantilla siguiente, que ejecuta una consulta que devuelve un identificador de empleado y una foto.</span><span class="sxs-lookup"><span data-stu-id="8e742-136">For example, consider the following template, which executes a query that returns an employee ID and a photo.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query client-side-xml="1">  
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML NESTED, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-137">Al ejecutar esta plantilla, la columna Photo se devuelve como una consulta dbobject.</span><span class="sxs-lookup"><span data-stu-id="8e742-137">Executing this template returns the Photo column as a dbobject query.</span></span> <span data-ttu-id="8e742-138">En esta consulta dbobject, `@P` hace referencia a un nombre de columna que no existe.</span><span class="sxs-lookup"><span data-stu-id="8e742-138">In this dbobject query, `@P` refers to a column name that does not exist.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@P</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-139">Si el formato XML se realiza en el servidor (**Client-Side-XML = "0"**), puede usar el alias para las columnas que devuelven las consultas dbobject en las que se devuelven los nombres reales de las tablas y columnas (aunque se hayan especificado alias).</span><span class="sxs-lookup"><span data-stu-id="8e742-139">If the XML formatting is done on the server (**client-side-xml="0"**), you can use the alias for the columns that return dbobject queries in which actual table and column names are returned (even if you have aliases specified).</span></span> <span data-ttu-id="8e742-140">Por ejemplo, la siguiente plantilla ejecuta una consulta y el formato XML se realiza en el servidor (no se especifica la opción **Client-Side-XML** y la opción **ejecutar en el cliente** no está seleccionada para la raíz virtual).</span><span class="sxs-lookup"><span data-stu-id="8e742-140">For example, the following template executes a query, and the XML formatting is done on the server (the **client-side-xml** option is not specified and the **Run On Client** option is not selected for the virtual root).</span></span> <span data-ttu-id="8e742-141">La consulta especifica también el modo AUTO (no el modo NESTED del lado cliente).</span><span class="sxs-lookup"><span data-stu-id="8e742-141">The query also specifies AUTO mode (not the client-side NESTED mode).</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query   
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML AUTO, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="8e742-142">Cuando se ejecuta esta plantilla, se devuelve el documento XML siguiente (observe que no se utilizan alias en la consulta dbobject para la columna LargePhoto):</span><span class="sxs-lookup"><span data-stu-id="8e742-142">When this template is executed, the following XML document is returned (note that aliases are not used in the dbobject query for the LargePhoto column):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@LargePhoto</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
### <a name="client-side-vs-server-side-xpath"></a><span data-ttu-id="8e742-143">Diferencias entre XPath en el cliente y en el servidor</span><span class="sxs-lookup"><span data-stu-id="8e742-143">Client-side vs. Server-side XPath</span></span>  
 <span data-ttu-id="8e742-144">No existen diferencias de funcionamiento entre XPath en el cliente y en el servidor, con las siguientes salvedades:</span><span class="sxs-lookup"><span data-stu-id="8e742-144">Client-side XPath and server-side XPath work the same except for these differences:</span></span>  
  
-   <span data-ttu-id="8e742-145">Las conversiones de datos que se aplican al utilizar consultas XPath del lado cliente son diferentes de las que se aplican cuando se utilizan consultas XPath en el servidor.</span><span class="sxs-lookup"><span data-stu-id="8e742-145">The data conversions that are applied when you use client-side XPath queries are different from those that are applied when you use server-side XPath queries.</span></span> <span data-ttu-id="8e742-146">XPath en el cliente utiliza CAST en lugar de CONVERT mode 126.</span><span class="sxs-lookup"><span data-stu-id="8e742-146">Client-side XPath uses CAST instead of CONVERT mode 126.</span></span>  
  
-   <span data-ttu-id="8e742-147">Cuando se especifica **Client-Side-XML = "0"** (false) en una plantilla, se solicita el formato XML del lado servidor.</span><span class="sxs-lookup"><span data-stu-id="8e742-147">When you specify **client-side-xml="0"** (false) in a template, you are requesting server-side XML formatting.</span></span> <span data-ttu-id="8e742-148">Por lo tanto, no es posible especificar FOR XML NESTED porque el servidor no reconoce la opción NESTED.</span><span class="sxs-lookup"><span data-stu-id="8e742-148">Therefore, you cannot specify FOR XML NESTED because the server does not recognize the NESTED option.</span></span> <span data-ttu-id="8e742-149">Esto genera un error.</span><span class="sxs-lookup"><span data-stu-id="8e742-149">This generates an error.</span></span> <span data-ttu-id="8e742-150">Deben utilizarse los modos AUTO, RAW o EXPLICIT, que el servidor sí que reconoce.</span><span class="sxs-lookup"><span data-stu-id="8e742-150">You must use the AUTO, RAW, or EXPLICIT modes, which the server does recognize.</span></span>  
  
-   <span data-ttu-id="8e742-151">Cuando se especifica **Client-Side-XML = "1"** (true) en una plantilla, se solicita el formato XML del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="8e742-151">When you specify **client-side-xml="1"** (true) in a template, you are requesting client-side XML formatting.</span></span> <span data-ttu-id="8e742-152">En este caso, puede especificarse FOR XML NESTED.</span><span class="sxs-lookup"><span data-stu-id="8e742-152">In this case, you can specify FOR XML NESTED.</span></span> <span data-ttu-id="8e742-153">Si especifica FOR XML AUTO, el formato XML se produce en el lado servidor, aunque se especifica **Client-Side-XML = "1"** en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8e742-153">If you specify FOR XML AUTO, the XML formatting occurs on the server side although **client-side-xml="1"** is specified in the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e742-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e742-154">See Also</span></span>  
 <span data-ttu-id="8e742-155">[Consideraciones de seguridad de FOR XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="8e742-155">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="8e742-156">[Formato XML del lado cliente &#40;SQLXML 4,0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="8e742-156">[Client-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="8e742-157">Formato XML del lado servidor &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="8e742-157">Server-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](server-side-xml-formatting-sqlxml-4-0.md)  
  
  
