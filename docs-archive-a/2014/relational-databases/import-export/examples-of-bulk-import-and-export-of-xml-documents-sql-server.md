---
title: Ejemplos de importación y exportación en bloque de documentos XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- field terminators [SQL Server]
- bulk importing [SQL Server], data formats
- row terminators [SQL Server]
- OPENROWSET function, XML bulk load
- terminators [SQL Server]
- bulk exporting [SQL Server], data formats
- XML bulk load [SQL Server]
ms.assetid: dff99404-a002-48ee-910e-f37f013d946d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d72c84a7ed84503e0c88d2a46c808196903900b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675385"
---
# <a name="examples-of-bulk-import-and-export-of-xml-documents-sql-server"></a><span data-ttu-id="c380c-102">Ejemplos de importación y exportación de forma masiva documentos XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c380c-102">Examples of Bulk Import and Export of XML Documents (SQL Server)</span></span>
    
##  <a name="you-can-bulk-import-xml-documents-into-a-ssnoversion-database-or-bulk-export-them-from-a-ssnoversion-database-this-topic-provides-examples-of-both"></a><a name="top"></a><span data-ttu-id="c380c-103">Puede realizar una importación masiva de documentos XML en una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de datos de o exportarlos de forma masiva desde una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de datos de.</span><span class="sxs-lookup"><span data-stu-id="c380c-103">You can bulk import XML documents into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or bulk export them from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="c380c-104">Este tema proporciona ejemplos de ambos casos.</span><span class="sxs-lookup"><span data-stu-id="c380c-104">This topic provides examples of both.</span></span>  
  
 <span data-ttu-id="c380c-105">Para importar datos de forma masiva de un archivo de datos a una tabla o vista sin particiones de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , puede utilizar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c380c-105">To bulk import data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or non-partitioned view, you can use the following:</span></span>  
  
-   <span data-ttu-id="c380c-106">Utilidad**bcp**</span><span class="sxs-lookup"><span data-stu-id="c380c-106">**bcp** utility</span></span>  
  
     <span data-ttu-id="c380c-107">También puede usar la utilidad **bcp** para exportar datos de cualquier ubicación a una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que funcione una instrucción SELECT, incluidas las vistas con particiones.</span><span class="sxs-lookup"><span data-stu-id="c380c-107">You can also use the **bcp** utility to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that a SELECT statement works, including partitioned views.</span></span>  
  
-   <span data-ttu-id="c380c-108">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="c380c-108">BULK INSERT</span></span>  
  
-   <span data-ttu-id="c380c-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="c380c-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
 <span data-ttu-id="c380c-110">Para obtener más información, vea [importar y exportar datos en bloque con la utilidad bcp &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) e [importar datos en bloque mediante BULK INSERT o OPENROWSET&#40;bulk... &#41; &#40;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md)SQL Server&#41;.</span><span class="sxs-lookup"><span data-stu-id="c380c-110">For more information, see [Import and Export Bulk Data by Using the bcp Utility &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) and [Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c380c-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c380c-111">Examples</span></span>  
 <span data-ttu-id="c380c-112">Los ejemplos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c380c-112">The examples are the following:</span></span>  
  
-   <span data-ttu-id="c380c-113">A.</span><span class="sxs-lookup"><span data-stu-id="c380c-113">A.</span></span> [<span data-ttu-id="c380c-114">Importar de forma masiva datos XML como un flujo de bytes binario</span><span class="sxs-lookup"><span data-stu-id="c380c-114">BULK importing XML data as a binary byte stream</span></span>](#binary_byte_stream)  
  
-   <span data-ttu-id="c380c-115">B.</span><span class="sxs-lookup"><span data-stu-id="c380c-115">B.</span></span> [<span data-ttu-id="c380c-116">Importar de forma masiva datos XML en una fila existente</span><span class="sxs-lookup"><span data-stu-id="c380c-116">Bulk importing XML data in an existing row</span></span>](#existing_row)  
  
-   <span data-ttu-id="c380c-117">C.</span><span class="sxs-lookup"><span data-stu-id="c380c-117">C.</span></span> [<span data-ttu-id="c380c-118">Importar de forma masiva datos XML de un archivo que contiene una DTD</span><span class="sxs-lookup"><span data-stu-id="c380c-118">Bulk importing XML data from a file that contains a DTD</span></span>](#file_contains_dtd)  
  
-   <span data-ttu-id="c380c-119">D.</span><span class="sxs-lookup"><span data-stu-id="c380c-119">D.</span></span> [<span data-ttu-id="c380c-120">Especificar el terminador de campo explícitamente mediante un archivo de formato</span><span class="sxs-lookup"><span data-stu-id="c380c-120">Specifying the field terminator explicitly using a format file</span></span>](#field_terminator_in_format_file)  
  
-   <span data-ttu-id="c380c-121">E.</span><span class="sxs-lookup"><span data-stu-id="c380c-121">E.</span></span> [<span data-ttu-id="c380c-122">Exportar datos XML de forma masiva</span><span class="sxs-lookup"><span data-stu-id="c380c-122">Bulk exporting XML data</span></span>](#bulk_export_xml_data)  
  
###  <a name="a-bulk-importing-xml-data-as-a-binary-byte-stream"></a><a name="binary_byte_stream"></a> <span data-ttu-id="c380c-123">A.</span><span class="sxs-lookup"><span data-stu-id="c380c-123">A.</span></span> <span data-ttu-id="c380c-124">Importar de forma masiva datos XML como un flujo de bytes binario</span><span class="sxs-lookup"><span data-stu-id="c380c-124">Bulk importing XML data as a binary byte stream</span></span>  
 <span data-ttu-id="c380c-125">Cuando importa datos XML de forma masiva de un archivo que contiene una declaración de codificación que quiere aplicar, especifique la opción SINGLE_BLOB en la cláusula OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="c380c-125">When you bulk import XML data from a file that contains an encoding declaration that you want to apply, specify the SINGLE_BLOB option in the OPENROWSET(BULK...) clause.</span></span> <span data-ttu-id="c380c-126">La opción SINGLE_BLOB garantiza que el analizador de XML de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importa los datos según el esquema de codificación especificado en la declaración XML.</span><span class="sxs-lookup"><span data-stu-id="c380c-126">The SINGLE_BLOB option makes sure that the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] imports the data according to the encoding scheme specified in the XML declaration.</span></span>  
  
#### <a name="sample-table"></a><span data-ttu-id="c380c-127">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c380c-127">Sample Table</span></span>  
 <span data-ttu-id="c380c-128">Para probar el ejemplo A, debe crear una tabla de ejemplo `T`.</span><span class="sxs-lookup"><span data-stu-id="c380c-128">To test example A, you must create sample table `T`.</span></span>  
  
```  
USE tempdb  
CREATE TABLE T (IntCol int, XmlCol xml);  
GO  
```  
  
#### <a name="sample-data-file"></a><span data-ttu-id="c380c-129">Archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c380c-129">Sample Data File</span></span>  
 <span data-ttu-id="c380c-130">Para poder ejecutar el ejemplo A, debe crear un archivo codificado con UTF-8 (`C:\SampleFolder\SampleData3.txt`) que contenga el ejemplo de instancia siguiente que especifica el esquema de codificación `UTF-8` .</span><span class="sxs-lookup"><span data-stu-id="c380c-130">Before you can run example A, you must create a UTF-8 encoded file (`C:\SampleFolder\SampleData3.txt`) that contains the following sample instance that specifies the `UTF-8` encoding scheme.</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<Root>  
          <ProductDescription ProductModelID="5">  
             <Summary>Some Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-a"></a><span data-ttu-id="c380c-131">Ejemplo A</span><span class="sxs-lookup"><span data-stu-id="c380c-131">Example A</span></span>  
 <span data-ttu-id="c380c-132">Este ejemplo utiliza la opción `SINGLE_BLOB` en una instrucción `INSERT ... SELECT * FROM OPENROWSET(BULK...)` para importar datos de un archivo llamado `SampleData3.txt` e insertar una instancia XML en la tabla de ejemplo de una sola columna `T`.</span><span class="sxs-lookup"><span data-stu-id="c380c-132">This example uses the `SINGLE_BLOB` option in an `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement to import data from a file named `SampleData3.txt` and insert an XML instance in the single-column table, sample table `T`.</span></span>  
  
```  
INSERT INTO T(XmlCol)  
SELECT * FROM OPENROWSET(  
   BULK 'c:\SampleFolder\SampleData3.txt',  
   SINGLE_BLOB) AS x;  
```  
  
#### <a name="remarks"></a><span data-ttu-id="c380c-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c380c-133">Remarks</span></span>  
 <span data-ttu-id="c380c-134">Si usa SINGLE_BLOB en este caso, puede evitar una discrepancia entre la codificación del documento XML (especificada por la declaración de codificación XML) y la página de códigos de cadena establecida implícitamente por el servidor.</span><span class="sxs-lookup"><span data-stu-id="c380c-134">By using SINGLE_BLOB in this case, you can avoid a mismatch between the encoding of the XML document (as specified by the XML encoding declaration) and the string codepage implied by the server.</span></span>  
  
 <span data-ttu-id="c380c-135">Si utiliza tipos de datos NCLOB o CLOB y se produce un conflicto de página de códigos o de codificación, deberá realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="c380c-135">If you use NCLOB or CLOB data types and run into a codepage or encoding conflict, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="c380c-136">Elimine la declaración XML para poder importar correctamente el contenido del archivo de datos XML.</span><span class="sxs-lookup"><span data-stu-id="c380c-136">Remove the XML declaration to successfully import the contents of the XML data file.</span></span>  
  
-   <span data-ttu-id="c380c-137">Especifique una página de códigos en la opción CODEPAGE de la consulta que coincida con el esquema de codificación que se utiliza en la declaración XML.</span><span class="sxs-lookup"><span data-stu-id="c380c-137">Specify a code page in the CODEPAGE option of the query that matches the encoding scheme that is used in the XML declaration.</span></span>  
  
-   <span data-ttu-id="c380c-138">Compare o resuelva los valores de intercalación de base de datos con un esquema de codificación XML distinto de Unicode.</span><span class="sxs-lookup"><span data-stu-id="c380c-138">Match, or resolve, the database collation settings with a non-Unicode XML encoding scheme.</span></span>  
  
 [<span data-ttu-id="c380c-139">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="c380c-139">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="b-bulk-importing-xml-data-in-an-existing-row"></a><a name="existing_row"></a> <span data-ttu-id="c380c-140">B.</span><span class="sxs-lookup"><span data-stu-id="c380c-140">B.</span></span> <span data-ttu-id="c380c-141">Importar de forma masiva datos XML en una fila existente</span><span class="sxs-lookup"><span data-stu-id="c380c-141">Bulk importing XML data in an existing row</span></span>  
 <span data-ttu-id="c380c-142">Este ejemplo utiliza el el proveedor de conjuntos de filas BULK `OPENROWSET` para agregar una instancia XML a una fila o filas existentes en la tabla de ejemplo `T`.</span><span class="sxs-lookup"><span data-stu-id="c380c-142">This example uses the `OPENROWSET` bulk rowset provider to add an XML instance to an existing row or rows in sample table `T`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c380c-143">Para ejecutar este ejemplo, es necesario que complete primero el script de prueba del ejemplo A. Ese ejemplo crea la tabla `tempdb.dbo.T` e importa los datos de forma masiva de `SampleData3.txt`.</span><span class="sxs-lookup"><span data-stu-id="c380c-143">To run this example, you must first complete the test script provided in example A. That example creates the `tempdb.dbo.T` table and bulk imports data from `SampleData3.txt`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="c380c-144">Archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c380c-144">Sample Data File</span></span>  
 <span data-ttu-id="c380c-145">El ejemplo B utiliza una versión modificada del archivo de datos de ejemplo `SampleData3.txt` del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c380c-145">Example B uses a modified version of the `SampleData3.txt` sample data file from the preceding example.</span></span> <span data-ttu-id="c380c-146">Para ejecutar este ejemplo, modifique el contenido de este archivo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c380c-146">To run this example, modify the content of this file as follows:</span></span>  
  
```  
<Root>  
          <ProductDescription ProductModelID="10">  
             <Summary>Some New Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-b"></a><span data-ttu-id="c380c-147">Ejemplo B</span><span class="sxs-lookup"><span data-stu-id="c380c-147">Example B</span></span>  
  
```  
-- Query before update shows initial state of XmlCol values.  
SELECT * FROM T  
UPDATE T  
SET XmlCol =(  
SELECT * FROM OPENROWSET(  
   BULK 'C:\SampleFolder\SampleData3.txt',  
           SINGLE_BLOB  
) AS x  
)  
WHERE IntCol = 1;  
GO  
```  
  
 [<span data-ttu-id="c380c-148">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="c380c-148">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="c-bulk-importing-xml-data-from-a-file-that-contains-a-dtd"></a><a name="file_contains_dtd"></a> <span data-ttu-id="c380c-149">C.</span><span class="sxs-lookup"><span data-stu-id="c380c-149">C.</span></span> <span data-ttu-id="c380c-150">Importar de forma masiva datos XML a partir de un archivo que contiene una DTD</span><span class="sxs-lookup"><span data-stu-id="c380c-150">Bulk importing XML data from a file that contains a DTD</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c380c-151">Se recomienda no habilitar la compatibilidad con definiciones de tipo de documento (DTD) si no es necesaria en el entorno XML.</span><span class="sxs-lookup"><span data-stu-id="c380c-151">We recommended that you not enable support for Document Type Definitions (DTDs) if it is not required in your XML environment.</span></span> <span data-ttu-id="c380c-152">Si se activa la compatibilidad con DTD, se aumenta el área expuesta susceptible de ataques del servidor, que puede quedar expuesta a un ataque por denegación de servicio.</span><span class="sxs-lookup"><span data-stu-id="c380c-152">Turning on DTD support increases the attackable surface area of your server, and may expose it to a denial-of-service attack.</span></span> <span data-ttu-id="c380c-153">En caso de que sea necesario habilitar la compatibilidad con DTD, este riesgo de seguridad puede reducirse procesando únicamente los documentos XML de confianza.</span><span class="sxs-lookup"><span data-stu-id="c380c-153">If you must enable DTD support, you can reduce this security risk by processing only trusted XML documents.</span></span>  
  
 <span data-ttu-id="c380c-154">Al intentar utilizar un comando [bcp](../../tools/bcp-utility.md) para importar datos XML de un archivo que contenga una DTD, puede producirse un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c380c-154">During an attempt to use a [bcp](../../tools/bcp-utility.md) command to import XML data from a file that contains a DTD, an error similar to the following can occur:</span></span>  
  
 <span data-ttu-id="c380c-155">"SQLState = 42000, NativeError = 6359"</span><span class="sxs-lookup"><span data-stu-id="c380c-155">"SQLState = 42000, NativeError = 6359"</span></span>  
  
 <span data-ttu-id="c380c-156">"Error = [Microsoft][SQL Server Native Client][ SQL Server]No se permite analizar XML con DTD de un subconjunto interno.</span><span class="sxs-lookup"><span data-stu-id="c380c-156">"Error = [Microsoft][SQL Server Native Client][ SQL Server]Parsing XML with internal subset DTDs not allowed.</span></span> <span data-ttu-id="c380c-157">Utilice CONVERT con la opción de estilo 2 para habilitar la compatibilidad limitada con DTD de subconjuntos internos."</span><span class="sxs-lookup"><span data-stu-id="c380c-157">Use CONVERT with style option 2 to enable limited internal subset DTD support."</span></span>  
  
 <span data-ttu-id="c380c-158">"Error de copia de %s en BCP"</span><span class="sxs-lookup"><span data-stu-id="c380c-158">"BCP copy %s failed"</span></span>  
  
 <span data-ttu-id="c380c-159">Para solucionar este problema, puede importar datos XML de un archivo de datos que contenga una DTD mediante la función `OPENROWSET(BULK...)` y especificando posteriormente la opción `CONVERT` en la cláusula `SELECT` del comando.</span><span class="sxs-lookup"><span data-stu-id="c380c-159">To work around this problem, you can import XML data from a data file that contains a DTD by using the `OPENROWSET(BULK...)` function and then specifying the `CONVERT` option in the `SELECT` clause of the command.</span></span> <span data-ttu-id="c380c-160">La sintaxis básica para el comando es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="c380c-160">The basic syntax for the command is:</span></span>  
  
 `INSERT ... SELECT CONVERT(...) FROM OPENROWSET(BULK...)`  
  
#### <a name="sample-data-file"></a><span data-ttu-id="c380c-161">Archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c380c-161">Sample Data File</span></span>  
 <span data-ttu-id="c380c-162">Para probar este ejemplo de importación en bloque, cree un archivo (`C:\temp\Dtdfile.xml`) que contenga la siguiente instancia de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c380c-162">Before you can test this bulk import example, create a file (`C:\temp\Dtdfile.xml`) that contains the following sample instance:</span></span>  
  
```  
<!DOCTYPE DOC [<!ATTLIST elem1 attr1 CDATA "defVal1">]><elem1>January</elem1>  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="c380c-163">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c380c-163">Sample Table</span></span>  
 <span data-ttu-id="c380c-164">El ejemplo C utiliza la tabla de ejemplo `T1` que crea la instrucción `CREATE TABLE` siguiente:</span><span class="sxs-lookup"><span data-stu-id="c380c-164">Example C uses the `T1` sample table that is created by the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE T1(XmlCol xml);  
GO  
```  
  
#### <a name="example-c"></a><span data-ttu-id="c380c-165">Ejemplo C</span><span class="sxs-lookup"><span data-stu-id="c380c-165">Example C</span></span>  
 <span data-ttu-id="c380c-166">Este ejemplo utiliza `OPENROWSET(BULK...)` y especifica la opción `CONVERT` en la cláusula `SELECT` para importar los datos XML desde `Dtdfile.xml` al ejemplo de tabla `T1`.</span><span class="sxs-lookup"><span data-stu-id="c380c-166">This example uses `OPENROWSET(BULK...)` and specifies the `CONVERT` option in the `SELECT` clause to import the XML data from `Dtdfile.xml` into sample table `T1`.</span></span>  
  
```  
INSERT T1  
  SELECT CONVERT(xml, BulkColumn, 2) FROM   
    OPENROWSET(Bulk 'c:\temp\Dtdfile.xml', SINGLE_BLOB) [rowsetresults];  
```  
  
 <span data-ttu-id="c380c-167">Después de ejecutar la instrucción `INSERT` , se quitará la DTD del XML y se almacenará en la tabla `T1` .</span><span class="sxs-lookup"><span data-stu-id="c380c-167">After the `INSERT` statement executes, the DTD is stripped from the XML and stored in the `T1` table.</span></span>  
  
 [<span data-ttu-id="c380c-168">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="c380c-168">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="d-specifying-the-field-terminator-explicitly-using-a-format-file"></a><a name="field_terminator_in_format_file"></a> <span data-ttu-id="c380c-169">D.</span><span class="sxs-lookup"><span data-stu-id="c380c-169">D.</span></span> <span data-ttu-id="c380c-170">Especificar el terminador de campo explícitamente mediante el uso de un archivo de formato</span><span class="sxs-lookup"><span data-stu-id="c380c-170">Specifying the field terminator explicitly using a format file</span></span>  
 <span data-ttu-id="c380c-171">El ejemplo siguiente muestra cómo importar de forma masiva el siguiente documento XML, `Xmltable.dat`.</span><span class="sxs-lookup"><span data-stu-id="c380c-171">The following example shows how to bulk import the following XML document, `Xmltable.dat`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="c380c-172">Archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c380c-172">Sample Data File</span></span>  
 <span data-ttu-id="c380c-173">El documento en `Xmltable.dat` contiene dos valores XML, uno para cada fila.</span><span class="sxs-lookup"><span data-stu-id="c380c-173">The document in `Xmltable.dat` contains two XML values, one for each row.</span></span> <span data-ttu-id="c380c-174">El primer valor XML está codificado con UTF-16 y el segundo con UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c380c-174">The first XML value is encoded with UTF-16, and the second value is encoded with UTF-8.</span></span>  
  
 <span data-ttu-id="c380c-175">El contenido de este archivo de datos se muestra en el volcado Hex siguiente:</span><span class="sxs-lookup"><span data-stu-id="c380c-175">The contents of this data file are shown in the following Hex dump:</span></span>  
  
```  
FF FE 3C 00 3F 00 78 00-6D 00 6C 00 20 00 76 00  *..<.?.x.m.l. .v.*  
65 00 72 00 73 00 69 00-6F 00 6E 00 3D 00 22 00  *e.r.s.i.o.n.=.".*  
31 00 2E 00 30 00 22 00-20 00 65 00 6E 00 63 00  *1...0.". .e.n.c.*  
6F 00 64 00 69 00 6E 00-67 00 3D 00 22 00 75 00  *o.d.i.n.g.=.".u.*  
74 00 66 00 2D 00 31 00-36 00 22 00 3F 00 3E 00  *t.f.-.1.6.".?.>.*  
3C 00 72 00 6F 00 6F 00-74 00 3E 00 A2 4F 9C 76  *<.r.o.o.t.>..O.v*  
0C FA 77 E4 80 00 89 00-00 06 90 06 91 2E 9B 2E  *..w.............*  
99 34 A2 34 86 00 83 02-92 20 7F 02 4E C5 E4 A3  *.4.4..... ..N...*  
34 B2 B7 B3 B7 FE F8 FF-F8 00 3C 00 2F 00 72 00  *4.........<./.r.*  
6F 00 6F 00 74 00 3E 00-00 00 00 00 7A EF BB BF  *o.o.t.>.....z...*  
3C 3F 78 6D 6C 20 76 65-72 73 69 6F 6E 3D 22 31  *<?xml version="1*  
2E 30 22 20 65 6E 63 6F-64 69 6E 67 3D 22 75 74  *.0" encoding="ut*  
66 2D 38 22 3F 3E 3C 72-6F 6F 74 3E E4 BE A2 E7  *f-8"?><root>....*  
9A 9C EF A8 8C EE 91 B7-C2 80 C2 89 D8 80 DA 90  *................*  
E2 BA 91 E2 BA 9B E3 92-99 E3 92 A2 C2 86 CA 83  *................*  
E2 82 92 C9 BF EC 95 8E-EA 8F A4 EB 88 B4 EB 8E  *................*  
B7 EF BA B7 EF BF B8 C3-B8 3C 2F 72 6F 6F 74 3E  *.........</root>*  
00 00 00 00 7A                                   *....z*  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="c380c-176">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c380c-176">Sample Table</span></span>  
 <span data-ttu-id="c380c-177">Al realizar una importación o exportación masiva de un documento XML, hay que usar un [terminador de campo](specify-field-and-row-terminators-sql-server.md) que no pueda aparecer en ninguno de los documentos; por ejemplo, una serie de cuatro valores NULL (`\0`) seguidos de la letra `z`: `\0\0\0\0z`.</span><span class="sxs-lookup"><span data-stu-id="c380c-177">When you bulk import or export an XML document, you should use a [field terminator](specify-field-and-row-terminators-sql-server.md) that cannot possibly appear in any of the documents; for example, a series of four nulls (`\0`) followed by the letter `z`: `\0\0\0\0z`.</span></span>  
  
 <span data-ttu-id="c380c-178">Este ejemplo muestra cómo utilizar el terminador de campo para la tabla de ejemplo `xTable` .</span><span class="sxs-lookup"><span data-stu-id="c380c-178">This example shows how to use this field terminator for the `xTable` sample table.</span></span> <span data-ttu-id="c380c-179">Para crear esta vista de ejemplo, utilice la siguiente instrucción `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="c380c-179">To create this sample table, use the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE xTable (xCol xml);  
GO  
```  
  
#### <a name="sample-format-file"></a><span data-ttu-id="c380c-180">Archivo de formato de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c380c-180">Sample Format File</span></span>  
 <span data-ttu-id="c380c-181">El terminador de campo se debe especificar en el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="c380c-181">The field terminator must be specified in the format file.</span></span> <span data-ttu-id="c380c-182">El ejemplo D utiliza un archivo de formato no XML denominado `Xmltable.fmt` que contiene lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c380c-182">Example D uses a non-XML format file named `Xmltable.fmt` that contains the following:</span></span>  
  
```  
9.0  
1  
1       SQLBINARY     0       0       "\0\0\0\0z"    1     xCol         ""  
```  
  
 <span data-ttu-id="c380c-183">Puede utilizar este archivo de formato para realizar importaciones masivas de documentos XML a la tabla `xTable` mediante el comando `bcp` o una instrucción `BULK INSERT` o `INSERT ... SELECT * FROM OPENROWSET(BULK...)` .</span><span class="sxs-lookup"><span data-stu-id="c380c-183">You can use this format file to bulk import XML documents into the `xTable` table by using a `bcp` command or a `BULK INSERT` or `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="c380c-184">Ejemplo D</span><span class="sxs-lookup"><span data-stu-id="c380c-184">Example D</span></span>  
 <span data-ttu-id="c380c-185">Este ejemplo utiliza el archivo de formato `Xmltable.fmt` en una instrucción `BULK INSERT` para importar el contenido de un archivo de datos XML denominado `Xmltable.dat`.</span><span class="sxs-lookup"><span data-stu-id="c380c-185">This example uses the `Xmltable.fmt` format file in a `BULK INSERT` statement to import the contents of an XML data file named `Xmltable.dat`.</span></span>  
  
```  
BULK INSERT xTable   
FROM 'C:\Xmltable.dat'  
WITH (FORMATFILE = 'C:\Xmltable.fmt');  
GO  
```  
  
 [<span data-ttu-id="c380c-186">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="c380c-186">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="e-bulk-exporting-xml-data"></a><a name="bulk_export_xml_data"></a> <span data-ttu-id="c380c-187">E.</span><span class="sxs-lookup"><span data-stu-id="c380c-187">E.</span></span> <span data-ttu-id="c380c-188">Exportar de forma masiva datos XML</span><span class="sxs-lookup"><span data-stu-id="c380c-188">Bulk exporting XML data</span></span>  
 <span data-ttu-id="c380c-189">En el ejemplo siguiente se utiliza `bcp` para realizar la exportación masiva de datos XML a partir de la tabla creada en el ejemplo anterior con el mismo archivo de formato XML.</span><span class="sxs-lookup"><span data-stu-id="c380c-189">The following example uses `bcp` to bulk export XML data from the table that is created in the preceding example by using the same XML format file.</span></span> <span data-ttu-id="c380c-190">En el siguiente comando `bcp` , `<server_name>` y `<instance_name>` representan los marcadores de posición que deben ser reemplazados con los valores adecuados:</span><span class="sxs-lookup"><span data-stu-id="c380c-190">In the following `bcp` command, `<server_name>` and `<instance_name>` represent placeholders that must be replaced with appropriate values:</span></span>  
  
```  
bcp bulktest..xTable out a-wn.out -N -T -S<server_name>\<instance_name>  
```  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c380c-191">no guarda la codificación XML cuando se mantienen datos XML en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="c380c-191">does not save the XML encoding when XML data is persisted in the database.</span></span> <span data-ttu-id="c380c-192">Por lo tanto, la codificación original de los campos XML no estará disponible cuando se exporten datos XML.</span><span class="sxs-lookup"><span data-stu-id="c380c-192">Therefore, the original encoding of XML fields is not available when XML data is exported.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c380c-193">usa la codificación UTF-16 al exportar datos XML.</span><span class="sxs-lookup"><span data-stu-id="c380c-193">uses UTF-16 encoding when exporting XML data.</span></span>  
  
 [<span data-ttu-id="c380c-194">&#91;Principio&#93;</span><span class="sxs-lookup"><span data-stu-id="c380c-194">&#91;Top&#93;</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="c380c-195">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c380c-195">See Also</span></span>  
 <span data-ttu-id="c380c-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c380c-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="c380c-197">[SELECT &#40;cláusula de Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c380c-197">[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span></span>  
 <span data-ttu-id="c380c-198">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="c380c-198">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="c380c-199">[Importar y exportar datos en bloque &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c380c-199">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="c380c-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c380c-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="c380c-201">OPENROWSET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c380c-201">OPENROWSET &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openrowset-transact-sql)  
  
  
