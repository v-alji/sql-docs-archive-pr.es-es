---
title: 'Solicitar referencias URL a datos BLOB mediante SQL: encode (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:encode
- encode annotation
- URL references to BLOB data [SQLXML]
- references to BLOB data [SQLXML]
- annotated XSD schemas, URL references to BLOB data
- requesting URL references to BLOB data
- BLOBs, URL references
- Base 64-encoded format
ms.assetid: 2f8cd93b-c636-462b-8291-167197233ee0
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a9f5edcfab4a9d7307327d97bc2099c78c666c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676421"
---
# <a name="requesting-url-references-to-blob-data-using-sqlencode-sqlxml-40"></a><span data-ttu-id="b5c05-102">Solicitar referencias URL a los datos BLOB mediante sql:encode (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b5c05-102">Requesting URL References to BLOB Data Using sql:encode (SQLXML 4.0)</span></span>
  <span data-ttu-id="b5c05-103">En un esquema XSD anotado, cuando un atributo (o elemento) se asigna a una columna de BLOB en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]de Microsoft, los datos se devuelven en formato codificado de base 64 en XML.</span><span class="sxs-lookup"><span data-stu-id="b5c05-103">In an annotated XSD schema, when an attribute (or element) is mapped to a BLOB column in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data is returned in Base 64-encoded format within XML.</span></span>  
  
 <span data-ttu-id="b5c05-104">Si desea obtener una referencia a los datos (un URI) que se van a devolver, que se pueden usar posteriormente para recuperar los datos BLOB en un formato binario, especifique la anotación `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="b5c05-104">If you want a reference to the data (a URI) to be returned that can be used later to retrieve the BLOB data in a binary format, specify the `sql:encode` annotation.</span></span> <span data-ttu-id="b5c05-105">Puede especificar `sql:encode` en un atributo o elemento de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="b5c05-105">You can specify `sql:encode` on an attribute or element of simple type.</span></span>  
  
 <span data-ttu-id="b5c05-106">Especifique la anotación `sql:encode` para indicar que se debe devolver al campo una dirección URL en lugar del valor del campo.</span><span class="sxs-lookup"><span data-stu-id="b5c05-106">Specify the `sql:encode` annotation to indicate that a URL to the field should be returned instead of the value of the field.</span></span> <span data-ttu-id="b5c05-107">`sql:encode` depende de la clave principal para generar un SELECT singleton en la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="b5c05-107">`sql:encode` depends on the primary key to generate a singleton select in the URL.</span></span> <span data-ttu-id="b5c05-108">La clave principal se puede especificar mediante la `sql:key-fields` anotación.</span><span class="sxs-lookup"><span data-stu-id="b5c05-108">The primary key can be specified using the `sql:key-fields` annotation.</span></span>  
  
 <span data-ttu-id="b5c05-109">La anotación `sql:encode` puede tener asignada la dirección "url" o el valor "predeterminado".</span><span class="sxs-lookup"><span data-stu-id="b5c05-109">The `sql:encode` annotation can be assigned the "url" or the "default" value.</span></span> <span data-ttu-id="b5c05-110">Un valor de "valor predeterminado" devuelve los datos en formato codificado de base 64.</span><span class="sxs-lookup"><span data-stu-id="b5c05-110">A value of "default" returns data in Base 64-encoded format.</span></span>  
  
 <span data-ttu-id="b5c05-111">La anotación `sql:encode` no se puede usar con `sql:use-cdata` o en los tipos de atributo ID, IDREF, IDREFS, NMTOKEN o NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="b5c05-111">The `sql:encode` annotation cannot be used with `sql:use-cdata` or on the ID, IDREF, IDREFS, NMTOKEN, or NMTOKENS attribute types.</span></span> <span data-ttu-id="b5c05-112">Tampoco se puede utilizar con el atributo **fixed** xsd.</span><span class="sxs-lookup"><span data-stu-id="b5c05-112">It can also not be used with XSD **fixed** attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5c05-113">Las columnas de tipo BLOB no se pueden usar como parte de una clave o clave externa.</span><span class="sxs-lookup"><span data-stu-id="b5c05-113">BLOB-type columns cannot be used as a part of a key or foreign key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b5c05-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b5c05-114">Examples</span></span>  
 <span data-ttu-id="b5c05-115">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="b5c05-115">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="b5c05-116">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="b5c05-116">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlencode-to-obtain-a-url-reference-to-blob-data"></a><span data-ttu-id="b5c05-117">A.</span><span class="sxs-lookup"><span data-stu-id="b5c05-117">A.</span></span> <span data-ttu-id="b5c05-118">Especificar sql:encode para obtener una referencia de URL a los datos BLOB</span><span class="sxs-lookup"><span data-stu-id="b5c05-118">Specifying sql:encode to obtain a URL reference to BLOB data</span></span>  
 <span data-ttu-id="b5c05-119">En este ejemplo, el esquema de asignación especifica `sql:encode` en el atributo **LargePhoto** para recuperar la referencia de URI a una fotografía de producto específica (en lugar de recuperar los datos binarios en formato codificado de base 64).</span><span class="sxs-lookup"><span data-stu-id="b5c05-119">In this example, the mapping schema specifies `sql:encode` on the **LargePhoto** attribute to retrieve the URI reference to a specific product photo (instead of retrieving the binary data in Base 64-encoded format).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="ProductPhoto" sql:relation="Production.ProductPhoto"   
               sql:key-fields="ProductPhotoID" >  
   <xsd:complexType>  
      <xsd:attribute name="ProductPhotoID"  type="xsd:int"  />  
     <xsd:attribute name="LargePhoto" type="xsd:string" sql:encode="url" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="b5c05-120">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="b5c05-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="b5c05-121">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="b5c05-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="b5c05-122">Guarde el archivo como sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="b5c05-122">Save the file as sqlEncode.xml.</span></span>  
  
2.  <span data-ttu-id="b5c05-123">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="b5c05-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="b5c05-124">Guarde el archivo como sqlEncodeT.xml en el mismo directorio donde guardó sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="b5c05-124">Save the file as sqlEncodeT.xml in the same directory where you saved sqlEncode.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sqlEncode.xml">  
            /ProductPhoto[@ProductPhotoID=100]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="b5c05-125">La ruta de acceso al directorio especificada para el esquema de asignación (sqlEncode.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b5c05-125">The directory path specified for the mapping schema (sqlEncode.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="b5c05-126">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b5c05-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlEncode.xml"  
    ```  
  
3.  <span data-ttu-id="b5c05-127">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b5c05-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="b5c05-128">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b5c05-128">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="b5c05-129">El resultado es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5c05-129">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <ProductPhoto ProductPhotoID="100"  
                 LargePhoto="dbobject/Production.ProductPhoto[@ProductPhotoID="100"]/@LargePhoto" />   
</ROOT>  
```  
  
  
