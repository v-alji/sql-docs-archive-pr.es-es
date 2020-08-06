---
title: Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- mapping columns to fields during import [SQL Server]
- format files [SQL Server], mapping columns to fields
ms.assetid: e7ee4f7e-24c4-4eb7-84d2-41e57ccc1ef1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7de0b5ce486f187a1bdd27197984aa3c411f4a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670384"
---
# <a name="use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server"></a><span data-ttu-id="6226a-102">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6226a-102">Use a Format File to Map Table Columns to Data-File Fields (SQL Server)</span></span>
  <span data-ttu-id="6226a-103">Un archivo de datos puede contener campos organizados en un orden diferente al de las columnas correspondientes en la tabla.</span><span class="sxs-lookup"><span data-stu-id="6226a-103">A data file can contain fields arranged in a different order from the corresponding columns in the table.</span></span> <span data-ttu-id="6226a-104">Este tema trata los archivos de formato XML y no XML que se han modificado para alojar un archivo de datos cuyos campos están organizados en un orden diferente al de las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6226a-104">This topic presents both non-XML and XML format files that have been modified to accommodate a data file whose fields are arranged in a different order from the table columns.</span></span> <span data-ttu-id="6226a-105">El archivo de formato modificado asigna los campos de datos a las columnas correspondientes de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6226a-105">The modified format file maps the data fields to their corresponding table columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6226a-106">Se puede usar un archivo de formato XML o no XML para importar de forma masiva un archivo de datos en la tabla mediante un comando **BCP** , una instrucción de Bulk Insert o una instrucción INSERT... SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="6226a-106">Either a non-XML format file or an XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="6226a-107">Para obtener más información, vea [Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6226a-107">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="6226a-108">Tabla y archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6226a-108">Sample Table and Data File</span></span>  
 <span data-ttu-id="6226a-109">Los ejemplos de archivos de formato modificados de este tema se basan en la siguiente tabla y archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="6226a-109">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="6226a-110">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6226a-110">Sample Table</span></span>  
 <span data-ttu-id="6226a-111">Los ejemplos de este tema requieren la creación de una tabla denominada `myTestOrder` en la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] , bajo el esquema `dbo` .</span><span class="sxs-lookup"><span data-stu-id="6226a-111">The examples in this topic require that a table named `myTestOrder` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="6226a-112">Para crear esta tabla, en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , ejecute el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="6226a-112">To create this table, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestOrder   
   (  
   Col1 smallint,  
   Col2 nvarchar(50) ,  
   Col3 nvarchar(50) ,   
   Col4 nvarchar(50)   
   );  
GO  
  
```  
  
### <a name="data-file"></a><span data-ttu-id="6226a-113">Archivo de datos</span><span class="sxs-lookup"><span data-stu-id="6226a-113">Data File</span></span>  
 <span data-ttu-id="6226a-114">El archivo de datos, `myTestOrder-c.txt`, contiene los siguientes registros:</span><span class="sxs-lookup"><span data-stu-id="6226a-114">The data file, `myTestOrder-c.txt`, contains the following records:</span></span>  
  
```  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
  
```  
  
 <span data-ttu-id="6226a-115">Para importar masivamente datos desde `myTestSkipCol2-c.dat` a la tabla `myTestSkipCol`, el archivo de formato debe asignar el primer campo de datos a `Col3`, el segundo campo de datos a `Col2`, el tercer campo de datos a `Col1` y el cuarto campo de datos a `Col4`.</span><span class="sxs-lookup"><span data-stu-id="6226a-115">To bulk import data from `myTestSkipCol2-c.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col3`, the second data field to `Col2`, the third data field to `Col1`, and the fourth data field to `Col4`.</span></span>  
  
## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="6226a-116">Usar un archivo de formato no XML</span><span class="sxs-lookup"><span data-stu-id="6226a-116">Using a Non-XML Format File</span></span>  
 <span data-ttu-id="6226a-117">Puede cambiar el orden de asignación de una columna cambiando el valor de orden de la columna para indicar la posición del campo de datos correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6226a-117">You can change the order of a column mapping by changing the order value for the column to indicate the position of the corresponding data field.</span></span>  
  
 <span data-ttu-id="6226a-118">El siguiente archivo de formato no XML de ejemplo presenta un archivo de formato, `myTestOrder.fmt`, que asigna los campos de `myTestOrder-c.txt` a las columnas de la tabla `myTestOrder`.</span><span class="sxs-lookup"><span data-stu-id="6226a-118">The following sample non-XML format file presents a format file, `myTestOrder.fmt`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table.</span></span> <span data-ttu-id="6226a-119">Para obtener información acerca de cómo crear el archivo de datos y la tabla, vea "Tabla y archivo de datos de ejemplo", anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="6226a-119">For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="6226a-120">El archivo de formato utiliza el formato de datos de carácter.</span><span class="sxs-lookup"><span data-stu-id="6226a-120">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="6226a-121">El archivo de formato contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="6226a-121">The format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       100     ","     3     Col3               SQL_Latin1_General_CP1_CI_AS  
2       SQLCHAR       0       100     ","     2     Col2               SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       7       ","     1     Col1               ""  
4       SQLCHAR       0       100     "\r\n"  4     Col4               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="6226a-122">Para obtener más información sobre el diseño de los archivos de formato no XML, vea [Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6226a-122">For more information about the layout of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="6226a-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6226a-123">Example</span></span>  
 <span data-ttu-id="6226a-124">El siguiente ejemplo utiliza una instrucción `BULK INSERT` para realizar una importación masiva de datos del archivo de datos `myTestOrder-c.txt` a la tabla de ejemplo `myTestOrder` utilizando el archivo de formato no XML `myTestOrder.fmt`.</span><span class="sxs-lookup"><span data-stu-id="6226a-124">The following example uses a `BULK INSERT` statement to bulk import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.fmt` non-XML format file.</span></span>  
  
 <span data-ttu-id="6226a-125">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="6226a-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestOrder  
FROM 'C:\myTestOrder-c.txt'   
WITH (formatfile='C:\myTestOrder.fmt');  
GO  
  
```  
  
## <a name="using-an-xml-format-file"></a><span data-ttu-id="6226a-126">Usar un archivo de formato XML</span><span class="sxs-lookup"><span data-stu-id="6226a-126">Using an XML Format File</span></span>  
 <span data-ttu-id="6226a-127">El siguiente archivo de formato no XML de ejemplo muestra un archivo de formato, `myTestOrder.xml`, que asigna los campos de `myTestOrder-c.txt` a las columnas de la tabla `myTestOrder`. Para obtener información sobre la creación del archivo y de la tabla de datos, vea "Tabla y archivo de datos de ejemplo", anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="6226a-127">The following sample non-XML format file presents a format file, `myTestOrder.xml`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="6226a-128">El archivo de formato `myTestOrder.xml` contiene la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="6226a-128">The `myTestOrder.xml` format file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="3" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="1" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="6226a-129">Para obtener más información sobre la sintaxis del esquema XML y ejemplos adicionales de archivos de formato XML, vea [XML, archivos de formato &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6226a-129">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="6226a-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6226a-130">Example</span></span>  
 <span data-ttu-id="6226a-131">El siguiente ejemplo utiliza el proveedor de conjuntos de filas BULK `OPENROWSET` para importar datos del archivo de datos `myTestOrder-c.txt` a la tabla de ejemplo `myTestOrder` utilizando el archivo de formato XML `myTestOrder.xml` .</span><span class="sxs-lookup"><span data-stu-id="6226a-131">The following example uses the `OPENROWSET` bulk rowset provider to import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.xml` XML format file.</span></span> <span data-ttu-id="6226a-132">La instrucción `INSERT... SELECT` especifica la lista de columnas en la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="6226a-132">The `INSERT... SELECT` statement specifies the column list in the select list.</span></span>  
  
 <span data-ttu-id="6226a-133">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="6226a-133">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestOrder   
  SELECT Col1, Col2, Col3, Col4  
      FROM  OPENROWSET(BULK  'C:\myTestOrder-c.txt',  
      FORMATFILE='C:\myTestOrder.Xml'    
       ) AS t1;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="6226a-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6226a-134">See Also</span></span>  
 <span data-ttu-id="6226a-135">[Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6226a-135">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="6226a-136">Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6226a-136">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
  
