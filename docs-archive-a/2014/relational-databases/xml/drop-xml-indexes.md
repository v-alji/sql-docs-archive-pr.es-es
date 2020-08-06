---
title: Quitar índices XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- removing indexes
- dropping indexes
- XML indexes [SQL Server], dropping
ms.assetid: 7591ebea-34af-4925-8553-b2adb5b487c2
author: rothja
ms.author: jroth
ms.openlocfilehash: b7d4621cf2182b4587b12665a1cfe10ddbe0db3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662698"
---
# <a name="drop-xml-indexes"></a><span data-ttu-id="5a4d7-102">Quitar índices XML</span><span class="sxs-lookup"><span data-stu-id="5a4d7-102">Drop XML Indexes</span></span>
  <span data-ttu-id="5a4d7-103">La instrucción [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] se puede usar para quitar índices XML y no XML principales y secundarios existentes.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-103">The [DROP INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] statement can be used to drop existing primary or secondary XML and non-XML indexes.</span></span> <span data-ttu-id="5a4d7-104">No obstante, ninguna opción de DROP INDEX se aplica a los índices XML.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-104">However, no options of DROP INDEX apply to XML indexes.</span></span> <span data-ttu-id="5a4d7-105">Si se quita el índice XML principal, también se eliminarán todos los índices secundarios existentes.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-105">If you drop the primary XML index, any secondary indexes that are present are also deleted.</span></span>  
  
 <span data-ttu-id="5a4d7-106">La sintaxis de DROP con *TableName.IndexName* está desapareciendo y no es compatible con los índices XML.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-106">The DROP syntax with *TableName.IndexName* is being phased out and is not supported for XML indexes.</span></span>  
  
## <a name="example-creating-and-dropping-a-primary-xml-index"></a><span data-ttu-id="5a4d7-107">Ejemplo: Creación y eliminación de un índice XML principal</span><span class="sxs-lookup"><span data-stu-id="5a4d7-107">Example: Creating and Dropping a Primary XML Index</span></span>  
 <span data-ttu-id="5a4d7-108">En el ejemplo siguiente se muestra cómo crear un índice XML en una columna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-108">In the following example, an XML index is created on an `xml` type column.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML)  
GO  
-- Create Primary XML index   
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol)  
GO  
-- Verify the index creation.   
-- Note index type is 3 for xml indexes.  
-- Note the type 3 is index on XML type.  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T')  
AND name='PIdx_T_XmlCol'   
-- Drop the index.  
DROP INDEX PIdx_T_XmlCol ON T  
```  
  
 <span data-ttu-id="5a4d7-109">Al quitar una tabla, se quitan automáticamente todos los índices XML que contiene.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-109">When a table is dropped, all the XML indexes on it are also automatically dropped.</span></span> <span data-ttu-id="5a4d7-110">No obstante, una columna XML no puede quitarse desde una tabla si existe un índice XML en la columna.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-110">However, an XML column cannot be dropped from a table if an XML index exists on the column.</span></span>  
  
 <span data-ttu-id="5a4d7-111">En el ejemplo siguiente se muestra cómo crear un índice XML en una columna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-111">In the following example, an XML index is created on an `xml` type column.</span></span> <span data-ttu-id="5a4d7-112">Para obtener más información, vea [Comparar XML con tipo y XML sin tipo](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="5a4d7-112">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
```  
CREATE TABLE TestTable(  
 Col1 int primary key,   
 Col2 xml (Production.ProductDescriptionSchemaCollection))   
GO  
```  
  
 <span data-ttu-id="5a4d7-113">En este momento, puede crear un índice XML principal en `Co12`.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-113">Now, you can create a primary XML index on `Co12`.</span></span>  
  
```  
CREATE PRIMARY XML INDEX PIdx_TestTable_Col2   
ON TestTable(Col2)  
GO  
```  
  
## <a name="example-creating-an-xml-index-by-using-the-drop_existing-index-option"></a><span data-ttu-id="5a4d7-114">Ejemplo: Creación de un índice XML con la opción de índice DROP_EXISTING</span><span class="sxs-lookup"><span data-stu-id="5a4d7-114">Example: Creating an XML Index by Using the DROP_EXISTING Index Option</span></span>  
 <span data-ttu-id="5a4d7-115">El ejemplo siguiente muestra cómo crear un índice XML en una columna (`XmlColx`).</span><span class="sxs-lookup"><span data-stu-id="5a4d7-115">In the following example, an XML index is created on a column (`XmlColx`).</span></span> <span data-ttu-id="5a4d7-116">A continuación, se creará otro índice XML con el mismo nombre en una columna diferente (`XmlColy`).</span><span class="sxs-lookup"><span data-stu-id="5a4d7-116">Then, another XML index with the same name is created on a different column, (`XmlColy`).</span></span> <span data-ttu-id="5a4d7-117">Dado que se ha especificado la opción `DROP_EXISTING` , el índice XML existente en (`XmlColx)` se quita y se crea un índice XML en (`XmlColy`).</span><span class="sxs-lookup"><span data-stu-id="5a4d7-117">Because the `DROP_EXISTING` option is specified, the existing XML index on (`XmlColx)` is dropped and a new XML index on (`XmlColy`) is created.</span></span>  
  
```  
DROP TABLE T  
GO  
CREATE TABLE T(Col1 int primary key, XmlColx xml, XmlColy xml)  
GO  
-- Create XML index on XmlColx.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColx)  
GO  
-- Create same name XML index on XmlColy.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlColy)   
WITH (DROP_EXISTING = ON)  
-- Verify the index is created on XmlColy.d.  
SELECT sc.name   
FROM   sys.xml_indexes si inner join sys.index_columns sic   
ON     sic.object_id=si.object_id and sic.index_id=si.index_id  
INNER  join sys.columns sc on sc.object_id=sic.object_id   
AND    sc.column_id=sic.column_id  
WHERE  si.name='PIdx_T_XmlCol'   
AND    si.object_id=object_id('T')  
```  
  
 <span data-ttu-id="5a4d7-118">Esta consulta devuelve el nombre de la columna en la que el índice XML especificado se ha creado.</span><span class="sxs-lookup"><span data-stu-id="5a4d7-118">This query returns the column name on which the specified XML index is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4d7-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a4d7-119">See Also</span></span>  
 [<span data-ttu-id="5a4d7-120">Índices XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="5a4d7-120">XML Indexes &#40;SQL Server&#41;</span></span>](xml-indexes-sql-server.md)  
  
  
