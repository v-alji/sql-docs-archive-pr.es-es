---
title: Usar un archivo de formato para omitir un campo de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], skipping data fields
- skipping data fields when importing
ms.assetid: 6a76517e-983b-47a1-8f02-661b99859a8b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d3f78c3c97c5bbe862867d5f51ff35f57d147df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678191"
---
# <a name="use-a-format-file-to-skip-a-data-field-sql-server"></a><span data-ttu-id="60ea9-102">Usar un archivo de formato para omitir un campo de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="60ea9-102">Use a Format File to Skip a Data Field (SQL Server)</span></span>
  <span data-ttu-id="60ea9-103">Un archivo de datos puede contener más campos que el número de columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="60ea9-103">A data file can contain more fields than the number of columns in the table.</span></span> <span data-ttu-id="60ea9-104">En este tema se describe la modificación de archivos de formato XML y no XML para adaptarse a un archivo de datos con más campos asignando las columnas de la tabla a los campos de datos correspondientes y omitiendo los campos adicionales.</span><span class="sxs-lookup"><span data-stu-id="60ea9-104">This topic describes modifying both non-XML and XML format files to accommodate a data file with more fields by mapping the table columns to the corresponding data fields and ignoring the extra fields.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="60ea9-105">Se puede usar un archivo de formato XML o no XML para realizar una importación masiva de un archivo de datos en la tabla mediante un comando **BCP** , una instrucción BULK INSERT o una instrucción INSERT... SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="60ea9-105">Either a non-XML or XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="60ea9-106">Para obtener más información, vea [Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="60ea9-106">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-data-file-and-table"></a><span data-ttu-id="60ea9-107">Archivo de datos y tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="60ea9-107">Sample Data File and Table</span></span>  
 <span data-ttu-id="60ea9-108">Los ejemplos de archivos de formato modificados de este tema se basan en la siguiente tabla y archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="60ea9-108">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="60ea9-109">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="60ea9-109">Sample Table</span></span>  
 <span data-ttu-id="60ea9-110">Los ejemplos requieren la creación de una tabla denominada `myTestSkipField` en la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] , bajo el esquema `dbo` .</span><span class="sxs-lookup"><span data-stu-id="60ea9-110">The examples require that a table named `myTestSkipField` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="60ea9-111">Para crear esta tabla, en [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] el editor de consultas, ejecute el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="60ea9-111">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestSkipField   
   (  
   PersonID smallint,  
   FirstName nvarchar(50) ,  
   LastName nvarchar(50)   
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="60ea9-112">Archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="60ea9-112">Sample Data File</span></span>  
 <span data-ttu-id="60ea9-113">El archivo de datos, `myTestSkipField-c.dat`, contiene los siguientes registros:</span><span class="sxs-lookup"><span data-stu-id="60ea9-113">The data file, `myTestSkipField-c.dat`, contains the following records:</span></span>  
  
```  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
```  
  
 <span data-ttu-id="60ea9-114">Para realizar una importación masiva de datos de `myTestSkipField-c.dat` en la tabla `myTestSkipField` , el archivo de formato debe llevar a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="60ea9-114">To bulk import data from `myTestSkipField-c.dat` into the `myTestSkipField` table, the format file must do the following:</span></span>  
  
-   <span data-ttu-id="60ea9-115">Asignar el primer campo de datos a la primera columna, `PersonID`.</span><span class="sxs-lookup"><span data-stu-id="60ea9-115">Map the first data field to the first column, `PersonID`.</span></span>  
  
-   <span data-ttu-id="60ea9-116">Omitir el segundo campo de datos.</span><span class="sxs-lookup"><span data-stu-id="60ea9-116">Skip the second data field.</span></span>  
  
-   <span data-ttu-id="60ea9-117">Asignar el tercer campo de datos a la segunda columna, `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="60ea9-117">Map the third data field to the second column, `FirstName`.</span></span>  
  
-   <span data-ttu-id="60ea9-118">Asignar el cuarto campo de datos a la tercera columna, `LastName`.</span><span class="sxs-lookup"><span data-stu-id="60ea9-118">Map the fourth data field to the third column, `LastName`.</span></span>  
  
## <a name="non-xml-format-file-for-more-data-fields"></a><span data-ttu-id="60ea9-119">Archivo de formato no XML para más campos de datos</span><span class="sxs-lookup"><span data-stu-id="60ea9-119">Non-XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="60ea9-120">El siguiente archivo de formato, `myTestSkipField.fmt`, asigna los campos de `myTestSkipField-c.dat` a las columnas de la tabla `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="60ea9-120">The following format file, `myTestSkipField.fmt`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="60ea9-121">El archivo de formato utiliza el formato de datos de carácter.</span><span class="sxs-lookup"><span data-stu-id="60ea9-121">The format file uses character data format.</span></span> <span data-ttu-id="60ea9-122">Para omitir la asignación de columnas, es necesario cambiar su valor de orden de columna a 0, como se muestra para la columna `ExtraField` del archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="60ea9-122">Skipping a column mapping requires changing its column order value to 0, as shown for the `ExtraField` column in the format file.</span></span>  
  
 <span data-ttu-id="60ea9-123">El archivo de formato `myTestSkipField.fmt` contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="60ea9-123">The `myTestSkipField.fmt` format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     PersonID               ""  
2       SQLCHAR       0       100       ","    0     ExtraField             SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      2     FirstName              SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   3     LastName               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="60ea9-124">Para obtener más información sobre la sintaxis de los archivos de formato no XML, vea [Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="60ea9-124">For information about the syntax of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="60ea9-125">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="60ea9-125">Examples</span></span>  
 <span data-ttu-id="60ea9-126">En el ejemplo siguiente se utiliza `INSERT ... SELECT * FROM OPENROWSET(BULK...)` , que usa el archivo de formato `myTestSkipField.fmt` .</span><span class="sxs-lookup"><span data-stu-id="60ea9-126">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.fmt` format file.</span></span> <span data-ttu-id="60ea9-127">En el ejemplo se importa masivamente el archivo de datos `myTestSkipField-c.dat` a la tabla `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="60ea9-127">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="60ea9-128">Para crear la tabla y el archivo de datos de ejemplo, vea "Tabla y archivo de datos de ejemplo", anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="60ea9-128">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="60ea9-129">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="60ea9-129">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
   SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.fmt'    
       ) AS t1;  
GO   
```  
  
## <a name="xml-format-file-for-more-data-fields"></a><span data-ttu-id="60ea9-130">Archivo de formato XML para más campos de datos</span><span class="sxs-lookup"><span data-stu-id="60ea9-130">XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="60ea9-131">El archivo de formato presentado en este ejemplo se basa en otro archivo de formato, `myTestSkipField.xml`, que utiliza el formato de datos de carácter y cuyos campos corresponden exactamente en número y orden a las columnas de la tabla `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="60ea9-131">The format file presented in this example is based on another format file, `myTestSkipField.xml`, which uses character data format throughout and whose fields correspond exactly in number and order to the columns in the `myTestSkipField` table.</span></span> <span data-ttu-id="60ea9-132">Para ver el contenido de ese archivo de formato, vea [Crear un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="60ea9-132">To view the contents of that format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
 <span data-ttu-id="60ea9-133">El siguiente archivo de formato, `myTestSkipField.xml`, asigna los campos de `myTestSkipField-c.dat` a las columnas de la tabla `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="60ea9-133">The following format file, `myTestSkipField.xml`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="60ea9-134">El archivo de formato utiliza el formato de datos de carácter.</span><span class="sxs-lookup"><span data-stu-id="60ea9-134">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="60ea9-135">El archivo de formato `myTestSkipField.xml` contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="60ea9-135">The `myTestSkipField.xml` format file contains the following information:</span></span>  
  
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
  <COLUMN SOURCE="1" NAME="PersonID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="3" NAME="FirstName" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="LastName" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
### <a name="examples"></a><span data-ttu-id="60ea9-136">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="60ea9-136">Examples</span></span>  
 <span data-ttu-id="60ea9-137">En el ejemplo siguiente se utiliza `INSERT ... SELECT * FROM OPENROWSET(BULK...)` , que usa el archivo de formato `myTestSkipField.Xml` .</span><span class="sxs-lookup"><span data-stu-id="60ea9-137">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.Xml` format file.</span></span> <span data-ttu-id="60ea9-138">En el ejemplo se importa masivamente el archivo de datos `myTestSkipField-c.dat` a la tabla `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="60ea9-138">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="60ea9-139">Para crear la tabla y el archivo de datos de ejemplo, vea "Tabla y archivo de datos de ejemplo", anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="60ea9-139">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="60ea9-140">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="60ea9-140">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
  SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.xml'    
       ) AS t1;  
GO  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="60ea9-141">Para obtener más información sobre la sintaxis del esquema XML y ejemplos adicionales de archivos de formato XML, vea [XML, archivos de formato &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="60ea9-141">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ea9-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="60ea9-142">See Also</span></span>  
 <span data-ttu-id="60ea9-143">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="60ea9-143">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="60ea9-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="60ea9-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="60ea9-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="60ea9-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="60ea9-146">[Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="60ea9-146">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="60ea9-147">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="60ea9-147">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
  
