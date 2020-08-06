---
title: Promoción de los valores XML usados con frecuencia con columnas calculadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- promoting properties [XML in SQL Server]
- property promotion [XML in SQL Server]
ms.assetid: f5111896-c2fd-4209-b500-f2baa45489ad
author: rothja
ms.author: jroth
ms.openlocfilehash: bfb83b7772ffd92eab7087db11e4c3ffd96afa47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746793"
---
# <a name="promote-frequently-used-xml-values-with-computed-columns"></a><span data-ttu-id="6badb-102">Promover los valores XML usados con frecuencia con columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="6badb-102">Promote Frequently Used XML Values with Computed Columns</span></span>
  <span data-ttu-id="6badb-103">Si se efectúan consultas principalmente en una cantidad pequeña de valores de elementos y atributos, puede que sea conveniente promover estas cantidades a columnas relacionales.</span><span class="sxs-lookup"><span data-stu-id="6badb-103">If queries are made principally on a small number of element and attribute values, you may want to promote those quantities into relational columns.</span></span> <span data-ttu-id="6badb-104">Esto es útil cuando se ejecutan consultas en una pequeña parte de los datos XML mientras se recupera toda la instancia XML.</span><span class="sxs-lookup"><span data-stu-id="6badb-104">This is helpful when queries are issued on a small part of the XML data while the whole XML instance is retrieved.</span></span> <span data-ttu-id="6badb-105">No es necesario crear un índice XML en la columna XML.</span><span class="sxs-lookup"><span data-stu-id="6badb-105">Creating an XML index on the XML column is not required.</span></span> <span data-ttu-id="6badb-106">En lugar de ello, se puede indizar la columna promocionada.</span><span class="sxs-lookup"><span data-stu-id="6badb-106">Instead, the promoted column can be indexed.</span></span> <span data-ttu-id="6badb-107">Las consultas se deben escribir de modo que usen la columna promocionada.</span><span class="sxs-lookup"><span data-stu-id="6badb-107">Queries must be written to use the promoted column.</span></span> <span data-ttu-id="6badb-108">Es decir, que el optimizador de consultas no dirige de nuevo las consultas de la columna XML a la columna promocionada.</span><span class="sxs-lookup"><span data-stu-id="6badb-108">That is, the query optimizer does not target again the queries on the XML column to the promoted column.</span></span>  
  
 <span data-ttu-id="6badb-109">La columna promocionada puede ser una columna calculada de la misma tabla o puede ser una columna aparte, mantenida por el usuario, de una tabla.</span><span class="sxs-lookup"><span data-stu-id="6badb-109">The promoted column can be a computed column in the same table or it can be a separate, user-maintained column in a table.</span></span> <span data-ttu-id="6badb-110">Esto es suficiente cuando se promocionan valores singleton desde cada instancia XML.</span><span class="sxs-lookup"><span data-stu-id="6badb-110">This is sufficient when singleton values are promoted from each XML instance.</span></span> <span data-ttu-id="6badb-111">No obstante, en el caso de propiedades con varios valores, es necesario crear una tabla aparte para la propiedad, como se describe en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="6badb-111">However, for multi-valued properties, you have to create a separate table for the property, as described in the following section.</span></span>  
  
## <a name="computed-column-based-on-the-xml-data-type"></a><span data-ttu-id="6badb-112">Columna calculada basada en el tipo de datos xml</span><span class="sxs-lookup"><span data-stu-id="6badb-112">Computed Column Based on the xml Data Type</span></span>  
 <span data-ttu-id="6badb-113">Una columna calculada se puede crear mediante una función definida por el usuario que invoque `xml` métodos de tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="6badb-113">A computed column can be created by using a user-defined function that invokes `xml` data type methods.</span></span> <span data-ttu-id="6badb-114">El tipo de la columna calculada puede ser cualquiera SQL, incluido XML.</span><span class="sxs-lookup"><span data-stu-id="6badb-114">The type of the computed column can be any SQL type, including XML.</span></span> <span data-ttu-id="6badb-115">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6badb-115">This is illustrated in the following example.</span></span>  
  
### <a name="example-computed-column-based-on-the-xml-data-type-method"></a><span data-ttu-id="6badb-116">Ejemplo: Columna calculada basada en el método de tipo de datos XML</span><span class="sxs-lookup"><span data-stu-id="6badb-116">Example: Computed Column Based on the xml Data Type Method</span></span>  
 <span data-ttu-id="6badb-117">Cree la función definida por el usuario para obtener el número ISBN de un libro:</span><span class="sxs-lookup"><span data-stu-id="6badb-117">Create the user-defined function for a book ISBN number:</span></span>  
  
```  
CREATE FUNCTION udf_get_book_ISBN (@xData xml)  
RETURNS varchar(20)  
BEGIN  
   DECLARE @ISBN   varchar(20)  
   SELECT @ISBN = @xData.value('/book[1]/@ISBN', 'varchar(20)')  
   RETURN @ISBN   
END  
```  
  
 <span data-ttu-id="6badb-118">Agregue una columna calculada a la tabla para el ISBN:</span><span class="sxs-lookup"><span data-stu-id="6badb-118">Add a computed column to the table for the ISBN:</span></span>  
  
```  
ALTER TABLE      T  
ADD   ISBN AS dbo.udf_get_book_ISBN(xCol)  
```  
  
 <span data-ttu-id="6badb-119">La columna calculada se puede indizar de la manera habitual.</span><span class="sxs-lookup"><span data-stu-id="6badb-119">The computed column can be indexed in the usual way.</span></span>  
  
### <a name="example-queries-on-a-computed-column-based-on-xml-data-type-methods"></a><span data-ttu-id="6badb-120">Ejemplo: Consultas en una columna calculada basada en métodos de tipo de datos XML</span><span class="sxs-lookup"><span data-stu-id="6badb-120">Example: Queries on a Computed Column Based on xml Data Type Methods</span></span>  
 <span data-ttu-id="6badb-121">Para obtener el <`book`> cuyo ISBN es 0-7356-1588-2:</span><span class="sxs-lookup"><span data-stu-id="6badb-121">To obtain the <`book`> whose ISBN is 0-7356-1588-2:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  xCol.exist('/book/@ISBN[. = "0-7356-1588-2"]') = 1  
```  
  
 <span data-ttu-id="6badb-122">La consulta en la columna XML se puede volver a escribir de modo que utilice la columna calculada, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="6badb-122">The query on the XML column can be rewritten to use the computed column as follows:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  ISBN = '0-7356-1588-2'  
```  
  
 <span data-ttu-id="6badb-123">Puede crear una función definida por el usuario para devolver el `xml` tipo de datos y una columna calculada mediante la función definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6badb-123">You can create a user-defined function to return the `xml` data type and a computed column by using the user-defined function.</span></span> <span data-ttu-id="6badb-124">Sin embargo, no puede crear un índice XML en la columna XML calculada.</span><span class="sxs-lookup"><span data-stu-id="6badb-124">However, you cannot create an XML index on the computed, XML column.</span></span>  
  
## <a name="creating-property-tables"></a><span data-ttu-id="6badb-125">Crear tablas de propiedades</span><span class="sxs-lookup"><span data-stu-id="6badb-125">Creating Property Tables</span></span>  
 <span data-ttu-id="6badb-126">Tal vez desee promocionar algunas de las propiedades con varios valores desde los datos XML a una o más tablas, crear índices en estas tablas y orientar de nuevo las consultas para que las utilicen.</span><span class="sxs-lookup"><span data-stu-id="6badb-126">You may want to promote some of the multivalued properties from your XML data into one or more tables, create indexes on those tables, and target again your queries to use them.</span></span> <span data-ttu-id="6badb-127">Un escenario típico es el caso en que un pequeño número de propiedades cubre casi toda la carga de trabajo de la consulta.</span><span class="sxs-lookup"><span data-stu-id="6badb-127">A typical scenario is one in which a small number of properties covers most of your query workload.</span></span> <span data-ttu-id="6badb-128">Puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6badb-128">You can do the following:</span></span>  
  
-   <span data-ttu-id="6badb-129">Cree una o más tablas que contengan las propiedades con varios valores.</span><span class="sxs-lookup"><span data-stu-id="6badb-129">Create one or more tables to hold the multivalued properties.</span></span> <span data-ttu-id="6badb-130">Puede resultarle práctico almacenar una propiedad por tabla y duplicar la clave principal de la tabla base en las tablas de propiedades para combinarlas de nuevo con la tabla base.</span><span class="sxs-lookup"><span data-stu-id="6badb-130">You may find it convenient to store one property per table and duplicate the primary key of the base table in the property tables for back joining with the base table.</span></span>  
  
-   <span data-ttu-id="6badb-131">Si desea mantener el orden relativo de las propiedades, tiene que insertar una columna nueva para el orden relativo.</span><span class="sxs-lookup"><span data-stu-id="6badb-131">If you want to maintain the relative order of the properties, you have to introduce a separate column for the relative order.</span></span>  
  
-   <span data-ttu-id="6badb-132">Cree desencadenadores en la columna XML para mantener las tablas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6badb-132">Create triggers on the XML column to maintain the property tables.</span></span> <span data-ttu-id="6badb-133">En los desencadenadores, realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="6badb-133">Within the triggers, do one of the following:</span></span>  
  
    -   <span data-ttu-id="6badb-134">Use `xml` métodos de tipo de datos, como **Nodes ()** y **Value ()**, para insertar y eliminar filas de las tablas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6badb-134">Use `xml` data type methods, such as **nodes()** and **value()**, to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="6badb-135">Cree funciones de transmisión por secuencias con valores de tabla en Common Language Runtime (CLR) para insertar y eliminar filas de las tablas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6badb-135">Create streaming table-valued functions in the common language runtime (CLR) to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="6badb-136">Escriba consultas para el acceso de SQL a las tablas de propiedades y para el acceso de XML a la columna XML de la tabla base, con combinaciones entre las tablas mediante el uso de su clave principal.</span><span class="sxs-lookup"><span data-stu-id="6badb-136">Write queries for SQL access to the property tables and for XML access to the XML column in the base table, with joins between the tables by using their primary key.</span></span>  
  
### <a name="example-create-a-property-table"></a><span data-ttu-id="6badb-137">Ejemplo: Creación de una tabla de propiedades</span><span class="sxs-lookup"><span data-stu-id="6badb-137">Example: Create a Property Table</span></span>  
 <span data-ttu-id="6badb-138">A modo de ilustración, suponga que desea promocionar el nombre de los autores.</span><span class="sxs-lookup"><span data-stu-id="6badb-138">For illustration, assume that you want to promote the first name of the authors.</span></span> <span data-ttu-id="6badb-139">Los libros tienen uno o varios autores, por lo que sus nombres son una propiedad con varios valores.</span><span class="sxs-lookup"><span data-stu-id="6badb-139">Books have one or more authors, so that first name is a multivalued property.</span></span> <span data-ttu-id="6badb-140">Cada nombre se almacena en una fila distinta de una tabla de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6badb-140">Each first name is stored in a separate row of a property table.</span></span> <span data-ttu-id="6badb-141">La clave principal de la tabla base se duplica en la tabla de propiedades para que se puedan volver a combinar más tarde.</span><span class="sxs-lookup"><span data-stu-id="6badb-141">The primary key of the base table is duplicated in the property table for back join.</span></span>  
  
```  
create table tblPropAuthor (propPK int, propAuthor varchar(max))  
```  
  
### <a name="example-create-a-user-defined-function-to-generate-a-rowset-from-an-xml-instance"></a><span data-ttu-id="6badb-142">Ejemplo: Creación de una función definida por el usuario para generar un conjunto de filas a partir de una instancia XML</span><span class="sxs-lookup"><span data-stu-id="6badb-142">Example: Create a User-defined Function to Generate a Rowset from an XML Instance</span></span>  
 <span data-ttu-id="6badb-143">La siguiente función con valores de tabla, udf_XML2Table, acepta un valor de clave principal y una instancia XML.</span><span class="sxs-lookup"><span data-stu-id="6badb-143">The following table-valued function, udf_XML2Table, accepts a primary key value and an XML instance.</span></span> <span data-ttu-id="6badb-144">Recupera el nombre de todos los autores de los elementos <`book`> y devuelve un conjunto de filas de pares de nombres y claves principales.</span><span class="sxs-lookup"><span data-stu-id="6badb-144">It retrieves the first name of all authors of the <`book`> elements and returns a rowset of primary key, first name pairs.</span></span>  
  
```  
create function udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (propPK int, propAuthor varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
      select @pk, nref.value('.', 'varchar(max)')  
      from   @xCol.nodes('/book/author/first-name') R(nref)  
      return  
end  
```  
  
### <a name="example-create-triggers-to-populate-a-property-table"></a><span data-ttu-id="6badb-145">Ejemplo: Creación de desencadenadores para rellenar una tabla de propiedades</span><span class="sxs-lookup"><span data-stu-id="6badb-145">Example: Create Triggers to Populate a Property Table</span></span>  
 <span data-ttu-id="6badb-146">El desencadenador insert inserta filas en la tabla de propiedades:</span><span class="sxs-lookup"><span data-stu-id="6badb-146">The insert trigger inserts rows into the property table:</span></span>  
  
```  
create trigger trg_docs_INS on T for insert  
as  
      declare @wantedXML xml  
      declare @FK int  
      select @wantedXML = xCol from inserted  
      select @FK = PK from inserted  
  
   insert into tblPropAuthor  
   select * from dbo.udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="6badb-147">El desencadenador delete elimina las filas de la tabla de propiedades basándose en el valor de la clave principal de las filas eliminadas:</span><span class="sxs-lookup"><span data-stu-id="6badb-147">The delete trigger deletes the rows from the property table based on the primary key value of the deleted rows:</span></span>  
  
```  
create trigger trg_docs_DEL on T for delete  
as  
   declare @FK int  
   select @FK = PK from deleted  
   delete tblPropAuthor where propPK = @FK  
```  
  
 <span data-ttu-id="6badb-148">El desencadenador update elimina las filas existentes en la tabla de propiedades correspondientes a la instancia XML actualizada e inserta nuevas filas en la tabla de propiedades:</span><span class="sxs-lookup"><span data-stu-id="6badb-148">The update trigger deletes the existing rows in the property table corresponding to the updated XML instance and inserts new rows into the property table:</span></span>  
  
```  
create trigger trg_docs_UPD  
on T  
for update  
as  
if update(xCol) or update(pk)  
begin  
      declare @FK int  
      declare @wantedXML xml  
      select @FK = PK from deleted  
      delete tblPropAuthor where propPK = @FK  
  
   select @wantedXML = xCol from inserted  
   select @FK = pk from inserted  
  
   insert into tblPropAuthor   
      select * from dbo.udf_XML2Table(@FK, @wantedXML)  
end  
```  
  
### <a name="example-find-xml-instances-whose-authors-have-the-same-first-name"></a><span data-ttu-id="6badb-149">Ejemplo: Búsqueda de instancias XML cuyos autores tengan el mismo nombre</span><span class="sxs-lookup"><span data-stu-id="6badb-149">Example: Find XML Instances Whose Authors Have the Same First Name</span></span>  
 <span data-ttu-id="6badb-150">La consulta se puede formar en la columna XML.</span><span class="sxs-lookup"><span data-stu-id="6badb-150">The query can be formed on the XML column.</span></span> <span data-ttu-id="6badb-151">Otra posibilidad es buscar en la tabla de propiedades el nombre "David" y combinarla de nuevo con la tabla base para devolver la instancia XML.</span><span class="sxs-lookup"><span data-stu-id="6badb-151">Alternatively, it can search the property table for first name "David" and perform a back join with the base table to return the XML instance.</span></span> <span data-ttu-id="6badb-152">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6badb-152">For example:</span></span>  
  
```  
SELECT xCol   
FROM     T JOIN tblPropAuthor ON T.pk = tblPropAuthor.propPK  
WHERE    tblPropAuthor.propAuthor = 'David'  
```  
  
### <a name="example-solution-using-the-clr-streaming-table-valued-function"></a><span data-ttu-id="6badb-153">Ejemplo: Solución mediante la función de transmisión por secuencias con valores de tabla de CLR</span><span class="sxs-lookup"><span data-stu-id="6badb-153">Example: Solution Using the CLR Streaming Table-valued Function</span></span>  
 <span data-ttu-id="6badb-154">Esta solución consta de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="6badb-154">This solution is made up of the following steps:</span></span>  
  
1.  <span data-ttu-id="6badb-155">Defina una clase de CLR, SqlReaderBase, que implemente ISqlReader y genere una función de salida de transmisión por secuencias con valores de tabla aplicando una expresión de ruta de acceso en una instancia XML.</span><span class="sxs-lookup"><span data-stu-id="6badb-155">Define a CLR class, SqlReaderBase, that implements ISqlReader and generates a streaming, table-valued output by applying a path expression on an XML instance.</span></span>  
  
2.  <span data-ttu-id="6badb-156">Cree un ensamblado y una función Transact-SQL definida por el usuario para iniciar la clase de CLR.</span><span class="sxs-lookup"><span data-stu-id="6badb-156">Create an assembly and a Transact-SQL user-defined function to start the CLR class.</span></span>  
  
3.  <span data-ttu-id="6badb-157">Defina los desencadenadores insert, update y delete mediante la función definida por el usuario para mantener tablas de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6badb-157">Define the insert, update, and delete triggers by using the user-defined function to maintain a property tables.</span></span>  
  
 <span data-ttu-id="6badb-158">Para ello, primero deberá crear la función de transmisión por secuencias de CLR.</span><span class="sxs-lookup"><span data-stu-id="6badb-158">To do this, you first create the streaming CLR function.</span></span> <span data-ttu-id="6badb-159">El `xml` tipo de datos se expone como una clase administrada SQLXML en ADO.net y admite el método **CreateReader ()** que devuelve un XmlReader.</span><span class="sxs-lookup"><span data-stu-id="6badb-159">The `xml` data type is exposed as a managed class SqlXml in ADO.NET and supports the **CreateReader()** method that returns an XmlReader.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6badb-160">El código de ejemplo de esta sección usa XPathDocument y XPathNavigator.</span><span class="sxs-lookup"><span data-stu-id="6badb-160">The example code in this section uses XPathDocument and XPathNavigator.</span></span> <span data-ttu-id="6badb-161">De este modo, se fuerza la carga de todos los documentos XML en la memoria.</span><span class="sxs-lookup"><span data-stu-id="6badb-161">These force you to load all the XML documents into memory.</span></span> <span data-ttu-id="6badb-162">Si utiliza código similar en su aplicación para procesar varios documentos XML grandes, este código no es escalable.</span><span class="sxs-lookup"><span data-stu-id="6badb-162">If you are using similar code in your application to process several large XML documents, this code is not scalable.</span></span> <span data-ttu-id="6badb-163">En lugar de ello, mantenga asignaciones de memoria de pequeño tamaño y use interfaces de transmisión por secuencias siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="6badb-163">Instead, keep memory allocations small and use streaming interfaces whenever possible.</span></span> <span data-ttu-id="6badb-164">Para obtener más información sobre el rendimiento, vea [Arquitectura de integración CLR](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span><span class="sxs-lookup"><span data-stu-id="6badb-164">For more information about performance, see [Architecture of CLR Integration](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span></span>  
  
```  
public class c_streaming_xml_tvf {  
   public static ISqlReader streaming_xml_tvf   
(SqlXml xmlDoc, string pathExpression) {  
      return (new TestSqlReaderBase (xmlDoc, pathExpression));  
   }  
}  
  
// Class that implements ISqlReader  
public class TestSqlReaderBase : ISqlReader {  
XPathNodeIterator m_iterator;           
   public SqlChars FirstName;  
// Metadata for current resultset  
private SqlMetaData[] m_rgSqlMetaData;        
  
   public TestSqlReaderBase (SqlXml xmlDoc, string pathExpression) {     
      // Variables for XPath navigation  
      XPathDocument xDoc;  
      XPathNavigator xNav;  
      XPathExpression xPath;  
  
      // Set sql metadata  
      m_rgSqlMetaData = new SqlMetaData[1];  
      m_rgSqlMetaData[0] = new SqlMetaData ("FirstName",    
SqlDbType.NVarChar,50);     
  
      //Set up the Navigator  
      if (!xmlDoc.IsNull)  
          xDoc = new XPathDocument (xmlDoc.CreateReader());  
      else  
          xDoc = new XPathDocument ();  
      xNav = xDoc.CreateNavigator();  
      xPath = xNav.Compile (pathExpression);  
      m_iterator = xNav.Select(xPath);  
   }  
   public bool Read() {  
      bool moreRows = true;  
      if (moreRows = m_iterator.MoveNext())  
         FirstName = new SqlChars (m_iterator.Current.Value);  
      return moreRows;  
   }  
}  
```  
  
 <span data-ttu-id="6badb-165">A continuación, cree un ensamblado y una función [!INCLUDE[tsql](../../includes/tsql-md.md)] definida por el usuario, SQL_streaming_xml_tvf (no se muestra), que corresponda a la función CLR, streaming_xml_tvf.</span><span class="sxs-lookup"><span data-stu-id="6badb-165">Next, create an assembly and a [!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined function, SQL_streaming_xml_tvf (not shown), that corresponds to the CLR function, streaming_xml_tvf.</span></span> <span data-ttu-id="6badb-166">La función definida por el usuario se utiliza para definir la función con valores de tabla, CLR_udf_XML2Table, para la generación de conjuntos de filas:</span><span class="sxs-lookup"><span data-stu-id="6badb-166">The user-defined function is used to define the table-valued function, CLR_udf_XML2Table, for rowset generation:</span></span>  
  
```  
create function CLR_udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (FK int, FirstName varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
   select @pk, FirstName   
   FROM   SQL_streaming_xml_tvf (@xCol, '/book/author/first-name')  
      return  
end  
```  
  
 <span data-ttu-id="6badb-167">Por último, defina desencadenadores como se muestra en el ejemplo "Crear desencadenadores para rellenar una tabla de propiedades", pero sustituya udf_XML2Table por la función CLR_udf_XML2Table.</span><span class="sxs-lookup"><span data-stu-id="6badb-167">Finally, define triggers as shown in the example, "Create triggers to populate a property table", but replace udf_XML2Table with the CLR_udf_XML2Table function.</span></span> <span data-ttu-id="6badb-168">El desencadenador insert se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6badb-168">The insert trigger is shown in the following example:</span></span>  
  
```  
create trigger CLR_trg_docs_INS on T for insert  
as  
   declare @wantedXML xml  
   declare @FK int  
   select @wantedXML = xCol from inserted  
   select @FK = PK from inserted  
  
   insert into tblPropAuthor  
      select *  
   from    dbo.CLR_udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="6badb-169">El desencadenador delete es idéntico a la versión no CLR.</span><span class="sxs-lookup"><span data-stu-id="6badb-169">The delete trigger is identical to the non-CLR version.</span></span> <span data-ttu-id="6badb-170">Sin embargo, el desencadenador update simplemente reemplaza la función udf_XML2Table() por CLR_udf_XML2Table().</span><span class="sxs-lookup"><span data-stu-id="6badb-170">However, the update trigger just replaces the function udf_XML2Table() with CLR_udf_XML2Table().</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6badb-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6badb-171">See Also</span></span>  
 [<span data-ttu-id="6badb-172">Usar XML en columnas calculadas</span><span class="sxs-lookup"><span data-stu-id="6badb-172">Use XML in Computed Columns</span></span>](use-xml-in-computed-columns.md)  
  
  
