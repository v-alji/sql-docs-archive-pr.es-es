---
title: Ver una colección de esquemas XML almacenada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- schema collections [SQL Server], viewing
- XML schemas [SQL Server], viewing
- CREATE XML SCHEMA COLLECTION statement
- xml_schema_namespace function
- XML schema collections [SQL Server], viewing
- displaying XML schema collections
- viewing XML schema collections
ms.assetid: e38031af-22df-4cd9-a14e-e316b822f91b
author: rothja
ms.author: jroth
ms.openlocfilehash: 6383fb17183a991d2f83325044663cc9671e9442
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669543"
---
# <a name="view-a-stored-xml-schema-collection"></a><span data-ttu-id="836d5-102">Ver una colección de esquemas XML almacenada</span><span class="sxs-lookup"><span data-stu-id="836d5-102">View a Stored XML Schema Collection</span></span>
  <span data-ttu-id="836d5-103">Después de importar una colección de esquemas XML mediante [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), los componentes del esquema se almacenan en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="836d5-103">After you import an XML schema collection by using [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), the schema components are stored in the metadata.</span></span> <span data-ttu-id="836d5-104">Puede usar la función intrínseca [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)para reconstruir la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="836d5-104">You can use the [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)intrinsic function to reconstruct the XML schema collection.</span></span> <span data-ttu-id="836d5-105">La función devuelve una instancia de tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="836d5-105">This function returns an `xml` data type instance.</span></span>  
  
 <span data-ttu-id="836d5-106">Por ejemplo, la siguiente consulta recupera una colección de esquemas XML (`ProductDescriptionSchemaCollection`) del esquema relacional de producción de la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="836d5-106">For example, the following query retrieves an XML schema collection (`ProductDescriptionSchemaCollection`) from the production relational schema in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection')  
GO  
```  
  
 <span data-ttu-id="836d5-107">Si solo desea ver un esquema de la colección de esquemas XML, puede especificar XQuery en el resultado de tipo `xml` devuelto por `xml_schema_namespace`.</span><span class="sxs-lookup"><span data-stu-id="836d5-107">If you want to see only one schema from the XML schema collection, you can specify XQuery against the `xml` type result that is returned by `xml_schema_namespace`.</span></span>  
  
```  
SELECT xml_schema_namespace(N'RelationalSchemaName',N'XmlSchemaCollectionName').query('  
/xs:schema[@targetNamespace="TargetNameSpace"]  
')  
GO  
```  
  
 <span data-ttu-id="836d5-108">La siguiente consulta, por ejemplo, recupera información de garantía del producto y de mantenimiento del esquema XML a partir de la colección de esquemas XML `ProductDescriptionSchemaCollection` .</span><span class="sxs-lookup"><span data-stu-id="836d5-108">For example, the following query retrieves product warranty and maintenance XML schema information from the `ProductDescriptionSchemaCollection` XML schema collection.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection').query('  
/xs:schema[@targetNamespace="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"]  
')  
GO  
```  
  
 <span data-ttu-id="836d5-109">También puede pasar el espacio de nombres de destino opcional como tercer parámetro a la función `xml_schema_namespace` con el fin de recuperar un esquema específico de la colección, tal y como muestra la consulta siguiente:</span><span class="sxs-lookup"><span data-stu-id="836d5-109">You can also pass the optional target namespace as the third parameter to the `xml_schema_namespace` function to retrieve specific schema from the collection, as shown in the following query:</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection', N'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain')  
GO  
```  
  
 <span data-ttu-id="836d5-110">Al crear una colección de esquemas XML mediante CREATE XML SCHEMA COLLECTION en la base de datos, la instrucción almacena los componentes de esquema en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="836d5-110">When you create an XML schema collection by using CREATE XML SCHEMA COLLECTION in the database, the statement stores the schema components in the metadata.</span></span> <span data-ttu-id="836d5-111">Observe que solo se almacenarán aquellos componentes de esquema que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pueda interpretar.</span><span class="sxs-lookup"><span data-stu-id="836d5-111">Note that only the schema components that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] understands are stored.</span></span> <span data-ttu-id="836d5-112">No se almacenarán comentarios, anotaciones ni atributos que no sean XSD.</span><span class="sxs-lookup"><span data-stu-id="836d5-112">Any comments, annotations, or non-XSD attributes are not stored.</span></span> <span data-ttu-id="836d5-113">Por tanto, el esquema reconstruido por **xml_schema_namespace** será funcionalmente equivalente al esquema original, pero no tendrá necesariamente la misma apariencia.</span><span class="sxs-lookup"><span data-stu-id="836d5-113">Therefore, the schema reconstructed by **xml_schema_namespace** is functionally equivalent to the original schema, but it will not necessarily look the same.</span></span> <span data-ttu-id="836d5-114">Por ejemplo, no se observarán los mismos prefijos del esquema original.</span><span class="sxs-lookup"><span data-stu-id="836d5-114">For example, you will not see the same prefixes you had in the original schema.</span></span> <span data-ttu-id="836d5-115">El esquema devuelto por **xml_schema_namespace** usa **t** como el prefijo para el espacio de nombres de destino y **ns1**, **ns2**, etc., para otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="836d5-115">The schema returned by **xml_schema_namespace** uses **t** as the prefix for the target namespace and **ns1**, **ns2**, and so on, for other namespaces.</span></span>  
  
 <span data-ttu-id="836d5-116">Si desea conservar una copia idéntica de los esquemas XML, debería guardarlos en un archivo o en una tabla de base de datos en una columna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="836d5-116">If you want to retain an identical copy of the XML schemas, you should save your XML schema in a file or in a database table in an `xml` type column.</span></span>  
  
 <span data-ttu-id="836d5-117">La vista de catálogo [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) también devuelve información sobre las colecciones de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="836d5-117">The [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) catalog view also returns information about XML schema collections.</span></span> <span data-ttu-id="836d5-118">La información consiste en el nombre la colección, la fecha de creación y el nombre del propietario.</span><span class="sxs-lookup"><span data-stu-id="836d5-118">This information includes the name of the collection, the creation date, and the owner of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836d5-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="836d5-119">See Also</span></span>  
 [<span data-ttu-id="836d5-120">Colecciones de esquemas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="836d5-120">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
