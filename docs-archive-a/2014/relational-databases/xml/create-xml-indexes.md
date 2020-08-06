---
title: Creación de índices XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- indexes [XML in SQL Server]
- XML indexes [SQL Server], creating
ms.assetid: 6ecac598-355d-4408-baf7-1b2e8d4cf7c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9e7800193222b8c9060fee1b247cc5585654cde4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748683"
---
# <a name="create-xml-indexes"></a><span data-ttu-id="2bb20-102">Crear índices XML</span><span class="sxs-lookup"><span data-stu-id="2bb20-102">Create XML Indexes</span></span>
  <span data-ttu-id="2bb20-103">En este tema se describe cómo crear índices XML principales y secundarios.</span><span class="sxs-lookup"><span data-stu-id="2bb20-103">This topic describes how to create primary and secondary XML indexes.</span></span>  
  
## <a name="creating-a-primary-xml-index"></a><span data-ttu-id="2bb20-104">Crear un índice XML principal</span><span class="sxs-lookup"><span data-stu-id="2bb20-104">Creating a Primary XML Index</span></span>  
 <span data-ttu-id="2bb20-105">Para crear un índice XML principal, use la instrucción DDL [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bb20-105">To create a primary XML index, use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement.</span></span> <span data-ttu-id="2bb20-106">Los índices XML no admiten todas las opciones que están disponibles para índices que no son XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-106">Not all options available for non-XML indexes are supported on XML indexes.</span></span>  
  
 <span data-ttu-id="2bb20-107">Cuando cree un índice XML, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bb20-107">Note the following when you are creating an XML index:</span></span>  
  
-   <span data-ttu-id="2bb20-108">Para crear un índice XML principal, la tabla que contiene la columna XML que se va a indizar, llamada tabla base, debe tener un índice clúster en la clave principal.</span><span class="sxs-lookup"><span data-stu-id="2bb20-108">To create a primary XML index, the table that contains the XML column being indexed, called the base table, must have a clustered index on the primary key.</span></span> <span data-ttu-id="2bb20-109">Esto garantiza que si la tabla base tiene particiones, se pueden crear particiones en el índice XML principal usando el mismo esquema y función de partición.</span><span class="sxs-lookup"><span data-stu-id="2bb20-109">This makes sure that if the base table is partitioned, the primary XML index can be partitioned by using the same partitioning scheme and partitioning function.</span></span>  
  
-   <span data-ttu-id="2bb20-110">Si ya existe un índice XML, la clave principal agrupada de la tabla no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="2bb20-110">If an XML index exists, the clustered, primary key of the table cannot be modified.</span></span> <span data-ttu-id="2bb20-111">Antes de modificar la clave principal, deberá quitar todos los índices XML de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2bb20-111">You will have to drop all XML indexes on the table before modifying the primary key.</span></span>  
  
-   <span data-ttu-id="2bb20-112">Un índice XML principal puede crearse en una sola columna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="2bb20-112">A primary XML index can be created on a single `xml` type column.</span></span> <span data-ttu-id="2bb20-113">No es posible crear ningún otro índice con una columna de tipo XML como columna de clave.</span><span class="sxs-lookup"><span data-stu-id="2bb20-113">You cannot create any other type of index with the XML type column as a key column.</span></span> <span data-ttu-id="2bb20-114">No obstante, puede incluir la columna de tipo L `xml` en un índice que no sea XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-114">However, you can include the `xml` L type column in a non-XML index.</span></span> <span data-ttu-id="2bb20-115">Cada columna de tipo `xml` de una tabla puede tener su propio índice XML principal.</span><span class="sxs-lookup"><span data-stu-id="2bb20-115">Each `xml` type column in a table can have its own primary XML index.</span></span> <span data-ttu-id="2bb20-116">No obstante, solo se admite un índice XML principal por cada columna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="2bb20-116">However, only one primary XML index per `xml` type column is permitted.</span></span>  
  
-   <span data-ttu-id="2bb20-117">Los índices XML existen en el mismo espacio de nombres que los índices que no son XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-117">XML indexes exist in the same namespace as non-XML indexes.</span></span> <span data-ttu-id="2bb20-118">Por tanto, no puede tener un índice XML y otro que no lo sea en la misma tabla y con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="2bb20-118">Therefore, you cannot have an XML index and a non-XML index on the same table with the same name.</span></span>  
  
-   <span data-ttu-id="2bb20-119">Las opciones IGNORE_DUP_KEY y ONLINE siempre se establecen en OFF para los índices XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-119">IGNORE_DUP_KEY and ONLINE options of are always set to OFF for XML indexes.</span></span> <span data-ttu-id="2bb20-120">Puede especificar estas opciones con el valor OFF.</span><span class="sxs-lookup"><span data-stu-id="2bb20-120">You can specify these options with a value of OFF.</span></span>  
  
-   <span data-ttu-id="2bb20-121">La información de partición o grupo de archivos de la tabla de usuarios se aplica al índice XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-121">The filegroup or partitioning information of the user table is applied to the XML index.</span></span> <span data-ttu-id="2bb20-122">Los usuarios no pueden especificar dicha información por separado en un índice XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-122">Users cannot specify these separately on an XML index.</span></span>  
  
-   <span data-ttu-id="2bb20-123">La opción de índice DROP_EXISTING permite quitar un índice XML principal y crear uno nuevo o efectuar la misma operación con un índice XML secundario.</span><span class="sxs-lookup"><span data-stu-id="2bb20-123">The DROP_EXISTING index option can drop a primary XML index and create a new primary XML index, or drop a secondary XML index and create a new secondary XML index.</span></span> <span data-ttu-id="2bb20-124">No obstante, esta opción no puede quitar un índice XML secundario para crear un índice XML principal ni viceversa.</span><span class="sxs-lookup"><span data-stu-id="2bb20-124">However, this option cannot drop a secondary XML index to create a new primary XML index or vice versa.</span></span>  
  
-   <span data-ttu-id="2bb20-125">Los nombres de índice XML principal tienen las mismas restricciones que los nombres de vista.</span><span class="sxs-lookup"><span data-stu-id="2bb20-125">Primary XML index names have the same restrictions as view names.</span></span>  
  
 <span data-ttu-id="2bb20-126">No se puede crear un índice XML en una `xml` columna de tipo de una vista, en una variable con valores de **tabla** con columnas de tipo `xml` o variables de `xml` tipo.</span><span class="sxs-lookup"><span data-stu-id="2bb20-126">You cannot create an XML index on an `xml` type column in a view, on a **table** valued variable with `xml` type columns, or `xml` type variables.</span></span>  
  
-   <span data-ttu-id="2bb20-127">Para cambiar una columna de tipo `xml` de XML con tipo a XML sin tipo, o viceversa, con la opción ALTER TABLE ALTER COLUMN, la columna no debe incluir ningún índice XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-127">To change an `xml` type column from untyped to typed XML, or vice versa, by using the ALTER TABLE ALTER COLUMN option, no XML index on the column should exist.</span></span> <span data-ttu-id="2bb20-128">Si existe alguno, debe quitarse antes de intentar cambiar el tipo de columna.</span><span class="sxs-lookup"><span data-stu-id="2bb20-128">If one does exist, it must be dropped before the column type change is tried.</span></span>  
  
-   <span data-ttu-id="2bb20-129">Al crear un índice XML, la opción ARITHABORT debe configurarse en ON.</span><span class="sxs-lookup"><span data-stu-id="2bb20-129">The option ARITHABORT must be set to ON when an XML index is created.</span></span> <span data-ttu-id="2bb20-130">Para consultar, insertar, eliminar o actualizar valores en la columna XML usando métodos de tipo de datos XML, debe establecerse la misma opción en la conexión.</span><span class="sxs-lookup"><span data-stu-id="2bb20-130">To query, insert, delete, or update values in the XML column using XML data type methods, the same option must be set on the connection.</span></span> <span data-ttu-id="2bb20-131">De lo contrario, los métodos de tipo de datos XML darán error.</span><span class="sxs-lookup"><span data-stu-id="2bb20-131">If it is not, the XML data type methods will fail.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2bb20-132">Las vistas de catálogo incluyen información acerca de los índices XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-132">Information about an XML index can be found in catalog views.</span></span> <span data-ttu-id="2bb20-133">Pero no se admite **sp_helpindex** .</span><span class="sxs-lookup"><span data-stu-id="2bb20-133">However, **sp_helpindex** is not supported.</span></span> <span data-ttu-id="2bb20-134">Los ejemplos que se ofrecen más adelante en este tema muestran cómo consultar las vistas de catálogo para encontrar información de índices XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-134">Examples provided later in this topic show how to query the catalog views to find XML index information.</span></span>  
  
 <span data-ttu-id="2bb20-135">Al crear o volver a crear un índice XML principal o una columna de tipo de datos XML que contiene valores de los tipos de esquema XML **xs:date** o **xs:dateTime** (o cualquier subtipo de estos tipos) que tengan un año de menos de 1, se producirá un error en la creación del índice en [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="2bb20-135">When creating or recreating a primary XML index on an XML data type column that contains values of the XML Schema types **xs:date** or **xs:dateTime** (or any subtypes of these types) that have a year of less than 1, the index creation will fail in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="2bb20-136">permitía estos valores, por lo que este problema se puede producir al crear índices en una base de datos generada en [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bb20-136">allowed these values, so this problem can occur when creating indexes in a database generated in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="2bb20-137">Para obtener más información, vea [Comparar XML con tipo y XML sin tipo](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2bb20-137">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
### <a name="example-creating-a-primary-xml-index"></a><span data-ttu-id="2bb20-138">Ejemplo: Crear un índice XML principal</span><span class="sxs-lookup"><span data-stu-id="2bb20-138">Example: Creating a Primary XML Index</span></span>  
 <span data-ttu-id="2bb20-139">En la mayoría de los ejemplos, se utiliza la tabla T (pk INT PRIMARY KEY, xCol XML) con una columna XML sin tipo.</span><span class="sxs-lookup"><span data-stu-id="2bb20-139">Table T (pk INT PRIMARY KEY, xCol XML) with an untyped XML column is used in most of the examples.</span></span> <span data-ttu-id="2bb20-140">Se pueden ampliar a XML con tipo de forma directa.</span><span class="sxs-lookup"><span data-stu-id="2bb20-140">These can be extended to typed XML in a straightforward way.</span></span> <span data-ttu-id="2bb20-141">Para simplificar el trabajo, las consultas se describen para instancias de datos XML como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="2bb20-141">For simplicity, queries are described for XML data instances as shown in the following:</span></span>  
  
```  
<book genre="security" publicationdate="2002" ISBN="0-7356-1588-2">  
   <title>Writing Secure Code</title>  
   <author>  
      <first-name>Michael</first-name>  
      <last-name>Howard</last-name>  
   </author>  
   <author>  
      <first-name>David</first-name>  
      <last-name>LeBlanc</last-name>  
   </author>  
   <price>39.99</price>  
</book>  
```  
  
 <span data-ttu-id="2bb20-142">La siguiente instrucción crea un índice XML, denominado idx_xCol, en la columna XML xCol de la tabla T:</span><span class="sxs-lookup"><span data-stu-id="2bb20-142">The following statement creates an XML index, called idx_xCol, on the XML column xCol of table T:</span></span>  
  
```  
CREATE PRIMARY XML INDEX idx_xCol on T (xCol)  
```  
  
## <a name="creating-a-secondary-xml-index"></a><span data-ttu-id="2bb20-143">Crear un índice XML secundario</span><span class="sxs-lookup"><span data-stu-id="2bb20-143">Creating a Secondary XML Index</span></span>  
 <span data-ttu-id="2bb20-144">Use la instrucción DDL [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] para crear índices XML secundarios y especificar el tipo de índice XML secundario que quiere.</span><span class="sxs-lookup"><span data-stu-id="2bb20-144">Use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement to create secondary XML indexes and specify the type of the secondary XML index that you want.</span></span>  
  
 <span data-ttu-id="2bb20-145">Cuando cree índices XML secundarios, tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2bb20-145">Note the following when you are creating secondary XML indexes:</span></span>  
  
-   <span data-ttu-id="2bb20-146">Todas las opciones de indización que se aplican a un índice no clúster, salvo IGNORE_DUP_KEY y ONLINE, se admiten para los índices XML secundarios.</span><span class="sxs-lookup"><span data-stu-id="2bb20-146">All indexing options that apply to a nonclustered index, except IGNORE_DUP_KEY and ONLINE, are permitted on secondary XML indexes.</span></span> <span data-ttu-id="2bb20-147">Las dos opciones deben establecerse siempre en OFF para los índices XML secundarios.</span><span class="sxs-lookup"><span data-stu-id="2bb20-147">The two options must always be set to OFF for secondary XML indexes.</span></span>  
  
-   <span data-ttu-id="2bb20-148">Los índices secundarios se dividen en particiones al igual que el índice XML principal.</span><span class="sxs-lookup"><span data-stu-id="2bb20-148">The secondary indexes are partitioned just like the primary XML index.</span></span>  
  
-   <span data-ttu-id="2bb20-149">DROP_EXISTING permite quitar un índice secundario de la tabla de usuario y crear otro en la misma tabla.</span><span class="sxs-lookup"><span data-stu-id="2bb20-149">DROP_EXISTING can drop a secondary index on the user table and create another secondary index on the user table.</span></span>  
  
 <span data-ttu-id="2bb20-150">Puede consultar la vista de catálogo **sys.xml_indexes** para recuperar información de índices XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-150">You can query the **sys.xml_indexes** catalog view to retrieve XML index information.</span></span> <span data-ttu-id="2bb20-151">Tenga en cuenta que la columna **secondary_type_desc** de la vista de catálogo **sys.xml_indexes** proporciona el tipo de índice secundario:</span><span class="sxs-lookup"><span data-stu-id="2bb20-151">Note that the **secondary_type_desc** column in the **sys.xml_indexes** catalog view provides the type of secondary index:</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="2bb20-152">Los valores que se devuelven en la columna **secondary_type_desc** pueden ser NULL, PATH, VALUE o PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="2bb20-152">The values returned in the **secondary_type_desc** column can be NULL, PATH, VALUE, or PROPERTY.</span></span> <span data-ttu-id="2bb20-153">El valor devuelto para el índice XML principal es NULL.</span><span class="sxs-lookup"><span data-stu-id="2bb20-153">For the primary XML index, the value returned is NULL.</span></span>  
  
### <a name="example-creating-secondary-xml-indexes"></a><span data-ttu-id="2bb20-154">Ejemplo: Crear índices XML secundarios</span><span class="sxs-lookup"><span data-stu-id="2bb20-154">Example: Creating Secondary XML Indexes</span></span>  
 <span data-ttu-id="2bb20-155">El ejemplo siguiente muestra cómo crear índices XML secundarios.</span><span class="sxs-lookup"><span data-stu-id="2bb20-155">The following example illustrates how secondary XML indexes are created.</span></span> <span data-ttu-id="2bb20-156">En el ejemplo también se muestra información acerca de los índices XML que ha creado.</span><span class="sxs-lookup"><span data-stu-id="2bb20-156">The example also shows information about the XML indexes that you created.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML);  
GO  
-- Create primary index.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol);  
GO  
-- Create secondary indexes (PATH, VALUE, PROPERTY).  
CREATE XML INDEX PIdx_T_XmlCol_PATH ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PATH;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_VALUE ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR VALUE;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_PROPERTY ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PROPERTY;  
GO  
```  
  
 <span data-ttu-id="2bb20-157">Puede consultar `sys.xml_indexes` para recuperar información de índices XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-157">You can query the `sys.xml_indexes` to retrieve XML indexes information.</span></span> <span data-ttu-id="2bb20-158">La columna `secondary_type_desc` proporciona el tipo de índice secundario.</span><span class="sxs-lookup"><span data-stu-id="2bb20-158">The `secondary_type_desc` column provides the secondary index type.</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="2bb20-159">También puede consultar la vista de catálogo para obtener información de índice.</span><span class="sxs-lookup"><span data-stu-id="2bb20-159">You can also query the catalog view for index information.</span></span>  
  
```  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T');  
```  
  
 <span data-ttu-id="2bb20-160">Puede agregar datos de ejemplo y, a continuación, revisar la información de índices XML.</span><span class="sxs-lookup"><span data-stu-id="2bb20-160">You can add sample data and then review the XML index information.</span></span>  
  
```  
INSERT INTO T VALUES (1,  
'<doc id="123">  
<sections>  
<section num="2">  
<heading>Background</heading>  
</section>  
<section num="3">  
<heading>Sort</heading>  
</section>  
<section num="4">  
<heading>Search</heading>  
</section>  
</sections>  
</doc>');  
GO  
-- Check XML index information.  
SELECT *  
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, NULL, 'DETAILED');  
GO  
-- Space usage of primary XML index  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id  
FROM    sys.xml_indexes i   
WHERE   i.name = 'PIdx_T_XmlCol' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
--- Space usage of secondary XML index (for example PATH secondary index)  PIdx_T_XmlCol_PATH  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id   
FROM    sys.xml_indexes i   
WHERE  i.name = 'PIdx_T_XmlCol_PATH' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
  
-- Space usage of all secondary XML indexes for a particular table  
SELECT i.name, object_name(i.object_id), stats.*   
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, DEFAULT, 'DETAILED') stats  
JOIN sys.xml_indexes i ON (stats.object_id = i.object_id and stats.index_id = i.index_id)  
WHERE secondary_type is not null;  
-- Drop secondary indexes.  
DROP INDEX PIdx_T_XmlCol_PATH ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_VALUE ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_PROPERTY ON T;  
GO  
-- Drop primary index.  
DROP INDEX PIdx_T_XmlCol ON T;  
-- Drop table T.  
DROP TABLE T;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="2bb20-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2bb20-161">See Also</span></span>  
 <span data-ttu-id="2bb20-162">[Índices XML &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2bb20-162">[XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span></span>  
 [<span data-ttu-id="2bb20-163">Datos XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2bb20-163">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
