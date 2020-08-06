---
title: 'Crear secciones CDATA mediante SQL: Use-CDATA (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- markup characters [SQLXML]
- special characters [SQLXML]
- use-cdata annotation
- plain text [SQLXML]
- CDATA sections
- escaping blocks of text [SQLXML]
- annotated XSD schemas, CDATA sections
- sql:use-cdata
ms.assetid: 26d2b9dc-f857-44ff-bcd4-aaf64ff809d0
author: rothja
ms.author: jroth
ms.openlocfilehash: c0ba0787efbda400590a75f0f3529e3df8819e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676429"
---
# <a name="creating-cdata-sections-using-sqluse-cdata-sqlxml-40"></a><span data-ttu-id="aaeb3-102">Crear secciones CDATA mediante sql:use-cdata (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="aaeb3-102">Creating CDATA Sections Using sql:use-cdata (SQLXML 4.0)</span></span>
  <span data-ttu-id="aaeb3-103">En XML, las secciones CDATA se usan para establecer secuencias de escape en bloques de texto que contienen caracteres que, de lo contrario, se reconocerían como caracteres de marcado.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-103">In XML, CDATA sections are used to escape blocks of text that contain characters that would otherwise be recognized as markup characters.</span></span>  
  
 <span data-ttu-id="aaeb3-104">En ocasiones, una base de datos de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede contener caracteres que el analizador XML trata como caracteres de marcado; por ejemplo, corchetes angulares ( \< and > ), el símbolo menor o igual que (<=) y la y comercial (&) se tratan como caracteres de marcado.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-104">A database in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can sometimes contain characters that are treated as markup characters by the XML parser; for example, angle brackets (\< and >), the less-than-or-equal-to symbol (<=), and the ampersand (&) are treated as markup characters.</span></span> <span data-ttu-id="aaeb3-105">Sin embargo, puede ajustar este tipo de caracteres especiales en una sección CDATA para evitar que se traten como caracteres de marcado.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-105">However, you can wrap this type of special characters in a CDATA section to prevent them from being treated as markup characters.</span></span> <span data-ttu-id="aaeb3-106">El analizador XML trata el texto de la sección CDATA como texto simple.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-106">The text within the CDATA section is treated by the XML parser as plain text.</span></span>  
  
 <span data-ttu-id="aaeb3-107">La anotación `sql:use-cdata` se usa para especificar que los datos que devuelve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se deberían ajustar en una sección CDATA (es decir, indica si el valor de una columna especificada a través de `sql:field` se debería agregar en una sección CDATA).</span><span class="sxs-lookup"><span data-stu-id="aaeb3-107">The `sql:use-cdata` annotation is used to specify that the data returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should be wrapped in a CDATA section (that is, it indicates whether the value from a column that is specified by `sql:field` should be enclosed in a CDATA section).</span></span> <span data-ttu-id="aaeb3-108">La anotación `sql:use-cdata` únicamente se puede especificar en los elementos que asignan a una columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-108">The `sql:use-cdata` annotation can be specified only on elements that map to a database column.</span></span>  
  
 <span data-ttu-id="aaeb3-109">La anotación `sql:use-cdata` toma un valor booleano (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="aaeb3-109">The `sql:use-cdata` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="aaeb3-110">Los valores permitidos son 0, 1, true y false.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="aaeb3-111">Esta anotación no se puede usar con `sql:url-encode` ni en los tipos de atributo ID, IDREF, IDREFS, NMTOKEN y NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-111">This annotation cannot be used with `sql:url-encode` or on the ID, IDREF, IDREFS, NMTOKEN, and NMTOKENS attribute types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="aaeb3-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="aaeb3-112">Examples</span></span>  
 <span data-ttu-id="aaeb3-113">Para crear muestras funcionales mediante los ejemplos siguientes, debe cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-113">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="aaeb3-114">Para obtener más información, vea [Requirements for Running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="aaeb3-114">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqluse-cdata-on-an-element"></a><span data-ttu-id="aaeb3-115">A.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-115">A.</span></span> <span data-ttu-id="aaeb3-116">Especificar sql:use-cdata en un elemento</span><span class="sxs-lookup"><span data-stu-id="aaeb3-116">Specifying sql:use-cdata on an element</span></span>  
 <span data-ttu-id="aaeb3-117">En el esquema siguiente, `sql:use-cdata` se establece en 1 (true) para **\<AddressLine1>** en el **\<Address>** elemento.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-117">In the following schema, `sql:use-cdata` is set to 1 (True) for the **\<AddressLine1>** within the **\<Address>** element.</span></span> <span data-ttu-id="aaeb3-118">Como resultado, los datos se devuelven en una sección CDATA.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-118">As a result, the data is returned in a CDATA section.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Address"   
               sql:relation="Person.Address"   
               sql:key-fields="AddressID" >  
   <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="AddressID"  type="xsd:string" />  
          <xsd:element name="AddressLine1" type="xsd:string"   
                       sql:use-cdata="1" />  
        </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="aaeb3-119">Para probar una consulta XPath de ejemplo en el esquema</span><span class="sxs-lookup"><span data-stu-id="aaeb3-119">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="aaeb3-120">Copie el código de esquema anterior y péguelo en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-120">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="aaeb3-121">Guarde el archivo como UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-121">Save the file as UseCData.xml.</span></span>  
  
2.  <span data-ttu-id="aaeb3-122">Copie la plantilla siguiente y péguela en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-122">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="aaeb3-123">Guarde el archivo como UseCDataT.xml en el mismo directorio donde guardó UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-123">Save the file as UseCDataT.xml in the same directory where you saved UseCData.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="UseCData.xml">  
            /Address[AddressID < 11]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="aaeb3-124">La ruta de acceso al directorio especificada para el esquema de asignación (UseCData.xml) es relativa al directorio donde se guarda la plantilla.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-124">The directory path specified for the mapping schema (UseCData.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="aaeb3-125">También puede especificarse una ruta de acceso absoluta como, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aaeb3-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\UseCData.xml"  
    ```  
  
3.  <span data-ttu-id="aaeb3-126">Cree y use el script de prueba SQLXML 4.0 (Sqlxml4test.vbs) para ejecutar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="aaeb3-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="aaeb3-127">Para obtener más información, vea [usar ado para ejecutar consultas SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="aaeb3-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="aaeb3-128">Éste es el conjunto de resultados parciales:</span><span class="sxs-lookup"><span data-stu-id="aaeb3-128">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Address>   
    <AddressID>1</CustomerID>   
    <AddressLine1>   
      <![CDATA[ 1970 Napa Ct.  ]]>   
    </AddressLine1>   
  </Address>  
  <Address>  
    <AddressLine1>   
      <![CDATA[ 9833 Mt. Dias Blv. ]]>   
    </AddressLine1>   
  </Address>  
  ...  
</ROOT>  
```  
  
  
