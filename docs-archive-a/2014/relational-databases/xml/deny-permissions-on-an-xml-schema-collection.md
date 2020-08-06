---
title: Revocación de los permisos en una colección de esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- denying permissions [SQL Server], XML server collections
ms.assetid: e2b300b0-e734-4c43-a4da-c78e6e5d4fba
author: rothja
ms.author: jroth
ms.openlocfilehash: 0791a9bd9c7f6b323886a38bed27bea84940770d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662697"
---
# <a name="deny-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="32f90-102">Denegar permisos en una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="32f90-102">Deny Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="32f90-103">Es posible denegar permisos para crear una colección de esquemas XML nueva o utilizar una existente.</span><span class="sxs-lookup"><span data-stu-id="32f90-103">Permission can be denied to either create a new XML schema collection or use an existing one.</span></span>  
  
## <a name="denying-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="32f90-104">Denegar permisos para crear una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="32f90-104">Denying Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="32f90-105">Puede denegar los permisos para crear una colección de esquemas XML del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="32f90-105">You can deny permission to create an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="32f90-106">Denegar el permiso ALTER en el esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="32f90-106">Deny ALTER permission on the relational schema.</span></span>  
  
-   <span data-ttu-id="32f90-107">Denegar el permiso CONTROL en el esquema relacional para denegar todos los permisos en el esquema relacional y en todos los objetos incluidos.</span><span class="sxs-lookup"><span data-stu-id="32f90-107">Deny CONTROL on the relational schema to deny all permissions on the relational schema and on all the contained objects.</span></span>  
  
-   <span data-ttu-id="32f90-108">Denegar el permiso ALTER ANY SCHEMA en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-108">Deny ALTER ANY SCHEMA on the database.</span></span> <span data-ttu-id="32f90-109">En este caso, la entidad de seguridad no puede crear una colección de esquemas XML en ninguna parte de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-109">In this case, the principal cannot create an XML schema collection anywhere in the database.</span></span> <span data-ttu-id="32f90-110">Observe que al denegar los permisos ALTER o CONTROL en la base de datos, se denegarán todos los permisos en todos los objetos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-110">Note also that denying ALTER or CONTROL permission on the database denies all permissions on all objects in the database.</span></span>  
  
## <a name="denying-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="32f90-111">Denegar permisos en un objeto de colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="32f90-111">Denying Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="32f90-112">A continuación, se enumeran los permisos que pueden denegarse en una colección de esquemas XML y los resultados:</span><span class="sxs-lookup"><span data-stu-id="32f90-112">Following are the permission that can be denied on an existing XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="32f90-113">Denegar el permiso ALTER deniega a la entidad de seguridad la posibilidad de modificar el contenido de la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="32f90-113">Denying the ALTER permission denies the principal the ability to modify the contents of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="32f90-114">Denegar el permiso CONTROL deniega a la entidad de seguridad la posibilidad de efectuar cualquier operación en la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="32f90-114">Denying the CONTROL permission denies the principal the ability to perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="32f90-115">Denegar el permiso REFERENCES deniega a la entidad de seguridad la posibilidad de escribir o restringir parámetros y columnas de tipo xml utilizando la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="32f90-115">Denying the REFERENCES permission denies the principal the ability to type or constrain xml type columns and parameters using the XML schema collection.</span></span> <span data-ttu-id="32f90-116">También deniega a la entidad de seguridad la posibilidad de consultar esta colección de esquemas XML desde otras colecciones de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="32f90-116">It also denies the principal the ability to refer to this XML schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="32f90-117">Denegar el permiso VIEW DEFINITION deniega a la entidad de seguridad la posibilidad de ver el contenido de una colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="32f90-117">Denying the VIEW DEFINITION permission denies the principal the ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="32f90-118">Denegar el permiso EXECUTE deniega a la entidad de seguridad la posibilidad de insertar o actualizar los valores de las columnas, variables y parámetros que se escriben o limitan por parte de la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="32f90-118">Denying the EXECUTE permission denies the principal the ability to insert or update the values in columns, variables, and parameters that are typed or constrained by the XML schema collection.</span></span> <span data-ttu-id="32f90-119">También deniega a la entidad de seguridad la posibilidad de consultar los valores en las mismas variables y columnas de tipo xml.</span><span class="sxs-lookup"><span data-stu-id="32f90-119">It also denies the principal the ability to query the values in those same xml type columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="32f90-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="32f90-120">Examples</span></span>  
 <span data-ttu-id="32f90-121">Los escenarios de los ejemplos siguientes muestran el funcionamiento de los permisos de los esquemas XML</span><span class="sxs-lookup"><span data-stu-id="32f90-121">The scenarios in the following examples show how XML schema permissions work.</span></span> <span data-ttu-id="32f90-122">En cada ejemplo se crea la base de datos de prueba, los esquemas relacionales y los inicios de sesión necesarios.</span><span class="sxs-lookup"><span data-stu-id="32f90-122">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="32f90-123">A estos inicios de sesión se les conceden los permisos necesarios para la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="32f90-123">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="32f90-124">Al final, cada ejemplo realiza las operaciones de limpieza necesarias.</span><span class="sxs-lookup"><span data-stu-id="32f90-124">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-preventing-a-user-from-creating-an-xml-schema-collection"></a><span data-ttu-id="32f90-125">A.</span><span class="sxs-lookup"><span data-stu-id="32f90-125">A.</span></span> <span data-ttu-id="32f90-126">Evitar que un usuario cree una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="32f90-126">Preventing a user from creating an XML schema collection</span></span>  
 <span data-ttu-id="32f90-127">Una de las formas de evitar que un usuario cree una colección de esquemas XML consiste en denegar el permiso ALTER en un esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="32f90-127">One of the ways to prevent a user from creating an XML schema collection is by denying the ALTER permission on a relational schema.</span></span> <span data-ttu-id="32f90-128">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="32f90-128">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="32f90-129">El ejemplo crea un usuario, `TestLogin1`, y una base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-129">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="32f90-130">Además del esquema `dbo` , también se crea un esquema relacional en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-130">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="32f90-131">Inicialmente, el permiso `CREATE XML SCHEMA` permite al usuario crear una colección de esquemas en cualquier lugar de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-131">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span> <span data-ttu-id="32f90-132">A continuación, se deniega el permiso `ALTER` al usuario en uno de los esquemas relacionales.</span><span class="sxs-lookup"><span data-stu-id="32f90-132">The example then denies `ALTER` permission to the user on one of the relational schemas.</span></span> <span data-ttu-id="32f90-133">Esto impide al usuario crear una colección de esquemas XML en ese esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="32f90-133">This prevents the user from creating an XML schema collection in that relational schema.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
GO  
-- Now deny permission from TestLogin1 to alter myOtherDBSchema.  
setuser  
GO  
DENY ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
GO  
-- Now TestLogin1 cannot create xml schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="b-denying-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="32f90-134">B.</span><span class="sxs-lookup"><span data-stu-id="32f90-134">B.</span></span> <span data-ttu-id="32f90-135">Denegar permisos en una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="32f90-135">Denying permissions on an XML schema collection</span></span>  
 <span data-ttu-id="32f90-136">El ejemplo siguiente muestra cómo se puede denegar a un inicio de sesión un permiso específico en una colección de esquemas XML existente.</span><span class="sxs-lookup"><span data-stu-id="32f90-136">The following example shows how a specific permission on an existing XML schema collection can be denied to a login.</span></span> <span data-ttu-id="32f90-137">En este ejemplo, se deniega el permiso REFERENCES a un inicio de sesión de prueba para una colección de esquemas XML existente.</span><span class="sxs-lookup"><span data-stu-id="32f90-137">In this example, a test login is denied REFERENCES permission on an existing XML schema collection.</span></span>  
  
 <span data-ttu-id="32f90-138">El ejemplo crea un usuario, `TestLogin1`, y una base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-138">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="32f90-139">Además del esquema `dbo` , también se crea un esquema relacional en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-139">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="32f90-140">Inicialmente, el permiso `CREATE XML SCHEMA` permite al usuario crear una colección de esquemas en cualquier lugar de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="32f90-140">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span>  
  
 <span data-ttu-id="32f90-141">El permiso `REFERENCES` para la colección de esquemas XML permite a `TestLogin1` utilizar el esquema para crear una columna `xml` con tipo en una tabla.</span><span class="sxs-lookup"><span data-stu-id="32f90-141">The `REFERENCES` permission on the XML schema collection lets `TestLogin1` use the schema in creating a typed `xml` column in a table.</span></span> <span data-ttu-id="32f90-142">Si se deniega el permiso `REFERENCES` para la colección de esquemas XML, se evita que `TestLogin1` use la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="32f90-142">If the `REFERENCES` permission on the XML schema collection is denied, it prevents the `TestLogin1` from using the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, the following  
-- permission is required.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant permission to TestLogin1 to create a table and reference the XML schema collection.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also needs REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on the schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection   
TO TestLogin1  
GO  
  
--TestLogin1 can use the schema.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
-- Drop the table.  
DROP TABLE T  
GO  
-- Now deny REFERENCES permission to TestLogin1 on the schema created previously.  
SETUSER  
GO  
DENY REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection TO TestLogin1  
  
GO  
-- Now TestLogin1 cannot create xml schema collection  
SETUSER 'TestLogin1'  
GO  
-- Following statement fails. TestLogin1 does not have REFERENCES   
-- permission on the XML schema collection.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="32f90-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32f90-143">See Also</span></span>  
 <span data-ttu-id="32f90-144">[Comparar XML con tipo y XML sin tipo](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="32f90-144">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="32f90-145">[Colecciones de esquemas XML &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="32f90-145">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 <span data-ttu-id="32f90-146">[Requisitos y limitaciones de las colecciones de esquemas XML en el servidor](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span><span class="sxs-lookup"><span data-stu-id="32f90-146">[Requirements and Limitations for XML Schema Collections on the Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span></span>  
 <span data-ttu-id="32f90-147">[Permisos de objeto DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="32f90-147">[DENY Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="32f90-148">[Permisos de objeto GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="32f90-148">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="32f90-149">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="32f90-149">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
