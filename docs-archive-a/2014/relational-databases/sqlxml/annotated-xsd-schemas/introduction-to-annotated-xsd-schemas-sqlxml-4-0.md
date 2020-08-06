---
title: Introducción a los esquemas XSD anotados (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- mapping schema [SQLXML], about mapping schema
- views [SQLXML]
- valid XSD schemas [SQLXML]
- annotations [SQLXML]
- XSD schemas [SQLXML], creating XML views
- annotated XSD schemas, creating XML views
- minimum XSD schema
- annotated XSD schemas, examples
- XML views [SQLXML]
ms.assetid: 15282db1-65c4-43be-bdb7-e9ef49cb33a2
author: rothja
ms.author: jroth
ms.openlocfilehash: b91be71569daa9e5bf4143be9f652617ba7c5b01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674715"
---
# <a name="introduction-to-annotated-xsd-schemas-sqlxml-40"></a><span data-ttu-id="9181f-102">Introducción a los esquemas XSD anotados (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="9181f-102">Introduction to Annotated XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="9181f-103">Puede crear vistas XML de datos relacionales utilizando el lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="9181f-103">You can create XML views of relational data by using the XML Schema Definition (XSD) language.</span></span> <span data-ttu-id="9181f-104">Estas vistas pueden consultarse después utilizando consultas XPath (Lenguaje de rutas XML).</span><span class="sxs-lookup"><span data-stu-id="9181f-104">These views can then be queried by using XML Path language (XPath) queries.</span></span> <span data-ttu-id="9181f-105">Es parecido a crear vistas utilizando instrucciones CREATE VIEW y, a continuación, especificar consultas SQL en la vista.</span><span class="sxs-lookup"><span data-stu-id="9181f-105">This is similar to creating views by using CREATE VIEW statements and then specifying SQL queries against the view.</span></span>  
  
 <span data-ttu-id="9181f-106">Un esquema XML describe la estructura de un documento XML y también describe las distintas restricciones en los datos del documento.</span><span class="sxs-lookup"><span data-stu-id="9181f-106">An XML schema describes the structure of an XML document and also describes the various constraints on the data in the document.</span></span> <span data-ttu-id="9181f-107">Cuando se especifican consultas XPath en el esquema, la estructura del documento XML devuelto viene determinada por el esquema en el que se ejecuta la consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="9181f-107">When you specify XPath queries against the schema, the structure of the XML document returned is determined by the schema against which the XPath query is executed.</span></span>  
  
 <span data-ttu-id="9181f-108">En un esquema XSD, el **\<xsd:schema>** elemento incluye todo el esquema; todas las declaraciones de elementos deben estar dentro del **\<xsd:schema>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9181f-108">In an XSD schema, the **\<xsd:schema>** element encloses the entire schema; all element declarations must be contained within the **\<xsd:schema>** element.</span></span> <span data-ttu-id="9181f-109">Puede describir los atributos que definen el espacio de nombres en el que reside el esquema y los espacios de nombres que se usan en el esquema como propiedades del **\<xsd:schema>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9181f-109">You can describe attributes that define the namespace in which the schema resides and the namespaces that are used in the schema as properties of the **\<xsd:schema>** element.</span></span>  
  
 <span data-ttu-id="9181f-110">Un esquema XSD válido debe contener el **\<xsd:schema>** elemento definido como se indica A continuación:</span><span class="sxs-lookup"><span data-stu-id="9181f-110">A valid XSD schema must contain the **\<xsd:schema>** element defined as follows:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<!-- additional schema definitions here -->  
</xsd:schema>  
```  
  
 <span data-ttu-id="9181f-111">El **\<xsd:schema>** elemento se deriva de la especificación del espacio de nombres del esquema XML en http://www.w3.org/2001/XMLSchema .</span><span class="sxs-lookup"><span data-stu-id="9181f-111">The **\<xsd:schema>** element is derived from the XML Schema namespace specification at http://www.w3.org/2001/XMLSchema.</span></span>  
  
## <a name="annotations-to-the-xsd-schema"></a><span data-ttu-id="9181f-112">Anotaciones en el esquema XSD</span><span class="sxs-lookup"><span data-stu-id="9181f-112">Annotations to the XSD Schema</span></span>  
 <span data-ttu-id="9181f-113">Puede usar un esquema XSD con anotaciones que describan la asignación a una base de datos, consultar la base de datos y devolver los resultados en forma de documento XML.</span><span class="sxs-lookup"><span data-stu-id="9181f-113">You can use an XSD schema with annotations that describe the mapping to a database, query the database, and return the results in the form of an XML document.</span></span> <span data-ttu-id="9181f-114">Las anotaciones se proporcionan para asignar un esquema XSD a las tablas y columnas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="9181f-114">Annotations are provided to map an XSD schema to database tables and columns.</span></span> <span data-ttu-id="9181f-115">Pueden especificarse consultas XPath en la vista XML creada por el esquema XSD para consultar la base de datos y obtener los resultados en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="9181f-115">XPath queries can be specified against the XML view created by the XSD schema to query the database and obtain results as an XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9181f-116">En [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, el lenguaje de esquemas XSD admite las anotaciones introducidas por el lenguaje de esquemas reducidos de datos XML (XDR) anotados de [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9181f-116">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports the annotations introduced with annotated XML-Data Reduced (XDR) schema language in [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="9181f-117">Los esquemas XDR anotados han quedado desusados en SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="9181f-117">Annotated XDR is deprecated in SQLXML 4.0.</span></span>  
  
 <span data-ttu-id="9181f-118">En el contexto de la base de datos relacional, resulta de gran utilidad para asignar el esquema XSD arbitrario a un almacén relacional.</span><span class="sxs-lookup"><span data-stu-id="9181f-118">In the context of the relational database, it is useful to map the arbitrary XSD schema to a relational store.</span></span> <span data-ttu-id="9181f-119">Una forma de conseguirlo es anotar el esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="9181f-119">One way to achieve this is to annotate the XSD schema.</span></span> <span data-ttu-id="9181f-120">Un esquema XSD con anotaciones se conoce como *esquema de asignación*, que proporciona información relativa al modo en que se asignan los datos XML al almacén relacional.</span><span class="sxs-lookup"><span data-stu-id="9181f-120">An XSD schema with the annotations is referred to as a *mapping schema*, which provides information pertaining to how XML data is to be mapped to the relational store.</span></span> <span data-ttu-id="9181f-121">Un esquema de asignación es realmente una vista XML de los datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="9181f-121">A mapping schema is, in effect, an XML view of the relational data.</span></span> <span data-ttu-id="9181f-122">Estas asignaciones pueden usarse para recuperar los datos relacionales como un documento XML.</span><span class="sxs-lookup"><span data-stu-id="9181f-122">These mappings can be used to retrieve relational data as an XML document.</span></span>  
  
## <a name="namespace-for-annotations"></a><span data-ttu-id="9181f-123">Espacio de nombres para las anotaciones</span><span class="sxs-lookup"><span data-stu-id="9181f-123">Namespace for Annotations</span></span>  
 <span data-ttu-id="9181f-124">En un esquema XSD, las anotaciones se especifican mediante el espacio de nombres **urn: schemas-microsoft-com: mapping-schema**.</span><span class="sxs-lookup"><span data-stu-id="9181f-124">In an XSD schema, annotations are specified by using the namespace **urn:schemas-microsoft-com:mapping-schema**.</span></span> <span data-ttu-id="9181f-125">Como se muestra en el ejemplo siguiente, la manera más fácil de especificar el espacio de nombres es especificarlo en la **\<xsd:schema>** etiqueta.</span><span class="sxs-lookup"><span data-stu-id="9181f-125">As shown in the following example, the easiest way to specify the namespace is to specify it in the **\<xsd:schema>** tag.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
...  
</xsd:schema>  
```  
  
 <span data-ttu-id="9181f-126">Se utiliza un prefijo de espacio de nombres arbitrario.</span><span class="sxs-lookup"><span data-stu-id="9181f-126">The namespace prefix that is used is arbitrary.</span></span> <span data-ttu-id="9181f-127">En esta documentación, el prefijo **SQL** se utiliza para denotar el espacio de nombres de la anotación y distinguir las anotaciones de este espacio de nombres de las de otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="9181f-127">In this documentation, the **sql** prefix is used to denote the annotation namespace and to distinguish annotations in this namespace from those in other namespaces.</span></span>  
  
## <a name="example-of-an-annotated-xsd-schema"></a><span data-ttu-id="9181f-128">Ejemplo de un esquema XSD anotado</span><span class="sxs-lookup"><span data-stu-id="9181f-128">Example of an Annotated XSD Schema</span></span>  
 <span data-ttu-id="9181f-129">En el ejemplo siguiente, el esquema XSD está compuesto de un **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9181f-129">In the following example, the XSD schema consists of an **\<Person.Contact>** element.</span></span> <span data-ttu-id="9181f-130">El **\<Employee>** elemento tiene un atributo **ContactID** y **\<FirstName>** **\<LastName>** los elementos secundarios y:</span><span class="sxs-lookup"><span data-stu-id="9181f-130">The **\<Employee>** element has a **ContactID** attribute and **\<FirstName>** and **\<LastName>** child elements:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <xsd:element name="Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"    
                     type="xsd:string" />   
        <xsd:element name="LName"  
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID" type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="9181f-131">Se han agregado anotaciones a este esquema XSD para asignar sus elementos y atributos a las tablas y columnas de base de datos:</span><span class="sxs-lookup"><span data-stu-id="9181f-131">Annotations are added to this XSD schema to map its elements and attributes to the database tables and columns:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID"   
                       sql:field="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="9181f-132">En el esquema de asignación, el **\<Contact>** elemento se asigna a la tabla person. contact de la base de datos de ejemplo AdventureWorks mediante la `sql:relation` anotación.</span><span class="sxs-lookup"><span data-stu-id="9181f-132">In the mapping schema, the **\<Contact>** element is mapped to the Person.Contact table in the sample AdventureWorks database by using the `sql:relation` annotation.</span></span> <span data-ttu-id="9181f-133">Los atributos ConID, FName y LName se asignan a las columnas ContactID, FirstName y LastName de la tabla Person.Contact mediante las anotaciones `sql:field`.</span><span class="sxs-lookup"><span data-stu-id="9181f-133">The attributes ConID, FName, and LName are mapped to the ContactID, FirstName, and LastName columns in the Person.Contact table by using the `sql:field` annotations.</span></span>  
  
 <span data-ttu-id="9181f-134">Este esquema XSD anotado proporciona la vista XML de los datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="9181f-134">This annotated XSD schema provides the XML view of the relational data.</span></span> <span data-ttu-id="9181f-135">Esta vista XML puede consultarse utilizando el lenguaje XPath.</span><span class="sxs-lookup"><span data-stu-id="9181f-135">This XML view can be queried using the XPath language.</span></span> <span data-ttu-id="9181f-136">Una consulta XPath devuelve como resultado un documento XML en lugar del conjunto de filas que devuelven las consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="9181f-136">An XPath query returns an XML document as a result, instead of the rowset that is returned by SQL queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9181f-137">En el esquema de asignación, la distinción de mayúsculas y minúsculas para los valores relacionales especificados (como el nombre de tabla y el nombre de columna) depende de que SQL Server utilice la configuración de intercalación con distinción de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9181f-137">In the mapping schema, case-sensitivity for the specified relational values (such as table name and column name) depends upon if SQL Server is using case-sensitive collation settings.</span></span> <span data-ttu-id="9181f-138">Para más información, consulte [Compatibilidad con la intercalación y Unicode](../../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="9181f-138">For more information, see [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="9181f-139">Otros recursos</span><span class="sxs-lookup"><span data-stu-id="9181f-139">Other Resources</span></span>  
 <span data-ttu-id="9181f-140">Puede buscar más información sobre el lenguaje de definición de esquemas XML (XSD), el lenguaje de rutas XML (XPath) y el lenguaje de transformación basado en hojas de estilo (XSLT) en los siguientes sitios web:</span><span class="sxs-lookup"><span data-stu-id="9181f-140">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="9181f-141">XML Schema Part 0: manual, recomendación de W3C (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="9181f-141">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="9181f-142">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="9181f-142">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="9181f-143">Esquema XML parte 2: tipos de archivo, recomendación de W3C (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="9181f-143">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="9181f-144">Lenguaje de rutas XML (XPath) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="9181f-144">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="9181f-145">Transformaciones XSL (XSLT) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="9181f-145">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9181f-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9181f-146">See Also</span></span>  
 <span data-ttu-id="9181f-147">[Consideraciones sobre la seguridad del esquema anotado &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="9181f-147">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="9181f-148">Los esquemas XDR anotados &#40;han quedado en desuso en SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9181f-148">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
  
  
