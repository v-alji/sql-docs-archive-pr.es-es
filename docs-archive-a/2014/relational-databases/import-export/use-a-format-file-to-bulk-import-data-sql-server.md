---
title: Usar un archivo de formato para importar datos en bloque (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], format files
- format files [SQL Server], importing data using
ms.assetid: 2956df78-833f-45fa-8a10-41d6522562b9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6d9779209b3ffb317658243c168d74740f6731b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678192"
---
# <a name="use-a-format-file-to-bulk-import-data-sql-server"></a><span data-ttu-id="ccb12-102">Usar un archivo de formato para importar datos de forma masiva (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ccb12-102">Use a Format File to Bulk Import Data (SQL Server)</span></span>
  <span data-ttu-id="ccb12-103">En este tema se describe cómo usar un archivo de formato en operaciones de importación masiva.</span><span class="sxs-lookup"><span data-stu-id="ccb12-103">This topic illustrates the use of a format file in bulk-import operations.</span></span> <span data-ttu-id="ccb12-104">El archivo de formato asigna los campos del archivo de datos a las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ccb12-104">The format file maps the fields of the data file to the columns of the table.</span></span>  <span data-ttu-id="ccb12-105">Puede usar un archivo de formato XML o no XML para importar datos de forma masiva al usar un comando **BCP** o un Bulk Insert o INSERT... SELECT \* FROM OPENROWSET (BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] Command.</span><span class="sxs-lookup"><span data-stu-id="ccb12-105">You can use a non-XML or XML format file to bulk import data when using a **bcp** command or a BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ccb12-106">Para que un archivo de formato trabaje con un archivo de datos de caracteres Unicode, todos los campos de entrada deben ser cadenas de texto Unicode (es decir, de tamaño fijo o cadenas Unicode terminadas en caracteres).</span><span class="sxs-lookup"><span data-stu-id="ccb12-106">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccb12-107">Si no está familiarizado con los archivos de formato, vea [archivos de formato no XML &#40;SQL Server](xml-format-files-sql-server.md) [archivos de formato xml y&#41;&#40;SQL Server ](xml-format-files-sql-server.md)&#41;.</span><span class="sxs-lookup"><span data-stu-id="ccb12-107">If you are unfamiliar with format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) and [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="format-file-options-for-bulk-import-commands"></a><span data-ttu-id="ccb12-108">Opciones de los archivos de formato para los comandos de importación masiva</span><span class="sxs-lookup"><span data-stu-id="ccb12-108">Format File Options for Bulk-Import Commands</span></span>  
 <span data-ttu-id="ccb12-109">La siguiente tabla resume la opción de archivo de formato para cada uno de los comandos de importación masiva.</span><span class="sxs-lookup"><span data-stu-id="ccb12-109">The following table summarizes the format-file option of for each of the bulk-import commands.</span></span>  
  
|<span data-ttu-id="ccb12-110">Comando de carga masiva</span><span class="sxs-lookup"><span data-stu-id="ccb12-110">Bulk-load Command</span></span>|<span data-ttu-id="ccb12-111">Opción de archivo de formato</span><span class="sxs-lookup"><span data-stu-id="ccb12-111">Using the Format-File Option</span></span>|  
|------------------------|-----------------------------------|  
|<span data-ttu-id="ccb12-112">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="ccb12-112">BULK INSERT</span></span>|<span data-ttu-id="ccb12-113">FORMATFILE = '*format_file_path*'</span><span class="sxs-lookup"><span data-stu-id="ccb12-113">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="ccb12-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="ccb12-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="ccb12-115">FORMATFILE = '*format_file_path*'</span><span class="sxs-lookup"><span data-stu-id="ccb12-115">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="ccb12-116">**BCP** ... **en**</span><span class="sxs-lookup"><span data-stu-id="ccb12-116">**bcp** ... **in**</span></span>|<span data-ttu-id="ccb12-117">**-f** *format_file*</span><span class="sxs-lookup"><span data-stu-id="ccb12-117">**-f** *format_file*</span></span>|  
  
 <span data-ttu-id="ccb12-118">Para obtener más información, vea [bcp (utilidad)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) u [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ccb12-118">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ccb12-119">Para importar o exportar de forma masiva datos SQLXML, utilice uno de los tipos de datos siguientes en el archivo de formato: SQLCHAR o SQLVARYCHAR (los datos se envían en la página de códigos del cliente o en la página de códigos implícita en la intercalación), SQLNCHAR o SQLNVARCHAR (los datos se envían como Unicode), o SQLBINARY o SQLVARYBIN (los datos se envían sin ninguna conversión).</span><span class="sxs-lookup"><span data-stu-id="ccb12-119">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ccb12-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ccb12-120">Examples</span></span>  
 <span data-ttu-id="ccb12-121">En los ejemplos de esta sección se muestra cómo usar archivos de formato para importar datos de forma masiva mediante el comando **BCP** y el Bulk Insert e insertar... Instrucciones SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="ccb12-121">The examples in this section illustrate how to use format files to bulk-import data by using the **bcp** command and the BULK INSERT, and INSERT ... SELECT \* FROM OPENROWSET(BULK...) statements.</span></span> <span data-ttu-id="ccb12-122">Para poder ejecutar los ejemplos de importación masiva, debe crear una tabla, un archivo de datos y un archivo de formato de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ccb12-122">Before you can run one of the bulk-import examples, you need to create a sample table, data file, and a format file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="ccb12-123">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccb12-123">Sample Table</span></span>  
 <span data-ttu-id="ccb12-124">Los ejemplos requieren la creación de una tabla denominada **myTestFormatFiles** en la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] , bajo el esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="ccb12-124">The examples require that a table named **myTestFormatFiles** table be created in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="ccb12-125">Para crear esta tabla, en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , ejecute:</span><span class="sxs-lookup"><span data-stu-id="ccb12-125">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestFormatFiles (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50),  
   Col4 nvarchar(50)  
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="ccb12-126">Archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccb12-126">Sample Data File</span></span>  
 <span data-ttu-id="ccb12-127">Los ejemplos utilizan un archivo de datos de ejemplo, `myTestFormatFiles-c.Dat`, que contiene los siguientes registros.</span><span class="sxs-lookup"><span data-stu-id="ccb12-127">The examples use a sample data file, `myTestFormatFiles-c.Dat`, which contains the following records.</span></span> <span data-ttu-id="ccb12-128">Para crear el archivo de datos, en el símbolo del sistema de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, escriba:</span><span class="sxs-lookup"><span data-stu-id="ccb12-128">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
10,Field2,Field3,Field4  
15,Field2,Field3,Field4  
46,Field2,Field3,Field4  
58,Field2,Field3,Field4  
```  
  
### <a name="sample-format-files"></a><span data-ttu-id="ccb12-129">Archivos de formato de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccb12-129">Sample Format Files</span></span>  
 <span data-ttu-id="ccb12-130">Algunos ejemplos de esta sección utilizan un archivo de formato XML, `myTestFormatFiles-f-x-c.Xml`, mientras que otros ejemplos utilizan un archivo sin formato XML.</span><span class="sxs-lookup"><span data-stu-id="ccb12-130">Some of the examples in this section use an XML format file, `myTestFormatFiles-f-x-c.Xml`, and other examples use a non-XML format file.</span></span> <span data-ttu-id="ccb12-131">Ambos archivos de formato usan formatos de datos de caracteres y un terminador de campo que no es el predeterminado (,).</span><span class="sxs-lookup"><span data-stu-id="ccb12-131">Both format files use character data formats and a non-default field terminator (,).</span></span>  
  
#### <a name="the-sample-non-xml-format-file"></a><span data-ttu-id="ccb12-132">Archivo de formato no XML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccb12-132">The Sample Non-XML Format File</span></span>  
 <span data-ttu-id="ccb12-133">En el siguiente ejemplo se usa **bcp** para generar un archivo de formato XML a partir de la tabla `myTestFormatFiles` .</span><span class="sxs-lookup"><span data-stu-id="ccb12-133">The following example uses **bcp** to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="ccb12-134">El archivo `myTestFormatFiles.Fmt` incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ccb12-134">The `myTestFormatFiles.Fmt` file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     Col1         ""  
2       SQLCHAR       0       100     ","      2     Col2         SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      3     Col3         SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   4     Col4         SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="ccb12-135">Para usar **bcp** con la opción **format** para crear este archivo de formato, en el símbolo del sistema de Windows, escriba:</span><span class="sxs-lookup"><span data-stu-id="ccb12-135">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -f myTestFormatFiles.Fmt -T  
  
```  
  
 <span data-ttu-id="ccb12-136">Para obtener más información sobre cómo crear un archivo de formato, vea [Crear un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ccb12-136">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
#### <a name="the-sample-xml-format-file"></a><span data-ttu-id="ccb12-137">Archivo de formato XML de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ccb12-137">The Sample XML Format File</span></span>  
 <span data-ttu-id="ccb12-138">En el siguiente ejemplo se usa **bcp** para generar un archivo de formato XML a partir de la tabla `myTestFormatFiles` .</span><span class="sxs-lookup"><span data-stu-id="ccb12-138">The following example uses **bcp** to create to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="ccb12-139">El archivo `myTestFormatFiles.Xml` incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ccb12-139">The `myTestFormatFiles.Xml` file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="ccb12-140">Para usar **bcp** con la opción **format** para crear este archivo de formato, en el símbolo del sistema de Windows, escriba:</span><span class="sxs-lookup"><span data-stu-id="ccb12-140">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -x -f myTestFormatFiles.Xml -T  
```  
  
### <a name="using-bcp"></a><span data-ttu-id="ccb12-141">Usar bcp</span><span class="sxs-lookup"><span data-stu-id="ccb12-141">Using bcp</span></span>  
 <span data-ttu-id="ccb12-142">En el siguiente ejemplo se usa **bcp** para importar datos en bloque desde el archivo de datos `myTestFormatFiles-c.Dat` a la tabla `HumanResources.myTestFormatFiles` en la base de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ccb12-142">The following example uses **bcp** to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the  sample database.</span></span> <span data-ttu-id="ccb12-143">Este ejemplo utiliza un archivo de formato XML, `MyTestFormatFiles.Xml`.</span><span class="sxs-lookup"><span data-stu-id="ccb12-143">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="ccb12-144">El ejemplo elimina todas las filas existentes en la tabla antes de importar el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="ccb12-144">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="ccb12-145">En el símbolo del sistema de Windows, escriba:</span><span class="sxs-lookup"><span data-stu-id="ccb12-145">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestFormatFiles in C:\myTestFormatFiles-c.Dat -f C:\myTestFormatFiles.Xml -T  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ccb12-146">Para obtener más información sobre este comando, vea [bcp (utilidad)](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ccb12-146">For more information about this command, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
### <a name="using-bulk-insert"></a><span data-ttu-id="ccb12-147">Usar BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="ccb12-147">Using BULK INSERT</span></span>  
 <span data-ttu-id="ccb12-148">El siguiente ejemplo usa BULK INSERT para importar datos de forma masiva desde el archivo de datos `myTestFormatFiles-c.Dat` a la tabla `HumanResources.myTestFormatFiles` de la base de datos de ejemplo  [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ccb12-148">The following example uses BULK INSERT to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="ccb12-149">Este ejemplo utiliza un archivo sin formato XML, `MyTestFormatFiles.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="ccb12-149">This example uses a non-XML format file, `MyTestFormatFiles.Fmt`.</span></span> <span data-ttu-id="ccb12-150">El ejemplo elimina todas las filas existentes en la tabla antes de importar el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="ccb12-150">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="ccb12-151">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="ccb12-151">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DELETE myTestFormatFiles;  
GO  
BULK INSERT myTestFormatFiles   
   FROM 'C:\myTestFormatFiles-c.Dat'   
   WITH (FORMATFILE = 'C:\myTestFormatFiles.Fmt');  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ccb12-152">Para obtener más información sobre esta instrucción, vea [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ccb12-152">For more information about this statement, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="using-the-openrowset-bulk-rowset-provider"></a><span data-ttu-id="ccb12-153">Usar el proveedor de conjunto de filas BULK OPENROWSET</span><span class="sxs-lookup"><span data-stu-id="ccb12-153">Using the OPENROWSET Bulk Rowset Provider</span></span>  
 <span data-ttu-id="ccb12-154">El siguiente ejemplo usa `INSERT ... SELECT * FROM OPENROWSET(BULK...)` para importar datos de forma masiva desde el archivo de datos `myTestFormatFiles-c.Dat` a la tabla `HumanResources.myTestFormatFiles` de la base de datos de ejemplo de `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="ccb12-154">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the `AdventureWorks` sample database.</span></span> <span data-ttu-id="ccb12-155">Este ejemplo utiliza un archivo de formato XML, `MyTestFormatFiles.Xml`.</span><span class="sxs-lookup"><span data-stu-id="ccb12-155">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="ccb12-156">El ejemplo elimina todas las filas existentes en la tabla antes de importar el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="ccb12-156">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="ccb12-157">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="ccb12-157">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
DELETE myTestFormatFiles;  
GO  
INSERT INTO myTestFormatFiles  
    SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestFormatFiles-c.Dat',  
      FORMATFILE='C:\myTestFormatFiles.Xml'       
      ) as t1 ;  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
 <span data-ttu-id="ccb12-158">Cuando haya terminado de utilizar la tabla de ejemplo, puede eliminarse con la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="ccb12-158">When you finish using the sample table, you can drop it using the following statement:</span></span>  
  
```  
DROP TABLE myTestFormatFiles  
```  
  
> [!NOTE]  
>  <span data-ttu-id="ccb12-159">Para obtener más información sobre la cláusula OPENROWSET BULK, vea [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ccb12-159">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="ccb12-160">Otros ejemplos</span><span class="sxs-lookup"><span data-stu-id="ccb12-160">Additional Examples</span></span>  
 [<span data-ttu-id="ccb12-161">Crear un archivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ccb12-161">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
 [<span data-ttu-id="ccb12-162">Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ccb12-162">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 [<span data-ttu-id="ccb12-163">Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ccb12-163">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
 [<span data-ttu-id="ccb12-164">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ccb12-164">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="ccb12-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ccb12-165">See Also</span></span>  
 <span data-ttu-id="ccb12-166">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="ccb12-166">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="ccb12-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ccb12-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="ccb12-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ccb12-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="ccb12-169">[Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ccb12-169">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="ccb12-170">XML, archivos de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ccb12-170">XML Format Files &#40;SQL Server&#41;</span></span>](xml-format-files-sql-server.md)  
  
  
