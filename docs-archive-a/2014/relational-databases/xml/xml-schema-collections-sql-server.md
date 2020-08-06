---
title: Colecciones de esquemas XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- xml_schema_namespace function
- XML schema collections [SQL Server], about XML schema collections
- metadata [SQL Server], XML schema collections
- queries [XML in SQL Server], XML schema collections
- schema collections [SQL Server]
- schemas [SQL Server], XML
- XML [SQL Server], schema collections
- XML schema collections [SQL Server]
- schema collections [SQL Server], about XML schema collections
ms.assetid: 659d41aa-ccec-4554-804a-722a96ef25c2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ee4757f1353278447ee55e97c8d4ba23aa2d649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674669"
---
# <a name="xml-schema-collections-sql-server"></a><span data-ttu-id="be025-102">Colecciones de esquemas XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="be025-102">XML Schema Collections (SQL Server)</span></span>
  <span data-ttu-id="be025-103">Tal y como se describe en el tema [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server proporciona almacenamiento nativo de datos XML a través del `xml` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-103">As described in the topic, [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server provides native storage of XML data through the `xml` data type.</span></span> <span data-ttu-id="be025-104">Opcionalmente, puede asociar esquemas XSD a una variable o una columna de `xml` tipo a través de una colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="be025-104">You can optionally associate XSD schemas with a variable or a column of `xml` type through an XML schema collection.</span></span> <span data-ttu-id="be025-105">Esta colección almacena los esquemas XML importados y luego se usa para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="be025-105">The XML schema collection stores the imported XML schemas and is then used to do the following:</span></span>  
  
-   <span data-ttu-id="be025-106">Validar instancias XML</span><span class="sxs-lookup"><span data-stu-id="be025-106">Validate XML instances</span></span>  
  
-   <span data-ttu-id="be025-107">Asignar un tipo a los datos XML cuando se almacenan en la base de datos</span><span class="sxs-lookup"><span data-stu-id="be025-107">Type the XML data as it is stored in the database</span></span>  
  
 <span data-ttu-id="be025-108">Tenga en cuenta que la colección de esquemas XML es una entidad de metadatos como una tabla de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-108">Note that the XML schema collection is a metadata entity like a table in the database.</span></span> <span data-ttu-id="be025-109">Se pueden crear, modificar y arrastrar.</span><span class="sxs-lookup"><span data-stu-id="be025-109">You can create, modify, and drop them.</span></span> <span data-ttu-id="be025-110">Los esquemas especificados en una instrucción [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) se importan automáticamente en el objeto de la colección de esquemas XML recién creado.</span><span class="sxs-lookup"><span data-stu-id="be025-110">Schemas specified in a [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) statement are automatically imported into the newly created XML schema collection object.</span></span> <span data-ttu-id="be025-111">Se pueden importar otros esquemas o componentes de esquemas en un objeto de la colección existente de la base de datos usando la instrucción [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="be025-111">You can import additional schemas or schema components into an existing collection object in the database by using the [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="be025-112">Como se describe en el tema [Comparar XML con tipo y XML sin tipo](../xml/compare-typed-xml-to-untyped-xml.md), el XML almacenado en una columna o variable al que está asociado un esquema se conoce como XML **con tipo**, porque el esquema indica la información del tipo de datos necesaria para los datos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="be025-112">As described in the topic, [Typed vs. Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md), the XML stored in a column or variable that a schema is associated with is referred to as **typed** XML, because the schema provides the necessary data type information for the instance data.</span></span> <span data-ttu-id="be025-113">SQL Server usa esta información del tipo para optimizar el almacenamiento de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-113">SQL Server uses this type information to optimize data storage.</span></span>  
  
 <span data-ttu-id="be025-114">El motor de procesamiento de consultas también usa el esquema para la comprobación de los tipos y para optimizar las consultas y la modificación de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-114">The query-processing engine also uses the schema for type checking and to optimize queries and data modification.</span></span>  
  
 <span data-ttu-id="be025-115">Además, SQL Server utiliza la colección de esquemas XML asociada, en el caso de con tipo `xml` , para validar la instancia XML.</span><span class="sxs-lookup"><span data-stu-id="be025-115">Also, SQL Server uses the associated XML schema collection, in the case of typed `xml`, to validate the XML instance.</span></span> <span data-ttu-id="be025-116">Si la instancia XML es compatible con el esquema, la base de datos permite que se almacene la instancia en el sistema con su información de tipos.</span><span class="sxs-lookup"><span data-stu-id="be025-116">If the XML instance complies with the schema, the database allows the instance to be stored in the system with their type information.</span></span> <span data-ttu-id="be025-117">De lo contrario, rechaza la instancia.</span><span class="sxs-lookup"><span data-stu-id="be025-117">Otherwise, it rejects the instance.</span></span>  
  
 <span data-ttu-id="be025-118">Se puede usar la función intrínseca XML_SCHEMA_NAMESPACE para recuperar la colección de esquemas que está almacenada en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-118">You can use the intrinsic function XML_SCHEMA_NAMESPACE to retrieve the schema collection that is stored in the database.</span></span> <span data-ttu-id="be025-119">Para obtener más información, vea [Ver una colección de esquemas XML almacenada](../xml/view-a-stored-xml-schema-collection.md).</span><span class="sxs-lookup"><span data-stu-id="be025-119">For more information, see [View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md).</span></span>  
  
 <span data-ttu-id="be025-120">También puede usar la colección de esquemas XML para escribir variables, parámetros y columnas XML.</span><span class="sxs-lookup"><span data-stu-id="be025-120">You can also use the XML schema collection to type XML variables, parameters, and columns.</span></span>  
  
##  <a name="ddl-for-managing-schema-collections"></a><a name="ddl"></a> <span data-ttu-id="be025-121">DDL para administrar colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="be025-121">DDL for Managing Schema Collections</span></span>  
 <span data-ttu-id="be025-122">Se pueden crear colecciones de esquemas XML en la base de datos y asociarlas a variables y columnas de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="be025-122">You can create XML schema collections in the database and associate them with variables and columns of `xml` type.</span></span> <span data-ttu-id="be025-123">Para administrar las colecciones de esquemas de la base de datos, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] proporciona las siguientes instrucciones DDL:</span><span class="sxs-lookup"><span data-stu-id="be025-123">To manage schema collections in the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following DDL statements:</span></span>  
  
-   <span data-ttu-id="be025-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Importa los componentes del esquema en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Imports schema components into a database.</span></span>  
  
-   <span data-ttu-id="be025-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifica los componentes de esquema en una colección de esquemas XML existente.</span><span class="sxs-lookup"><span data-stu-id="be025-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifies the schema components in an existing XML schema collection.</span></span>  
  
-   <span data-ttu-id="be025-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Elimina toda la colección de esquemas XML y todos sus componentes.</span><span class="sxs-lookup"><span data-stu-id="be025-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Deletes a complete XML schema collection and all its components.</span></span>  
  
 <span data-ttu-id="be025-127">Para utilizar una colección de esquemas XML y los esquemas que contiene, primero es necesario crear la colección y los esquemas mediante la instrucción CREATE XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="be025-127">To use an XML schema collection and the schemas it contains, you must first create the collection and the schemas by using the CREATE XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="be025-128">Una vez creada la colección de esquemas, se pueden crear variables y columnas de tipo `xml` y asociarles la colección.</span><span class="sxs-lookup"><span data-stu-id="be025-128">After the schema collection is created, you can then create variables and columns of `xml` type and associate the schema collection with them.</span></span> <span data-ttu-id="be025-129">Tenga en cuenta que, después de crear una colección de esquemas, varios componentes de esquema se almacenan en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="be025-129">Note that after a schema collection is created, various schema components are stored in the metadata.</span></span> <span data-ttu-id="be025-130">Se puede utilizar también ALTER XML SCHEMA COLLECTION para agregar más componentes a los esquemas existentes o agregar esquemas nuevos a la colección.</span><span class="sxs-lookup"><span data-stu-id="be025-130">You can also use the ALTER XML SCHEMA COLLECTION to add more components to the existing schemas or add new schemas to an existing collection.</span></span>  
  
 <span data-ttu-id="be025-131">Para quitar la colección de esquemas, utilice la instrucción DROP XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="be025-131">To drop the schema collection, use the DROP XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="be025-132">Se quitarán todos los esquemas contenidos en la colección, así como el objeto de colección.</span><span class="sxs-lookup"><span data-stu-id="be025-132">This drops all schemas that are contained in the collection and removes the collection object.</span></span> <span data-ttu-id="be025-133">Tenga en cuenta que, para quitar una colección de esquemas, deben cumplirse las condiciones descritas en [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="be025-133">Note that before you can drop a schema collection, the conditions described in [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql)must be met.</span></span>  
  
##  <a name="understanding-schema-components"></a><a name="components"></a> <span data-ttu-id="be025-134">Descripción de los componentes de esquema</span><span class="sxs-lookup"><span data-stu-id="be025-134">Understanding Schema Components</span></span>  
 <span data-ttu-id="be025-135">Cuando se utiliza la instrucción CREATE XML SCHEMA COLLECTION, se importan varios componentes de esquema a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-135">When you use the CREATE XML SCHEMA COLLECTION statement, various schema components are imported into the database.</span></span> <span data-ttu-id="be025-136">Los componentes de esquema son los elementos de esquema, los atributos y las definiciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="be025-136">Schema components include schema elements, attributes, and type definitions.</span></span> <span data-ttu-id="be025-137">Cuando se utiliza la instrucción DROP XML SCHEMA COLLECTION, se quita toda la colección.</span><span class="sxs-lookup"><span data-stu-id="be025-137">When you use the DROP XML SCHEMA COLLECTION statement, you remove the complete collection.</span></span>  
  
 <span data-ttu-id="be025-138">CREATE XML SCHEMA COLLECTION guarda los componentes de esquema en varias tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="be025-138">CREATE XML SCHEMA COLLECTION saves the schema components into various system tables.</span></span>  
  
 <span data-ttu-id="be025-139">Considere, por ejemplo, el siguiente esquema:</span><span class="sxs-lookup"><span data-stu-id="be025-139">For example, consider the following schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            targetNamespace="uri:Cust_Orders2"  
            xmlns="uri:Cust_Orders2" >  
  <xsd:attribute name="SomeAttribute" type="xsd:int" />  
  <xsd:complexType name="SomeType" />  
  <xsd:complexType name="OrderType" >  
    <xsd:sequence>  
      <xsd:element name="OrderDate" type="xsd:date" />  
      <xsd:element name="RequiredDate" type="xsd:date" />  
      <xsd:element name="ShippedDate" type="xsd:date" />  
    </xsd:sequence>  
    <xsd:attribute name="OrderID" type="xsd:ID" />  
    <xsd:attribute name="CustomerID"  />  
    <xsd:attribute name="EmployeeID"  />  
  </xsd:complexType>  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order" type="OrderType"  
                     maxOccurs="unbounded" />  
       </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
      <xsd:attribute name="OrderIDList" type="xsd:IDREFS" />  
  </xsd:complexType>  
  <xsd:element name="Customer" type="CustomerType" />  
</xsd:schema>  
```  
  
 <span data-ttu-id="be025-140">El esquema anterior muestra los distintos tipos de componentes que se pueden almacenar en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-140">The previous schema shows the different types of components that can be stored in the database.</span></span> <span data-ttu-id="be025-141">Incluyen `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`y `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="be025-141">These include `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`, and `ShippedDate`.</span></span>  
  
### <a name="component-categories"></a><span data-ttu-id="be025-142">Categorías del componente</span><span class="sxs-lookup"><span data-stu-id="be025-142">Component Categories</span></span>  
 <span data-ttu-id="be025-143">Los componentes de esquema que se almacenan en la base de datos se incluyen en estas categorías:</span><span class="sxs-lookup"><span data-stu-id="be025-143">The Schema components stored in the database fall into the following categories:</span></span>  
  
-   <span data-ttu-id="be025-144">ELEMENT</span><span class="sxs-lookup"><span data-stu-id="be025-144">ELEMENT</span></span>  
  
-   <span data-ttu-id="be025-145">ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="be025-145">ATTRIBUTE</span></span>  
  
-   <span data-ttu-id="be025-146">TYPE (para tipos simples o complejos)</span><span class="sxs-lookup"><span data-stu-id="be025-146">TYPE (for simple or complex types)</span></span>  
  
-   <span data-ttu-id="be025-147">ATTRIBUTEGROUP</span><span class="sxs-lookup"><span data-stu-id="be025-147">ATTRIBUTEGROUP</span></span>  
  
-   <span data-ttu-id="be025-148">MODELGROUP</span><span class="sxs-lookup"><span data-stu-id="be025-148">MODELGROUP</span></span>  
  
 <span data-ttu-id="be025-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="be025-149">For example:</span></span>  
  
-   <span data-ttu-id="be025-150">**SomeAttribute** es un componente ATTRIBUTE.</span><span class="sxs-lookup"><span data-stu-id="be025-150">**SomeAttribute** is an ATTRIBUTE component.</span></span>  
  
-   <span data-ttu-id="be025-151">**SomeType**, **OrderType**y **CustomerType** son componentes TYPE.</span><span class="sxs-lookup"><span data-stu-id="be025-151">**SomeType**, **OrderType**, and **CustomerType** are TYPE components.</span></span>  
  
-   <span data-ttu-id="be025-152">**Customer** es un componente ELEMENT.</span><span class="sxs-lookup"><span data-stu-id="be025-152">**Customer** is an ELEMENT component.</span></span>  
  
 <span data-ttu-id="be025-153">Cuando se importa un esquema a la base de datos, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no almacena el propio esquema.</span><span class="sxs-lookup"><span data-stu-id="be025-153">When you import a schema into the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not store the schema itself.</span></span> <span data-ttu-id="be025-154">En su lugar, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] almacena sus distintos componentes individuales.</span><span class="sxs-lookup"><span data-stu-id="be025-154">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stores the various individual components.</span></span> <span data-ttu-id="be025-155">En otras palabras, no se almacena la etiqueta \<Schema>, sino que solo se conservan los componentes definidos en ella.</span><span class="sxs-lookup"><span data-stu-id="be025-155">That is, the \<Schema> tag is not stored, only the components that are defined within it are preserved.</span></span> <span data-ttu-id="be025-156">No se conservan todos los elementos del esquema.</span><span class="sxs-lookup"><span data-stu-id="be025-156">All schema elements are not preserved.</span></span> <span data-ttu-id="be025-157">Si la etiqueta \<Schema> contiene atributos que especifican el comportamiento predeterminado de sus componentes, estos atributos se trasladan a esos componentes de esquema durante el proceso de importación, como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="be025-157">If the \<Schema> tag contains attributes that specify default behavior of its components, these attributes are moved to the schema components within it during the import process, as shown in the following table.</span></span>  
  
|<span data-ttu-id="be025-158">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="be025-158">Attribute name</span></span>|<span data-ttu-id="be025-159">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="be025-159">Behavior</span></span>|  
|--------------------|--------------|  
|<span data-ttu-id="be025-160">**attributeFormDefault**</span><span class="sxs-lookup"><span data-stu-id="be025-160">**attributeFormDefault**</span></span>|<span data-ttu-id="be025-161">El atributo **form** se aplica a todas las declaraciones de atributo del esquema donde todavía no está presente y el valor se establece en el valor del atributo **attributeFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="be025-161">The **form** attribute applied to all attribute declarations in the schema where it is not already present and the value is set to the value of the **attributeFormDefault** attribute.</span></span>|  
|<span data-ttu-id="be025-162">**elementFormDefault**</span><span class="sxs-lookup"><span data-stu-id="be025-162">**elementFormDefault**</span></span>|<span data-ttu-id="be025-163">El atributo **form** se aplica a todas las declaraciones de elemento del esquema donde todavía no está presente y el valor se establece en el valor del atributo **elementFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="be025-163">The **form** attribute applied to all element declarations in the schema where it is not already present and the value is set to the value of the **elementFormDefault** attribute.</span></span>|  
|<span data-ttu-id="be025-164">**blockDefault**</span><span class="sxs-lookup"><span data-stu-id="be025-164">**blockDefault**</span></span>|<span data-ttu-id="be025-165">El atributo **block** se aplica a todas las declaraciones de elemento y definiciones de tipo donde todavía no está presente y el valor se establece en el valor del atributo **blockDefault** .</span><span class="sxs-lookup"><span data-stu-id="be025-165">The **block** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **blockDefault** attribute.</span></span>|  
|<span data-ttu-id="be025-166">**finalDefault**</span><span class="sxs-lookup"><span data-stu-id="be025-166">**finalDefault**</span></span>|<span data-ttu-id="be025-167">El atributo **final** se aplica a todas las declaraciones de elemento y definiciones de tipo donde todavía no está presente y el valor se establece en el valor del atributo **finalDefault** .</span><span class="sxs-lookup"><span data-stu-id="be025-167">The **final** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **finalDefault** attribute.</span></span>|  
|<span data-ttu-id="be025-168">**targetNamespace**</span><span class="sxs-lookup"><span data-stu-id="be025-168">**targetNamespace**</span></span>|<span data-ttu-id="be025-169">La información acerca de los componentes que pertenecen al espacio de nombres de destino se almacena en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="be025-169">Information about the components that belong to the target namespace is stored in the metadata.</span></span>|  
  
##  <a name="permissions-on-an-xml-schema-collection"></a><a name="perms"></a> <span data-ttu-id="be025-170">Permisos en una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-170">Permissions on an XML Schema Collection</span></span>  
 <span data-ttu-id="be025-171">Deberá tener los permisos necesarios para realizar las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="be025-171">You must have the necessary permissions to do the following:</span></span>  
  
-   <span data-ttu-id="be025-172">Crear o cargar la colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-172">Create/load the XML schema collection</span></span>  
  
-   <span data-ttu-id="be025-173">Modificar la colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-173">Modify the XML schema collection</span></span>  
  
-   <span data-ttu-id="be025-174">Quitar la colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-174">Drop the XML schema collection</span></span>  
  
-   <span data-ttu-id="be025-175">Usar la colección de esquemas XML para escribir `xml` tipos de columnas, variables y parámetros, o para utilizarlos en restricciones de tabla o columna</span><span class="sxs-lookup"><span data-stu-id="be025-175">Use the XML schema collection to type `xml` type columns, variables, and parameters, or use it in table or column constraints</span></span>  
  
 <span data-ttu-id="be025-176">El modelo de seguridad de SQL Server concede el permiso CONTROL para todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="be025-176">The SQL Server security model allows CONTROL permission on every object.</span></span> <span data-ttu-id="be025-177">El receptor de este permiso obtiene todos los demás permisos para el objeto.</span><span class="sxs-lookup"><span data-stu-id="be025-177">The grantee of this permission obtains all other permissions on the object.</span></span> <span data-ttu-id="be025-178">El propietario del objeto también dispone de todos los permisos para el objeto.</span><span class="sxs-lookup"><span data-stu-id="be025-178">The owner of the object also has all the permissions on the object.</span></span>  
  
 <span data-ttu-id="be025-179">El propietario y el receptor del permiso CONTROL para un objeto puede conceder cualquier permiso para ese objeto.</span><span class="sxs-lookup"><span data-stu-id="be025-179">The owner and the grantee of the CONTROL permission on an object can grant any permission on the object.</span></span> <span data-ttu-id="be025-180">Un usuario que no sea el propietario del objeto ni disponga del permiso CONTROL todavía puede conceder permisos para un objeto si se especifica WITH GRANT OPTION.</span><span class="sxs-lookup"><span data-stu-id="be025-180">A user who is not the owner and does not have CONTROL permission can still grant permission on an object when WITH GRANT OPTION is specified.</span></span> <span data-ttu-id="be025-181">Supongamos, por ejemplo, que el usuario A tiene permiso REFERENCES en la colección de esquemas XML S, por medio de WITH GRANT OPTION, pero no posee ningún otro permiso en S. El usuario A podría conceder el permiso REFERENCES para la colección de esquemas S al usuario B.</span><span class="sxs-lookup"><span data-stu-id="be025-181">For example, assume User A has REFERENCES permission on XML schema collection S, through WITH GRANT OPTION, but no other permissions on S. User A could grant User B REFERENCES permission on schema collection S.</span></span>  
  
 <span data-ttu-id="be025-182">El modelo de seguridad también otorga permisos para crear y utilizar colecciones de esquemas XML o transferir la propiedad de un usuario a otro.</span><span class="sxs-lookup"><span data-stu-id="be025-182">The security model also allows permissions to create and use XML schema collections or transfer ownership from one user to another.</span></span> <span data-ttu-id="be025-183">En los temas siguientes se describen los permisos de las colecciones de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="be025-183">The following topics describe the XML schema collection permissions.</span></span>  
  
-   [<span data-ttu-id="be025-184">Conceder permisos para una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-184">Grant Permissions on an XML Schema Collection</span></span>](../xml/grant-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="be025-185">Este tema explica cómo conceder permisos para crear una colección de esquemas XML y cómo conceder permisos para un objeto de colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="be025-185">This topic discussess how to grant permissions to create an XML schema collection and how to grant permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="be025-186">Revocar los permisos en una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-186">Revoke Permissions on an XML Schema Collection</span></span>](../xml/revoke-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="be025-187">Este tema explica cómo se pueden revocar permisos para impedir la creación de una colección de esquemas XML y cómo revocar los permisos en un objeto de colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="be025-187">This topic discusses how revoking permissions can be used to prevent the creation of an XML schema collection and how to revoke permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="be025-188">Denegar permisos en una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-188">Deny Permissions on an XML Schema Collection</span></span>](../xml/deny-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="be025-189">Este tema explica cómo negar permisos para crear una colección de esquemas XML y cómo negar los permisos en un objeto de colección de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="be025-189">This topic discusses how to deny permissions to create an XML schema collection and deny permission on an XML schema collection object.</span></span>  
  
##  <a name="getting-information-about-xml-schemas-and-schema-collections"></a><a name="info"></a> <span data-ttu-id="be025-190">Obtener información acerca de los esquemas XML y las colecciones de esquemas</span><span class="sxs-lookup"><span data-stu-id="be025-190">Getting Information about XML Schemas and Schema Collections</span></span>  
 <span data-ttu-id="be025-191">Las colecciones de esquemas XML se enumeran en la vista de catálogo sys.xml_schema_collections.</span><span class="sxs-lookup"><span data-stu-id="be025-191">XML schema collections are enumerated in the catalog view, sys.xml_schema_collections.</span></span> <span data-ttu-id="be025-192">La colección de esquemas XML "sys" la define el sistema.</span><span class="sxs-lookup"><span data-stu-id="be025-192">The XML schema collection "sys" is defined by the system.</span></span> <span data-ttu-id="be025-193">Contiene los espacios de nombres predefinidos que se pueden usar en todas las colecciones de esquemas XML definidas por el usuario, sin tener que cargarlos explícitamente.</span><span class="sxs-lookup"><span data-stu-id="be025-193">It contains the predefined namespaces that can be used in all user-defined XML schema collections without having to load them explicitly.</span></span> <span data-ttu-id="be025-194">Esta lista contiene los espacios de nombres para xml, xs, xsi, fn y xdt.</span><span class="sxs-lookup"><span data-stu-id="be025-194">This list contains the namespaces for xml, xs, xsi, fn, and xdt.</span></span> <span data-ttu-id="be025-195">Otras dos vistas de catálogo son sys.xml_schema_namespaces, que enumera todos los espacios de nombres incluidos en una colección de esquemas XML, y sys.xml_components, que enumera todos los componentes de esquemas XML dentro de cada esquema XML.</span><span class="sxs-lookup"><span data-stu-id="be025-195">Two other catalog views are sys.xml_schema_namespaces, which enumerates all namespaces within each XML schema collection, and sys.xml_components, which enumerates all XML schema components within each XML schema.</span></span>  
  
 <span data-ttu-id="be025-196">La función integrada **XML_SCHEMA_NAMESPACE**, *schemaName, XmlSchemacollectionName, namespace-uri*, produce una `xml` instancia de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="be025-196">The built-in function **XML_SCHEMA_NAMESPACE**, *schemaName, XmlSchemacollectionName, namespace-uri*, yields an `xml` data type instance..</span></span> <span data-ttu-id="be025-197">Esta instancia contiene fragmentos de esquemas XML correspondientes a esquemas incluidos en una colección de esquemas XML, excepto los esquemas XML predefinidos.</span><span class="sxs-lookup"><span data-stu-id="be025-197">This instance contains XML schema fragments for schemas that are contained in an XML schema collection, except the predefined XML schemas.</span></span>  
  
 <span data-ttu-id="be025-198">Puede enumerar el contenido de una colección de esquemas XML de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="be025-198">You can enumerate the contents of an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="be025-199">Escriba consultas Transact-SQL sobre las vistas de catálogo apropiadas para colecciones de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="be025-199">Write Transact-SQL queries on the appropriate catalog views for XML schema collections.</span></span>  
  
-   <span data-ttu-id="be025-200">Use la función integrada **XML_SCHEMA_NAMESPACE()** .</span><span class="sxs-lookup"><span data-stu-id="be025-200">Use the built-in function **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="be025-201">Puede aplicar `xml` métodos de tipo de datos en la salida de esta función.</span><span class="sxs-lookup"><span data-stu-id="be025-201">You can apply `xml` data type methods on the output of this function.</span></span> <span data-ttu-id="be025-202">Sin embargo, no puede modificar los esquemas XML subyacentes.</span><span class="sxs-lookup"><span data-stu-id="be025-202">However, you cannot modify the underlying XML schemas.</span></span>  
  
 <span data-ttu-id="be025-203">Los ejemplos siguientes ilustran lo comentado.</span><span class="sxs-lookup"><span data-stu-id="be025-203">These are illustrated in the following examples.</span></span>  
  
### <a name="example-enumerate-the-xml-namespaces-in-an-xml-schema-collection"></a><span data-ttu-id="be025-204">Ejemplo: Enumerar los espacios de nombres XML en una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-204">Example: Enumerate the XML Namespaces in an XML Schema Collection</span></span>  
 <span data-ttu-id="be025-205">Use la siguiente consulta para la colección de esquemas XML "myCollection".</span><span class="sxs-lookup"><span data-stu-id="be025-205">Use the following query for the XML schema collection "myCollection":</span></span>  
  
```  
SELECT XSN.name  
FROM    sys.xml_schema_collections XSC JOIN sys.xml_schema_namespaces XSN  
    ON (XSC.xml_collection_id = XSN.xml_collection_id)  
WHERE    XSC.name = 'myCollection'     
```  
  
### <a name="example-enumerate-the-contents-of-an-xml-schema-collection"></a><span data-ttu-id="be025-206">Ejemplo: Enumerar el contenido de una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-206">Example: Enumerate the Contents of an XML Schema Collection</span></span>  
 <span data-ttu-id="be025-207">La instrucción siguiente enumera el contenido de la colección de esquemas XML "myCollection" dentro del esquema relacional dbo.</span><span class="sxs-lookup"><span data-stu-id="be025-207">The following statement enumerates the contents of the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection')  
```  
  
 <span data-ttu-id="be025-208">Los esquemas XML individuales de la colección se pueden obtener como `xml` instancias de tipo de datos especificando el espacio de nombres de destino como tercer argumento para **XML_SCHEMA_NAMESPACE ()**.</span><span class="sxs-lookup"><span data-stu-id="be025-208">Individual XML schemas within the collection can be obtained as `xml` data type instances by specifying the target namespace as the third argument to **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="be025-209">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="be025-209">This is shown in the following example.</span></span>  
  
### <a name="example-output-a-specified-schema-from-an-xml-schema-collection"></a><span data-ttu-id="be025-210">Ejemplo: Obtener un esquema especificado a partir de una colección de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-210">Example: Output a Specified Schema from an XML Schema Collection</span></span>  
 <span data-ttu-id="be025-211">La instrucción siguiente genera como resultado el esquema XML con el espacio de nombres de destino "<https://www.microsoft.com/books>" a partir de la colección de esquemas XML "myCollection" dentro del esquema relacional dbo.</span><span class="sxs-lookup"><span data-stu-id="be025-211">The following statement outputs the XML schema with the target namespace "<https://www.microsoft.com/books>" from the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection',   
N'https://www.microsoft.com/books')  
```  
  
### <a name="querying-xml-schemas"></a><span data-ttu-id="be025-212">Consultar esquemas XML</span><span class="sxs-lookup"><span data-stu-id="be025-212">Querying XML Schemas</span></span>  
 <span data-ttu-id="be025-213">Los siguientes procedimientos permiten consultar esquemas XML que se hayan cargado en colecciones de esquemas XML:</span><span class="sxs-lookup"><span data-stu-id="be025-213">You can query XML schemas that you have loaded into XML schema collections in the following ways:</span></span>  
  
-   <span data-ttu-id="be025-214">Escriba consultas Transact-SQL sobre vistas de catálogo para espacios de nombres de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="be025-214">Write Transact-SQL queries on catalog views for XML schema namespaces.</span></span>  
  
-   <span data-ttu-id="be025-215">Cree una tabla que contenga una columna de tipo de datos `xml` para almacenar los esquemas XML y también cargarlos en el sistema de tipo XML.</span><span class="sxs-lookup"><span data-stu-id="be025-215">Create a table that contains an `xml` data type column to store your XML schemas and also load them into the XML type system.</span></span> <span data-ttu-id="be025-216">Puede consultar la columna XML mediante los métodos de tipo de datos `xml`.</span><span class="sxs-lookup"><span data-stu-id="be025-216">You can query the XML column by using the `xml` data type methods.</span></span> <span data-ttu-id="be025-217">Además, puede crear un índice XML en esta columna.</span><span class="sxs-lookup"><span data-stu-id="be025-217">Also, you can build an XML index on this column.</span></span> <span data-ttu-id="be025-218">Sin embargo, con este enfoque, la aplicación debe mantener la coherencia entre los esquemas XML almacenados en la columna XML y el sistema de tipo XML.</span><span class="sxs-lookup"><span data-stu-id="be025-218">However, with this approach, the application must maintain consistency between the XML schemas stored in the XML column and the XML type system.</span></span> <span data-ttu-id="be025-219">Por ejemplo, si se quita el espacio de nombres de esquemas XML del sistema de tipo XML, también se tiene que quitar de la tabla para preservar la coherencia.</span><span class="sxs-lookup"><span data-stu-id="be025-219">For example, if you drop the XML schema namespace from the XML type system, you also have to drop it from the table in order to preserve consistency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be025-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="be025-220">See Also</span></span>  
 <span data-ttu-id="be025-221">[Ver una colección de esquemas XML almacenada](../xml/view-a-stored-xml-schema-collection.md) </span><span class="sxs-lookup"><span data-stu-id="be025-221">[View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md) </span></span>  
 <span data-ttu-id="be025-222">[Preprocesar un esquema para combinar esquemas incluidos](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="be025-222">[Preprocess a Schema to Merge Included Schemas](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span></span>  
 [<span data-ttu-id="be025-223">Requisitos y limitaciones de las colecciones de esquemas XML en el servidor</span><span class="sxs-lookup"><span data-stu-id="be025-223">Requirements and Limitations for XML Schema Collections on the Server</span></span>](../xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
