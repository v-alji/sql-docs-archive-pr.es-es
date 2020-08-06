---
title: Asignación de referencias a la colección de esquemas XML integrada (sys) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- sys XML schema collections [SQL Server]
- schema collections [SQL Server], predefined
- predefined XML schema collections [SQL Server]
- XML schema collections [SQL Server], predefined
- built-in XML schema collections [SQL Server]
ms.assetid: 1e118303-5df0-4ee4-bd8d-14ced7544144
author: rothja
ms.author: jroth
ms.openlocfilehash: 7fa30107e1746b33e3f9b8eb1cfa53d1f4d25fb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745079"
---
# <a name="reference-the-built-in-xml-schema-collection-sys"></a><span data-ttu-id="aaa6f-102">Hacer referencia a la colección de esquemas XML integrada (sys)</span><span class="sxs-lookup"><span data-stu-id="aaa6f-102">Reference the Built-in XML Schema Collection (sys)</span></span>
  <span data-ttu-id="aaa6f-103">Cada base de datos que se crea posee una colección de esquemas XML **sys** predefinida en el esquema relacional **sys** .</span><span class="sxs-lookup"><span data-stu-id="aaa6f-103">Every database you create has a predefined **sys** XML schema collection in the **sys** relational schema.</span></span> <span data-ttu-id="aaa6f-104">Estos esquemas predefinidos se reservan, y son accesibles desde cualquier otra colección de esquemas XML creada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-104">It reserves these predefined schemas, and they can be accessed from any other user-created XML schema collection.</span></span> <span data-ttu-id="aaa6f-105">Los prefijos utilizados en estos esquemas predefinidos son significativos en XQuery.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-105">The prefixes used in these predefined schemas are meaningful in XQuery.</span></span> <span data-ttu-id="aaa6f-106">El único prefijo reservado es **xml** .</span><span class="sxs-lookup"><span data-stu-id="aaa6f-106">Only **xml** is a reserved prefix.</span></span>  
  
```  
xml = http://www.w3.org/XML/1998/namespace  
xs = http://www.w3.org/2001/XMLSchema  
xsi = http://www.w3.org/2001/XMLSchema-instance  
fn = http://www.w3.org/2004/07/xpath-functions  
sqltypes = https://schemas.microsoft.com/sqlserver/2004/sqltypes  
xdt = http://www.w3.org/2004/07/xpath-datatypes  
(no prefix) = urn:schemas-microsoft-com:xml-sql  
(no prefix) = https://schemas.microsoft.com/sqlserver/2004/SOAP  
```  
  
 <span data-ttu-id="aaa6f-107">Debe tenerse en cuenta que el espacio de nombres **sqltypes** contiene componentes a los que se puede hacer referencia desde cualquier colección de esquemas XML creada por el usuario.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-107">Note that the **sqltypes** namespace contains components that can be referenced from any user-created XML schema collection.</span></span> <span data-ttu-id="aaa6f-108">Puede descargar el esquema **sqltypes** de el [sitio web de Microsoft](https://go.microsoft.com/fwlink/?linkid=31850).</span><span class="sxs-lookup"><span data-stu-id="aaa6f-108">You can download the **sqltypes** schema from this [Microsoft Web site](https://go.microsoft.com/fwlink/?linkid=31850).</span></span> <span data-ttu-id="aaa6f-109">Los componentes integrados son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="aaa6f-109">The built-in components include the following:</span></span>  
  
-   <span data-ttu-id="aaa6f-110">Tipos XSD</span><span class="sxs-lookup"><span data-stu-id="aaa6f-110">XSD types</span></span>  
  
-   <span data-ttu-id="aaa6f-111">Atributos XML **lang**, **base**y **space**</span><span class="sxs-lookup"><span data-stu-id="aaa6f-111">XML attributes **lang**, **base**, and **space**</span></span>  
  
-   <span data-ttu-id="aaa6f-112">Componentes del espacio de nombres **sqltypes**</span><span class="sxs-lookup"><span data-stu-id="aaa6f-112">Components of the **sqltypes** namespace</span></span>  
  
 <span data-ttu-id="aaa6f-113">La consulta siguiente devuelve los componentes integrados a los que se puede hacer referencia desde una colección de esquemas XML creada por el usuario:</span><span class="sxs-lookup"><span data-stu-id="aaa6f-113">The following query returns built-in components that can be referenced from a user-created XML schema collection:</span></span>  
  
```  
SELECT C.name, N.name, C.symbol_space_desc from sys.xml_schema_components C join sys.xml_schema_namespaces N  
on ((C.xml_namespace_id = N.xml_namespace_id) AND (C.xml_collection_id = N.xml_collection_id))  
join sys.xml_schema_collections SC  
on SC.xml_collection_id = C.xml_collection_id  
where ((C.xml_collection_id = 1) AND (C.name is not null) AND (C.scoping_xml_component_id is null)   
AND (SC.schema_id = 4))  
GO  
```  
  
 <span data-ttu-id="aaa6f-114">En el ejemplo siguiente se muestra cómo se hace referencia a estos componentes en un esquema de usuario.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-114">The following example shows how these components are referenced in a user schema.</span></span> <span data-ttu-id="aaa6f-115">`CREATE XML SCHEMA COLLECTION` crea una colección de esquemas XML que hace referencia al tipo `varchar` definido en el espacio de nombres `sqltypes` .</span><span class="sxs-lookup"><span data-stu-id="aaa6f-115">`CREATE XML SCHEMA COLLECTION` creates an XML schema collection that references the `varchar` type defined in the `sqltypes` namespace.</span></span> <span data-ttu-id="aaa6f-116">En el ejemplo también se hace referencia al atributo `lang` que está definido en el espacio de nombres `xml` .</span><span class="sxs-lookup"><span data-stu-id="aaa6f-116">The example also references the `lang` attribute that is defined in the `xml` namespace.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema   
   xmlns="http://www.w3.org/2001/XMLSchema"   
   targetNamespace="myNS"  
   xmlns:ns="myNS"  
   xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
   <import namespace="http://www.w3.org/XML/1998/namespace"/>  
   <import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
   <element name="root">  
      <complexType>  
          <sequence>  
             <element name="a" type="string"/>  
             <element name="b" type="string"/>  
             <!-- varchar type is defined in the sys.sys collection and   
                  can be referenced in any user-defined schema -->  
             <element name="c" type="s:varchar"/>  
          </sequence>  
          <attribute name="att" type="int"/>  
          <!-- xml:lang attribute is defined in the sys.sys collection   
               and can be referenced in any user-defined schema -->  
          <attribute ref="xml:lang"/>  
      </complexType>  
    </element>  
 </schema>'  
GO  
 -- Cleanup  
DROP xml schema collection SC   
GO  
```  
  
 <span data-ttu-id="aaa6f-117">Se debe tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aaa6f-117">You should note the following:</span></span>  
  
-   <span data-ttu-id="aaa6f-118">No se pueden modificar esquemas XML con estos espacios de nombres en ninguna colección de esquemas XML definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-118">You cannot modify XML schemas with these namespaces in any user-defined XML schema collection.</span></span> <span data-ttu-id="aaa6f-119">Por ejemplo, la siguiente colección de esquemas XML genera un error porque agrega un componente al espacio de nombres protegido `sqltypes` :</span><span class="sxs-lookup"><span data-stu-id="aaa6f-119">For example, the following XML schema collection fails, because it is adding a component to the `sqltypes` protected namespace:</span></span>  
  
    ```  
    CREATE XML SCHEMA COLLECTION SC AS '  
    <schema xmlns="http://www.w3.org/2001/XMLSchema"   
    targetNamespace    
        ="https://schemas.microsoft.com/sqlserver/2004/sqltypes" >   
          <element name="root" type="string"/>  
    </schema>'  
    GO  
    ```  
  
-   <span data-ttu-id="aaa6f-120">No se puede utilizar la colección de esquemas XML `sys` para escribir columnas, variables o parámetros `xml` .</span><span class="sxs-lookup"><span data-stu-id="aaa6f-120">You cannot use the `sys` XML schema collection to type `xml` columns, variables, or parameters.</span></span> <span data-ttu-id="aaa6f-121">Por ejemplo, el siguiente código genera un error:</span><span class="sxs-lookup"><span data-stu-id="aaa6f-121">For example, the following code returns an error:</span></span>  
  
    ```  
    DECLARE @x xml (sys.sys)  
    ```  
  
-   <span data-ttu-id="aaa6f-122">No se admite la serialización de estos esquemas integrados.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-122">Serialization of these built-in schemas is not supported.</span></span> <span data-ttu-id="aaa6f-123">Por ejemplo, el siguiente código genera un error:</span><span class="sxs-lookup"><span data-stu-id="aaa6f-123">For example, the following code returns an error:</span></span>  
  
    ```  
    SELECT XML_SCHEMA_NAMESPACE(N'sys',N'sys')  
    GO  
    ```  
  
 <span data-ttu-id="aaa6f-124">A continuación se ofrece otro ejemplo de código en el que se crea una colección de esquemas XML que utiliza el tipo `varchar` definido en el espacio de nombres `sqltypes`:</span><span class="sxs-lookup"><span data-stu-id="aaa6f-124">The following code is another example in which you create an XML schema collection that uses the `varchar` type defined in the `sqltypes` namespace:</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="myNS" xmlns:ns="myNS"  
        xmlns:s="https://schemas.microsoft.com/sqlserver/2004/sqltypes">  
   <import     
     namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes"/>  
      <simpleType name="myType">  
            <restriction base="s:varchar">  
                  <maxLength value="20"/>  
            </restriction>  
      </simpleType>  
      <element name="root" type="ns:myType"/>  
</schema>'  
go  
```  
  
 <span data-ttu-id="aaa6f-125">Como se observa a continuación, se puede crear una variable `XML` con tipo, asignarle una instancia XML y comprobar que el valor del tipo de elemento <`root`> sea `varchar`.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-125">As shown in the following, you can create a typed `XML` variable, assign an XML instance to it, and verify that the value of the <`root`> element type is a `varchar` type.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<root xmlns="myNS">My data</root>'  
SELECT @var.query('declare namespace sqltypes = "https://schemas.microsoft.com/sqlserver/2004/sqltypes";  
declare namespace ns="myNS";   
data(/ns:root[1]) instance of sqltypes:varchar?')  
GO  
```  
  
 <span data-ttu-id="aaa6f-126">La expresión `instance of sqltypes:varchar?` devuelve TRUE, porque el valor del elemento <`root`> es de un tipo derivado de **varchar** según el esquema asociado a la variable `@var`.</span><span class="sxs-lookup"><span data-stu-id="aaa6f-126">The `instance of sqltypes:varchar?` expression returns TRUE, because the <`root`> element value is of a type derived from **varchar** according to the schema that is associated with the `@var` variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa6f-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aaa6f-127">See Also</span></span>  
 [<span data-ttu-id="aaa6f-128">Colecciones de esquemas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aaa6f-128">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
