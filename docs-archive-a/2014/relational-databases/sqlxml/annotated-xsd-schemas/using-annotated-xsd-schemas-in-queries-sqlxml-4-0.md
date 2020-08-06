---
title: Usar esquemas XSD anotados en consultas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML]
- inline schemas [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- queries [SQLXML], annotated XSD schemas
- retrieving data
- mapping schema [SQLXML], queries
- multiple inline schemas
- annotated XSD schemas, queries
- XSD schemas [SQLXML], queries
- templates [SQLXML], annotated XSD schemas in queries
ms.assetid: 927a30a2-eae8-420d-851d-551c5f884f3c
author: rothja
ms.author: jroth
ms.openlocfilehash: c3038ea234f707da7a87a030cb4110510f5a77c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674718"
---
# <a name="using-annotated-xsd-schemas-in-queries-sqlxml-40"></a><span data-ttu-id="1a479-102">Usar esquemas XSD anotados en consultas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1a479-102">Using Annotated XSD Schemas in Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="1a479-103">Puede especificar consultas en un esquema anotado para recuperar datos de la base de datos especificando consultas XPath en una plantilla en el esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="1a479-103">You can specify queries against an annotated schema to retrieve data from the database by specifying XPath queries in a template against the XSD schema.</span></span>  
  
 <span data-ttu-id="1a479-104">El **\<sql:xpath-query>** elemento permite especificar una consulta XPath en la vista XML definida por el esquema anotado.</span><span class="sxs-lookup"><span data-stu-id="1a479-104">The **\<sql:xpath-query>** element allows you to specify an XPath query against the XML view that is defined by the annotated schema.</span></span> <span data-ttu-id="1a479-105">El esquema anotado en el que se va a ejecutar la consulta XPath se identifica mediante el `mapping-schema` atributo del **\<sql:xpath-query>** elemento.</span><span class="sxs-lookup"><span data-stu-id="1a479-105">The annotated schema against which the XPath query is to be executed is identified by using the `mapping-schema` attribute of the **\<sql:xpath-query>** element.</span></span>  
  
 <span data-ttu-id="1a479-106">Las plantillas son documentos XML válidos que contienen una o varias consultas.</span><span class="sxs-lookup"><span data-stu-id="1a479-106">Templates are valid XML documents that contain one or more queries.</span></span> <span data-ttu-id="1a479-107">Las consultas FOR XML y XPath devuelven un fragmento de documento.</span><span class="sxs-lookup"><span data-stu-id="1a479-107">The FOR XML and XPath queries return a document fragment.</span></span> <span data-ttu-id="1a479-108">Las plantillas actúan como contenedores para los fragmentos de documento; de esta forma, las plantillas proporcionan un modo de especificar un elemento único de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="1a479-108">Templates act as containers for the document fragments; templates thus provide a way to specify a single, top-level element.</span></span>  
  
 <span data-ttu-id="1a479-109">En los ejemplos de este tema se usan plantillas para especificar una consulta XPath en un esquema anotado con objeto de recuperar datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1a479-109">The examples in this topic use templates to specify an XPath query against an annotated schema to retrieve data from the database.</span></span>  
  
 <span data-ttu-id="1a479-110">Por ejemplo, fíjese este esquema anotado:</span><span class="sxs-lookup"><span data-stu-id="1a479-110">For example, consider this annotated schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID" type="xsd:string" />   
       <xsd:attribute name="FirstName" type="xsd:string" />   
       <xsd:attribute name="LastName"  type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="1a479-111">Con fines meramente ilustrativos, este esquema XSD se almacena en un archivo denominado Schema2.xml.</span><span class="sxs-lookup"><span data-stu-id="1a479-111">For the purpose of illustration, this XSD schema is stored in file named Schema2.xml.</span></span> <span data-ttu-id="1a479-112">A continuación, podría incluir una consulta XPath en el esquema anotado especificado en el siguiente archivo de plantilla (Schema2T.xml):</span><span class="sxs-lookup"><span data-stu-id="1a479-112">You could then have an XPath query against the annotated schema specified in the following template file (Schema2T.xml):</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql"  
     >  
          Person.Contact[@ContactID="1"]  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="1a479-113">Después, puede crear y usar el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la consulta como parte de un archivo de plantilla.</span><span class="sxs-lookup"><span data-stu-id="1a479-113">You can then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the query as part of a template file.</span></span> <span data-ttu-id="1a479-114">Para obtener más información, consulte [esquemas XDR anotados &#40;en desuso en SQLXML 4,0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="1a479-114">For more information, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="using-inline-mapping-schemas"></a><span data-ttu-id="1a479-115">Usar esquemas de asignación insertados</span><span class="sxs-lookup"><span data-stu-id="1a479-115">Using Inline Mapping Schemas</span></span>  
 <span data-ttu-id="1a479-116">Un esquema anotado puede incluirse directamente en una plantilla y, después, puede especificarse una consulta XPath en la plantilla en el esquema insertado.</span><span class="sxs-lookup"><span data-stu-id="1a479-116">An annotated schema can be included directly in a template, and then an XPath query can be specified in the template against the inline schema.</span></span> <span data-ttu-id="1a479-117">La plantilla también puede ser un diagrama de actualización.</span><span class="sxs-lookup"><span data-stu-id="1a479-117">The template can also be an updategram.</span></span>  
  
 <span data-ttu-id="1a479-118">Una plantilla puede incluir varios esquemas insertados.</span><span class="sxs-lookup"><span data-stu-id="1a479-118">A template can include multiple inline schemas.</span></span> <span data-ttu-id="1a479-119">Para usar un esquema insertado que esté incluido en una plantilla, especifique el atributo **ID** con un valor único en el **\<xsd:schema>** elemento y, a continuación, utilice **#idvalue** para hacer referencia al esquema en línea.</span><span class="sxs-lookup"><span data-stu-id="1a479-119">To use an inline schema that is included in a template, specify the **id** attribute with a unique value on the **\<xsd:schema>** element, and then use **#idvalue** to reference the inline schema.</span></span> <span data-ttu-id="1a479-120">El atributo **ID** es idéntico en comportamiento al **SQL: ID** ({urn: schemas-microsoft-com: XML-SQL} ID) que se usa en los esquemas XDR.</span><span class="sxs-lookup"><span data-stu-id="1a479-120">The **id** attribute is identical in behavior to the **sql:id** ({urn:schemas-microsoft-com:xml-sql}id) used in XDR schemas.</span></span>  
  
 <span data-ttu-id="1a479-121">Por ejemplo, la plantilla siguiente especifica dos esquemas anotados insertados:</span><span class="sxs-lookup"><span data-stu-id="1a479-121">For example, the following template specifies two inline-annotated schemas:</span></span>  
  
```  
<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'>  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema1' sql:is-mapping-schema='1'>  
  <xsd:element name='Employees' ms:relation='HumanResources.Employee'>  
    <xsd:complexType>  
      <xsd:attribute name='LoginID'   
                     type='xsd:string'/>  
      <xsd:attribute name='Title'   
                     type='xsd:string'/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema2' sql:is-mapping-schema='1'>  
  <xsd:element name='Contacts' ms:relation='Person.Contact'>  
    <xsd:complexType>  
  
      <xsd:attribute name='ContactID'   
                     type='xsd:string' />  
      <xsd:attribute name='FirstName'   
                     type='xsd:string' />  
      <xsd:attribute name='LastName'   
                     type='xsd:string' />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema1'>  
    /Employees[@LoginID='adventure-works\guy1']  
</sql:xpath-query>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema2'>  
    /Contacts[@ContactID='1']  
</sql:xpath-query>  
</ROOT>  
```  
  
 <span data-ttu-id="1a479-122">La plantilla también especifica dos consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="1a479-122">The template also specifies two XPath queries.</span></span> <span data-ttu-id="1a479-123">Cada uno de los **\<xpath-query>** elementos identifica de forma única el esquema de asignación especificando el `mapping-schema` atributo.</span><span class="sxs-lookup"><span data-stu-id="1a479-123">Each of the **\<xpath-query>** elements uniquely identifies the mapping schema by specifying the `mapping-schema` attribute.</span></span>  
  
 <span data-ttu-id="1a479-124">Cuando se especifica un esquema insertado en la plantilla, la `sql:is-mapping-schema` anotación también debe especificarse en el **\<xsd:schema>** elemento.</span><span class="sxs-lookup"><span data-stu-id="1a479-124">When you specify an inline schema in the template, the `sql:is-mapping-schema` annotation must also be specified on the **\<xsd:schema>** element.</span></span> <span data-ttu-id="1a479-125">`sql:is-mapping-schema` toma un valor booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="1a479-125">The `sql:is-mapping-schema` takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="1a479-126">Un esquema insertado con **SQL: is-mapping-schema = "1"** se trata como esquema anotado insertado y no se devuelve en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="1a479-126">An inline schema with **sql:is-mapping-schema="1"** is treated as inline annotated schema and is not returned in the XML document.</span></span>  
  
 <span data-ttu-id="1a479-127">La anotación `sql:is-mapping-schema` pertenece al espacio de nombres de plantilla `urn:schemas-microsoft-com:xml-sql`.</span><span class="sxs-lookup"><span data-stu-id="1a479-127">The `sql:is-mapping-schema` annotation belongs to the template namespace `urn:schemas-microsoft-com:xml-sql`.</span></span>  
  
 <span data-ttu-id="1a479-128">Para probar este ejemplo, guarde la plantilla (InlineSchemaTemplate.xml) en un directorio local y, a continuación, cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="1a479-128">To test this example, save the template (InlineSchemaTemplate.xml) in a local directory and then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="1a479-129">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1a479-129">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1a479-130">Además de especificar el `mapping-schema` atributo en el **\<sql:xpath-query>** elemento de una plantilla (cuando hay una consulta XPath) o en un **\<updg:sync>** elemento de un diagrama, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1a479-130">In addition to specifying the `mapping-schema` attribute on the **\<sql:xpath-query>** element in a template (when there is an XPath query), or on **\<updg:sync>** element in an updategram, you can do the following:</span></span>  
  
-   <span data-ttu-id="1a479-131">Especifique el `mapping-schema` atributo en el **\<ROOT>** elemento (declaración global) de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="1a479-131">Specify the `mapping-schema` attribute on the **\<ROOT>** element (global declaration) in the template.</span></span> <span data-ttu-id="1a479-132">Este esquema de asignación se convierte en el esquema predeterminado que utilizarán todos los nodos XPath y de diagrama de actualización que no tengan ninguna anotación `mapping-schema` explícita.</span><span class="sxs-lookup"><span data-stu-id="1a479-132">This mapping schema then becomes the default schema that will be used by all XPath and updategram nodes that have no explicit `mapping-schema` annotation.</span></span>  
  
-   <span data-ttu-id="1a479-133">Especificar el atributo `mapping schema` mediante el objeto ADO `Command`.</span><span class="sxs-lookup"><span data-stu-id="1a479-133">Specify the `mapping schema` attribute by using the ADO `Command` object.</span></span>  
  
 <span data-ttu-id="1a479-134">El `mapping-schema` atributo que se especifica en el **\<xpath-query>** **\<updg:sync>** elemento o tiene la prioridad más alta; el `Command` objeto ADO tiene la prioridad más baja.</span><span class="sxs-lookup"><span data-stu-id="1a479-134">The `mapping-schema` attribute that is specified on the **\<xpath-query>** or **\<updg:sync>** element has the highest precedence; the ADO `Command` object has the lowest precedence.</span></span>  
  
 <span data-ttu-id="1a479-135">Tenga en cuenta que si especifica una consulta XPath en una plantilla y no especifica un esquema de asignación en el que se ejecuta la consulta XPath, la consulta XPath se trata como una consulta de tipo **dbobject** .</span><span class="sxs-lookup"><span data-stu-id="1a479-135">Note that if you specify an XPath query in a template and do not specify a mapping schema against which the XPath query is executed, the XPath query is treated as a **dbobject** type query.</span></span> <span data-ttu-id="1a479-136">Por ejemplo, fíjese en esta plantilla:</span><span class="sxs-lookup"><span data-stu-id="1a479-136">For example, consider this template:</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql">  
          Production.ProductPhoto[@ProductPhotoID='100']/@LargePhoto  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="1a479-137">La plantilla especifica una consulta XPath, pero no especifica ningún esquema de asignación.</span><span class="sxs-lookup"><span data-stu-id="1a479-137">The template specifies an XPath query but it does not specify a mapping schema.</span></span> <span data-ttu-id="1a479-138">Por lo tanto, esta consulta se trata como una consulta de tipo **dbobject** en la que production. ProductPhoto es el nombre de tabla y @ProductPhotoID = ' 100 ' es un predicado que busca una fotografía de producto con el valor de identificador de 100.</span><span class="sxs-lookup"><span data-stu-id="1a479-138">Therefore, this query is treated as a **dbobject** type query in which Production.ProductPhoto is the table name and @ProductPhotoID='100' is a predicate that finds a product photo with the ID value of 100.</span></span> <span data-ttu-id="1a479-139">@LargePhotoes la columna de la que se va a recuperar el valor.</span><span class="sxs-lookup"><span data-stu-id="1a479-139">@LargePhoto is the column from which to retrieve the value.</span></span>  
  
  
