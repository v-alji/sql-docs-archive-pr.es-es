---
title: Conceder permisos para una colección de esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- granting permissions [SQL Server], XML schema collections
- ALTER permission
ms.assetid: ffbb829c-3b8f-4e5d-97d9-ab4059aab0db
author: rothja
ms.author: jroth
ms.openlocfilehash: 2dc6384acb2f079245c80923e683ebe2c03d2562
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744539"
---
# <a name="grant-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="05a31-102">Conceder permisos para una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="05a31-102">Grant Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="05a31-103">Puede conceder permisos para crear una colección de esquemas XML y también puede concederlos para un objeto de colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-103">You can grant permissions to create an XML schema collection and also grant permissions on an XML schema collection object.</span></span>  
  
## <a name="granting-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="05a31-104">Conceder permisos para crear una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="05a31-104">Granting Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="05a31-105">Para crear una colección de esquemas XML, son necesarios los siguientes permisos:</span><span class="sxs-lookup"><span data-stu-id="05a31-105">To create an XML schema collection, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="05a31-106">La entidad de seguridad requiere el permiso CREATE XML SCHEMA COLLECTION en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05a31-106">The principal requires CREATE XML SCHEMA COLLECTION permission at the database-level.</span></span>  
  
-   <span data-ttu-id="05a31-107">Dado que las colecciones de esquemas XML tienen ámbito de esquema relacional, la entidad de seguridad también debe tener el permiso ALTER en el esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="05a31-107">Because the XML schema collections are relational schema-scoped, the principal must also have ALTER permission on the relational schema.</span></span>  
  
 <span data-ttu-id="05a31-108">Los permisos siguientes permiten a la entidad de seguridad crear una colección de esquemas XML en un esquema relacional en una base de datos de un servidor:</span><span class="sxs-lookup"><span data-stu-id="05a31-108">The following permissions let a principal create an XML schema collection in a relational schema in a database on a server:</span></span>  
  
-   <span data-ttu-id="05a31-109">Permiso CONTROL en el servidor</span><span class="sxs-lookup"><span data-stu-id="05a31-109">CONTROL permission on the server</span></span>  
  
-   <span data-ttu-id="05a31-110">Permiso ALTER ANY DATABASE en el servidor</span><span class="sxs-lookup"><span data-stu-id="05a31-110">ALTER ANY DATABASE permission on the server</span></span>  
  
-   <span data-ttu-id="05a31-111">Permiso ALTER en la base de datos</span><span class="sxs-lookup"><span data-stu-id="05a31-111">ALTER permission on the database</span></span>  
  
-   <span data-ttu-id="05a31-112">Permiso CONTROL en la base de datos</span><span class="sxs-lookup"><span data-stu-id="05a31-112">CONTROL permission in the database</span></span>  
  
-   <span data-ttu-id="05a31-113">Permiso ALTER ANY SCHEMA y permiso CREATE XML SCHEMA COLLECTION en la base de datos</span><span class="sxs-lookup"><span data-stu-id="05a31-113">ALTER ANY SCHEMA permission and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
-   <span data-ttu-id="05a31-114">Permiso ALTER o CONTROL en el esquema relacional y permiso CREATE XML SCHEMA COLLECTION en la base de datos</span><span class="sxs-lookup"><span data-stu-id="05a31-114">ALTER or CONTROL permission on the relational schema and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
 <span data-ttu-id="05a31-115">Éste último método de permisos se utiliza en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="05a31-115">This last method of permissions is used in the following example.</span></span>  
  
 <span data-ttu-id="05a31-116">El propietario del esquema relacional se convierte en el propietario de la colección de esquemas XML creada en dicho esquema.</span><span class="sxs-lookup"><span data-stu-id="05a31-116">The owner of the relational schema becomes the owner of the XML schema collection created in that schema.</span></span> <span data-ttu-id="05a31-117">Este propietario tendrá control total sobre la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-117">This owner then has full control over the XML schema collection.</span></span> <span data-ttu-id="05a31-118">Por tanto, el propietario puede modificar la colección de esquemas XML, escribir una columna xml o quitar la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-118">Therefore, this owner can modify the XML schema collection, type an xml column, or drop the XML schema collection.</span></span>  
  
## <a name="granting-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="05a31-119">Conceder permisos para un objeto de colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="05a31-119">Granting Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="05a31-120">Los permisos siguientes se admiten en la colección de esquemas XML:</span><span class="sxs-lookup"><span data-stu-id="05a31-120">The following permissions are allowed on the XML schema collection:</span></span>  
  
-   <span data-ttu-id="05a31-121">El permiso ALTER es necesario para modificar el contenido de una colección de esquemas XML utilizando la instrucción ALTER XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="05a31-121">The ALTER permission is required when modifying contents of an existing XML schema collection by using the ALTER XML SCHEMA COLLECTION statement.</span></span>  
  
-   <span data-ttu-id="05a31-122">El permiso CONTROL permite a un usuario realizar cualquier operación en la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-122">The CONTROL permission lets a user perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="05a31-123">El permiso TAKE OWNERSHIP es necesario para transferir la propiedad de la colección de esquemas XML de una entidad de seguridad a otra.</span><span class="sxs-lookup"><span data-stu-id="05a31-123">The TAKE OWNERSHIP permission is required to transfer ownership of the XML schema collection from one principal to another.</span></span>  
  
-   <span data-ttu-id="05a31-124">El permiso REFERENCES permite que la entidad de seguridad utilice la colección de esquemas XML para escribir o restringir columnas de tipo `xml` en tablas, vistas y parámetros.</span><span class="sxs-lookup"><span data-stu-id="05a31-124">The REFERENCES permission authorizes the principal to use the XML schema collection to type or constrain `xml` type columns, in tables and views and parameters.</span></span> <span data-ttu-id="05a31-125">El permiso REFERENCES también es necesario cuando una colección de esquemas XML hace referencia a otra.</span><span class="sxs-lookup"><span data-stu-id="05a31-125">The REFERENCES permission is also required when one XML schema collection refers to another.</span></span>  
  
-   <span data-ttu-id="05a31-126">El permiso VIEW DEFINITION permite que la entidad de seguridad consulte el contenido de una colección de esquemas XML a través de XML_SCHEMA_NAMESPACE o de las vistas de catálogo, siempre que esta entidad de seguridad tenga uno de los permisos ALTER, REFERENCES o CONTROL en la colección.</span><span class="sxs-lookup"><span data-stu-id="05a31-126">The VIEW DEFINITION permission allows the principal to query the contents of an XML schema collection either through XML_SCHEMA_NAMESPACE or through the catalog views, provided this principal also has one of the ALTER, REFERENCES, or CONTROL permissions on the collection.</span></span>  
  
-   <span data-ttu-id="05a31-127">El permiso EXECUTE es necesario para validar valores insertados o actualizados por la entidad de seguridad según la colección de esquemas XML que está escribiendo o restringiendo los parámetros, variables y columnas de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="05a31-127">The EXECUTE permission is required to validate values inserted or updated by the principal against the XML schema collection that is typing or constraining the `xml` type columns, variables, and parameters.</span></span> <span data-ttu-id="05a31-128">También necesita este permiso para consultar el XML almacenado en estas columnas y variables.</span><span class="sxs-lookup"><span data-stu-id="05a31-128">You also need this permission when you are querying the XML stored in these columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="05a31-129">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="05a31-129">Examples</span></span>  
 <span data-ttu-id="05a31-130">Los escenarios de los ejemplos siguientes ilustran el funcionamiento de los permisos de los esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-130">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="05a31-131">En cada ejemplo se crea la base de datos de prueba, los esquemas relacionales y los inicios de sesión necesarios.</span><span class="sxs-lookup"><span data-stu-id="05a31-131">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="05a31-132">A estos inicios de sesión se les conceden los permisos necesarios para la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-132">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="05a31-133">Al final, cada ejemplo realiza las operaciones de limpieza necesarias.</span><span class="sxs-lookup"><span data-stu-id="05a31-133">Each example does the necessary clean up at the end.</span></span>  
  
### <a name="a-granting-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="05a31-134">A.</span><span class="sxs-lookup"><span data-stu-id="05a31-134">A.</span></span> <span data-ttu-id="05a31-135">Conceder permisos para crear una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="05a31-135">Granting permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="05a31-136">El ejemplo siguiente muestra cómo conceder los permisos de tal forma que una entidad de seguridad pueda crear una colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-136">The following example shows how to grant permissions so that a principal can create an XML schema collection.</span></span> <span data-ttu-id="05a31-137">En el ejemplo, se crea una base de datos de ejemplo y un usuario de prueba, `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="05a31-137">The example creates a sample database and a test user, `TestLogin1`.</span></span> <span data-ttu-id="05a31-138">`TestLogin1` el permiso `ALTER` para el esquema relacional y el permiso `CREATE XML SCHEMA COLLECTION` para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05a31-138">`TestLogin1` is then given `ALTER` permission on the relational schema and given `CREATE XML SCHEMA COLLECTION` permission on the database.</span></span> <span data-ttu-id="05a31-139">Con estos permisos, `TestLogin1` crea correctamente una colección de esquemas XML de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="05a31-139">With these permissions, `TestLogin1` succeeds in creating a sample XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Execute CREATE XML SCHEMA COLLECTION.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="root" type="xsd:byte"/>  
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
  
### <a name="b-granting-permission-to-use-an-existing-xml-schema-collection"></a><span data-ttu-id="05a31-140">B.</span><span class="sxs-lookup"><span data-stu-id="05a31-140">B.</span></span> <span data-ttu-id="05a31-141">Conceder permisos para utilizar una colección de esquemas XML existente</span><span class="sxs-lookup"><span data-stu-id="05a31-141">Granting permission to use an existing XML schema collection</span></span>  
 <span data-ttu-id="05a31-142">El ejemplo siguiente muestra el modelo de permisos para la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-142">The following example further shows the permission model for the XML schema collection.</span></span> <span data-ttu-id="05a31-143">Ilustra los diferentes permisos que se necesitan para crear y utilizar la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-143">The example shows how different permissions are required to create and use the XML schema collection.</span></span>  
  
 <span data-ttu-id="05a31-144">En el ejemplo, se crea una base de datos de prueba y un inicio de sesión, `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="05a31-144">The example creates a test database and a login, `TestLogin1`.</span></span> <span data-ttu-id="05a31-145">`TestLogin1` crea una colección de esquemas XML en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05a31-145">`TestLogin1` creates an XML schema collection in the database.</span></span> <span data-ttu-id="05a31-146">El inicio de sesión crea una tabla y utiliza la colección de esquemas XML para crear una columna xml con tipo.</span><span class="sxs-lookup"><span data-stu-id="05a31-146">The login then creates a table and uses the XML schema collection to create a typed xml column.</span></span> <span data-ttu-id="05a31-147">A continuación, el usuario inserta los datos y los consulta.</span><span class="sxs-lookup"><span data-stu-id="05a31-147">The user then inserts data and queries it.</span></span> <span data-ttu-id="05a31-148">Todos estos pasos requieren los permisos de esquema necesarios que muestra el código.</span><span class="sxs-lookup"><span data-stu-id="05a31-148">All these steps require the necessary schema permissions, as shown in the code.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Create a table by using the collection to type an XML column.   
--TestLogin1 must have permission to create a table.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also must have REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- Now user can create a table and use the XML schema collection to create   
-- a typed XML column.  
SETUSER 'TestLogin1'  
GO  
CREATE TABLE MyTestTable (xmlCol xml (dbo.myTestSchemaCollection))  
GO  
-- To insert data in the table, the user needs EXECUTE permission on the XML schema collection.  
-- GRANT EXECUTE permission to TestLogin2 on the xml schema collection.  
SETUSER  
GO  
GRANT EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- TestLogin1 does not own the dbo schema. This user must have INSERT permission.  
GRANT INSERT TO TestLogin1  
GO  
-- Now the user can insert data into the table.  
SETUSER 'TestLogin1'  
GO  
INSERT INTO MyTestTable VALUES('  
<telephone xmlns="http://schemas.adventure-works.com/Additional/ContactInfo">111-1111</telephone>  
')  
GO  
-- To query the table, TestLogin1 must have permissions: SELECT on the table and EXECUTE on the XML schema collection.  
SETUSER  
GO  
GRANT SELECT TO TestLogin1  
GO  
-- TestLogin1 already has EXECUTE permission on the schema (granted before inserting a record in the table).  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- To show that the user must have EXECUTE permission to query, revoke the  
-- previously granted permission and return the query.  
SETUSER  
GO  
REVOKE EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection to TestLogin1  
Go  
-- Now TestLogin1 cannot execute the query.  
SETUSER 'TestLogin1'  
GO  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
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
  
### <a name="c-granting-alter-permission-on-an-xml-schema-collection"></a><span data-ttu-id="05a31-149">C.</span><span class="sxs-lookup"><span data-stu-id="05a31-149">C.</span></span> <span data-ttu-id="05a31-150">Conceder el permiso ALTER para una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="05a31-150">Granting ALTER permission on an XML schema collection</span></span>  
 <span data-ttu-id="05a31-151">Un usuario debe tener el permiso ALTER para modificar una colección de esquemas XML en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="05a31-151">A user must have ALTER permission to modify an existing XML schema collection in the database.</span></span> <span data-ttu-id="05a31-152">En el siguiente ejemplo se muestra cómo conceder el permiso `ALTER` .</span><span class="sxs-lookup"><span data-stu-id="05a31-152">The following example shows how to grant `ALTER` permission.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant ALTER permission to TestLogin1.  
setuser  
GO  
GRANT ALTER ON XML SCHEMA COLLECTION::myTestSchemaCollection TO TestLogin1  
GO  
-- TestLogin1 should be able to add components to the collection.  
SETUSER 'TestLogin1'  
GO  
ALTER XML SCHEMA COLLECTION myTestSchemaCollection ADD '  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns="http://schemas.adventure-works.com/Additional/ContactInfo"   
elementFormDefault="qualified">  
 <xsd:element name="pager" type="xsd:string"/>  
</xsd:schema>  
'  
Go  
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
  
### <a name="d-granting-take-ownership-permission-on-an-xml-schema-collection"></a><span data-ttu-id="05a31-153">D.</span><span class="sxs-lookup"><span data-stu-id="05a31-153">D.</span></span> <span data-ttu-id="05a31-154">Conceder el permiso TAKE OWNERSHIP en una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="05a31-154">Granting TAKE OWNERSHIP permission on an XML schema collection</span></span>  
 <span data-ttu-id="05a31-155">Este ejemplo muestra cómo se transfiere la propiedad del esquema XML de un usuario a otro.</span><span class="sxs-lookup"><span data-stu-id="05a31-155">The following example shows how to transfer XML schema ownership from one user to another.</span></span> <span data-ttu-id="05a31-156">Para hacer más interesante el ejemplo, los usuarios de este ejemplo trabajarán con diferentes esquemas relacionales predeterminados.</span><span class="sxs-lookup"><span data-stu-id="05a31-156">To make the example more interesting, the users in this example work in different default relational schemas.</span></span>  
  
 <span data-ttu-id="05a31-157">En el ejemplo, se realizan las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="05a31-157">This example does the following:</span></span>  
  
-   <span data-ttu-id="05a31-158">Se crea una base de datos con dos esquemas relacionales, `dbo` y `myOtherDBSchema`.</span><span class="sxs-lookup"><span data-stu-id="05a31-158">Creates a database with two relational schemas, `dbo` and `myOtherDBSchema`).</span></span>  
  
-   <span data-ttu-id="05a31-159">Se crean dos usuarios, `TestLogin1` y `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="05a31-159">Creates two users, `TestLogin1` and `TestLogin2`.</span></span> <span data-ttu-id="05a31-160">`TestLogin2` en el propietario del esquema relacional `myOtherDBSchema` .</span><span class="sxs-lookup"><span data-stu-id="05a31-160">`TestLogin2` is made the owner of the `myOtherDBSchema` relational schema.</span></span>  
  
-   <span data-ttu-id="05a31-161">`TestLogin1` crea una colección de esquemas relacionales XML en el esquema relacional `dbo` .</span><span class="sxs-lookup"><span data-stu-id="05a31-161">`TestLogin1` creates an XML schema collection in the `dbo` relational schema.</span></span>  
  
-   <span data-ttu-id="05a31-162">`TestLogin1` concede a `TAKE OWNERSHIP` el permiso `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="05a31-162">`TestLogin1` then gives `TAKE OWNERSHIP` permission on the XML schema collection to `TestLogin2`.</span></span>  
  
-   <span data-ttu-id="05a31-163">`TestLogin2` se convierte en el propietario de la colección de esquemas XML de `myOtherDBSchema`, sin cambiar el esquema relacional de la colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-163">`TestLogin2` becomes the owner of the XML schema collection in `myOtherDBSchema`, without changing the relational schema of the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 with password='SQLSvrPwd1'  
GO  
CREATE LOGIN TestLogin2 with password='SQLSvrPwd2'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
-- Create users in the database. Note TestLogin2's default schema is  
-- myOtherDBSchema.  
CREATE USER TestLogin1  
GO  
CREATE USER TestLogin2 WITH DEFAULT_SCHEMA=myOtherDBSchema  
GO  
-- TestLogin2 will own myOtherDBSchema relational schema.  
ALTER AUTHORIZATION ON SCHEMA::myOtherDBSchema TO TestLogin2  
GO  
  
-- For TestLogin1 to create XML schema collection, the following  
-- permission is required.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- Now TestLogin1 can create an XML schema collection.  
setuser 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
 <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"   
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
 </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Grant TAKE OWNERSHIP to TestLogin2.  
SETUSER  
GO  
GRANT TAKE OWNERSHIP ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Verify the owner. Note the UserName and Principal_id is null.   
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections   
      JOIN sys.schemas   
      ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- TestLogin2 can take ownership now.  
setuser 'TestLogin2'  
GO  
ALTER AUTHORIZATION ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Note that although TestLogin2 is the owner,the XML schema collection   
-- is still in dbo.  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
      sys.schemas.name as RelSchemaName,*   
FROM sys.xml_schema_collections JOIN sys.schemas   
     ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
  
-- TestLogin2 moves the collection from dbo to myOtherDBSchema relational schema.  
-- TestLogin2 already has all necessary permissions.  
-- 1) TestLogin2 owns the destination relational schema so he can alter it.  
-- 2) TestLogin2 owns the XML schema collection (therefore, has CONTROL permission).  
ALTER SCHEMA myOtherDBSchema  
TRANSFER XML SCHEMA COLLECTION::dbo.myTestSchemaCollection  
GO  
  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections JOIN sys.schemas   
       ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
DROP LOGIN TestLogin2  
go   
```  
  
### <a name="e-granting-view-definition-permission-on-an-xml-schema-collection"></a><span data-ttu-id="05a31-164">E.</span><span class="sxs-lookup"><span data-stu-id="05a31-164">E.</span></span> <span data-ttu-id="05a31-165">Conceder el permiso VIEW DEFINITION para una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="05a31-165">Granting VIEW DEFINITION permission on an XML schema collection</span></span>  
 <span data-ttu-id="05a31-166">En el ejemplo siguiente se muestra cómo conceder permisos VIEW DEFINITION para una colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="05a31-166">The following example shows how to grant VIEW DEFINITION permissions for an XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
IF EXISTS( SELECT * FROM sysdatabases WHERE name='permissionsDB' )  
   DROP DATABASE permissionsDB  
GO  
IF EXISTS( SELECT * FROM sys.sql_logins WHERE name='schemaUser' )  
   DROP LOGIN schemaUser  
GO  
CREATE DATABASE permissionsDB  
GO  
CREATE LOGIN schemaUser WITH PASSWORD='Pass#123',DEFAULT_DATABASE=permissionsDB  
GO  
GRANT CONNECT SQL TO schemaUser  
GO  
USE permissionsDB  
GO  
CREATE USER schemaUser WITH DEFAULT_SCHEMA=dbo  
GO  
CREATE XML SCHEMA COLLECTION MySC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns"  
xmlns:ns="http://ns">  
  
   <simpleType name="ListOfIntegers">  
      <list itemType="integer"/>  
   </simpleType>  
  
   <element name="root" type="ns:ListOfIntegers"/>  
  
   <element name="gRoot" type="gMonth"/>  
  
</schema>  
'  
GO  
-- schemaUser cannot see the contents of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
  
-- Grant schemaUser VIEW DEFINITION and REFERENCES permissions  
-- on the XML schema collection.  
SETUSER  
GO  
GRANT VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
GRANT REFERENCES ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
-- Now schemaUser can see the content of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
-- Revoke schemaUser VIEW DEFINITION permissions  
-- on the XML schema collection.  
SETUSER  
GO  
REVOKE VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC FROM schemaUser  
GO  
-- Now schemaUser cannot see the contents of   
-- the collection.  
setuser 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="05a31-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05a31-167">See Also</span></span>  
 <span data-ttu-id="05a31-168">[Datos XML &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="05a31-168">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="05a31-169">[Comparar XML con tipo y XML sin tipo](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="05a31-169">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="05a31-170">[Colecciones de esquemas XML &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="05a31-170">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="05a31-171">Requisitos y limitaciones de las colecciones de esquemas XML en el servidor</span><span class="sxs-lookup"><span data-stu-id="05a31-171">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
