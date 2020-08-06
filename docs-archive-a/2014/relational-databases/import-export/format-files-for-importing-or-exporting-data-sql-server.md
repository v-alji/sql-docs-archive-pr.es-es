---
title: Archivos de formato para importar o exportar datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], format files
- bulk importing [SQL Server], format files
- format files [SQL Server]
ms.assetid: b7b97d68-4336-4091-aee4-1941fab568e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1143690f0322fef2612fde51eebcb7427ee237ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675379"
---
# <a name="format-files-for-importing-or-exporting-data-sql-server"></a><span data-ttu-id="63e2c-102">Archivos de formato para importar o exportar datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="63e2c-102">Format Files for Importing or Exporting Data (SQL Server)</span></span>
  <span data-ttu-id="63e2c-103">Al importar masivamente datos en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o exportar masivamente datos de una tabla, puede usar un *archivo de formato* para almacenar toda la información de formato necesaria para exportar o importar datos masivamente.</span><span class="sxs-lookup"><span data-stu-id="63e2c-103">When you bulk import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or bulk export data from a table, you can use a *format file* to store all the format information that is required to bulk export or bulk import data.</span></span> <span data-ttu-id="63e2c-104">Esto incluye la información de formato para cada campo de un archivo de datos relativo a la tabla.</span><span class="sxs-lookup"><span data-stu-id="63e2c-104">This includes format information for each field in a data file relative to that table.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="63e2c-105">admite dos tipos de archivos de formato: formatos XML y archivos de formato no XML.</span><span class="sxs-lookup"><span data-stu-id="63e2c-105">supports two types of format files: XML formats and non-XML format files.</span></span> <span data-ttu-id="63e2c-106">Tanto los archivos con formato XML como los archivos no XML contienen descripciones de todos los campos de un archivo de datos, y los archivos de formato XML también contienen descripciones de las columnas de tabla correspondientes.</span><span class="sxs-lookup"><span data-stu-id="63e2c-106">Both non-XML format files and XML format files contain descriptions of every field in a data file, and XML format files also contain descriptions of the corresponding table columns.</span></span> <span data-ttu-id="63e2c-107">Por lo general, los archivos de formato XML y no XML son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="63e2c-107">Generally, XML and non-XML format files are interchangeable.</span></span> <span data-ttu-id="63e2c-108">Sin embargo, es recomendable utilizar la sintaxis XML para los nuevos archivos de formato porque proporciona varias ventajas con relación a los archivos de formato no XML.</span><span class="sxs-lookup"><span data-stu-id="63e2c-108">However, we recommend that you use the XML syntax for new format files because they provide several advantages over non-XML format files.</span></span> <span data-ttu-id="63e2c-109">Para obtener más información, vea [XML, archivos de formato &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="63e2c-109">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 
  
##  <a name="benefits-of-format-files"></a><a name="Benefits"></a> <span data-ttu-id="63e2c-110">Ventajas de los archivos de formato</span><span class="sxs-lookup"><span data-stu-id="63e2c-110">Benefits of Format Files</span></span>  
  
-   <span data-ttu-id="63e2c-111">El archivo de formato proporciona una manera flexible de escribir archivos de datos que requiere poca o ninguna modificación para adaptarlos a otros formatos de datos y para leer archivos de datos de otros programas.</span><span class="sxs-lookup"><span data-stu-id="63e2c-111">Provides a flexible system for writing data files that requires little or no editing to comply with other data formats or to read data files from other software.</span></span>  
  
-   <span data-ttu-id="63e2c-112">Permite realizar la importación masiva de datos sin tener que agregar o eliminar datos innecesarios o reordenar los datos existentes en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="63e2c-112">Enables you to bulk import data without having to add or delete unnecessary data or to reorder existing data in the data file.</span></span> <span data-ttu-id="63e2c-113">Los archivos de formato resultan especialmente útiles cuando existe una discrepancia entre los campos del archivo de datos y las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="63e2c-113">Format files are particularly useful when a mismatch exists between fields in the data file and columns in the table.</span></span>  
  
##  <a name="examples-of-format-files"></a><a name="ExamplesOfFFs"></a> <span data-ttu-id="63e2c-114">Ejemplos de archivos de formato</span><span class="sxs-lookup"><span data-stu-id="63e2c-114">Examples of Format Files</span></span>  
 <span data-ttu-id="63e2c-115">Los siguientes ejemplos muestran el diseño de un archivo de formato no XML y de un archivo de formato XML.</span><span class="sxs-lookup"><span data-stu-id="63e2c-115">The following examples show the layout of a non-XML format file and of an XML format file.</span></span> <span data-ttu-id="63e2c-116">Estos archivos de formato corresponden a la tabla `HumanResources.myTeam` de la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63e2c-116">These format files correspond to the `HumanResources.myTeam` table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="63e2c-117">Esta tabla tiene cuatro columnas: `EmployeeID`, `Name`, `Title`y `ModifiedDate`.</span><span class="sxs-lookup"><span data-stu-id="63e2c-117">This table contains four columns: `EmployeeID`, `Name`, `Title`, and `ModifiedDate`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63e2c-118">Para obtener más información sobre la tabla y cómo crearla, vea [Tabla de ejemplo HumanResources.myTeam &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="63e2c-118">For information about this table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
### <a name="a-using-a-non-xml-format-file"></a><span data-ttu-id="63e2c-119">A.</span><span class="sxs-lookup"><span data-stu-id="63e2c-119">A.</span></span> <span data-ttu-id="63e2c-120">Uso de un archivo de formato no XML</span><span class="sxs-lookup"><span data-stu-id="63e2c-120">Using a non-XML format file</span></span>  
 <span data-ttu-id="63e2c-121">El siguiente archivo de formato no XML usa el formato de datos nativo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la tabla `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="63e2c-121">The following non-XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="63e2c-122">Este formato se creó usando el siguiente comando `bcp` .</span><span class="sxs-lookup"><span data-stu-id="63e2c-122">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Fmt -n -T   
The contents of this format file are as follows: 9.0  
4  
1       SQLSMALLINT   0       2       ""   1     EmployeeID               ""  
2       SQLNCHAR      2       100     ""   2     Name                     SQL_Latin1_General_CP1_CI_AS  
3       SQLNCHAR      2       100     ""   3     Title                    SQL_Latin1_General_CP1_CI_AS  
4       SQLNCHAR      2       100     ""   4     Background               SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="63e2c-123">Para obtener más información, vea [Archivos de formato no XML &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="63e2c-123">For more information, see [Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span></span>  
  
 
  
### <a name="b-using-an-xml-format-file"></a><span data-ttu-id="63e2c-124">B.</span><span class="sxs-lookup"><span data-stu-id="63e2c-124">B.</span></span> <span data-ttu-id="63e2c-125">Uso de un archivo de formato XML</span><span class="sxs-lookup"><span data-stu-id="63e2c-125">Using an XML format file</span></span>  
 <span data-ttu-id="63e2c-126">El siguiente archivo de formato XML usa el formato de datos nativo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la tabla `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="63e2c-126">The following XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="63e2c-127">Este formato se creó usando el siguiente comando `bcp` .</span><span class="sxs-lookup"><span data-stu-id="63e2c-127">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Xml -x -n -T   
```  
  
 <span data-ttu-id="63e2c-128">El archivo de formato contiene:</span><span class="sxs-lookup"><span data-stu-id="63e2c-128">The format file contains:</span></span>  
  
```  
 <?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="EmployeeID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Name" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Title" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Background" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="63e2c-129">Para obtener más información, vea [XML, archivos de formato &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="63e2c-129">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="when-is-a-format-file-required"></a><a name="WhenFFrequired"></a> <span data-ttu-id="63e2c-130">¿Cuándo se necesita un archivo de formato?</span><span class="sxs-lookup"><span data-stu-id="63e2c-130">When Is a Format File Required?</span></span>  
 <span data-ttu-id="63e2c-131">Una instrucción INSERT ... SELECT \* FROM OPENROWSET(BULK...) necesita siempre un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="63e2c-131">An INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement always requires a format file.</span></span>  
  
-   <span data-ttu-id="63e2c-132">Para **bcp** o BULK INSERT, en situaciones simples, el uso de un archivo de formato es opcional y pocas veces necesario.</span><span class="sxs-lookup"><span data-stu-id="63e2c-132">For **bcp** or BULK INSERT, in simple situations, using a format file is optional and rarely necessary.</span></span> <span data-ttu-id="63e2c-133">Sin embargo, en situaciones de importación masiva complejas, el archivo de formato suele ser necesario.</span><span class="sxs-lookup"><span data-stu-id="63e2c-133">However, for complex bulk-import situations, a format file is frequently required.</span></span>  
  
 <span data-ttu-id="63e2c-134">Los archivos de formato se necesitan cuando:</span><span class="sxs-lookup"><span data-stu-id="63e2c-134">Format files are required if:</span></span>  
  
-   <span data-ttu-id="63e2c-135">Se utiliza el mismo archivo de datos como origen de varias tablas que tienen esquemas distintos.</span><span class="sxs-lookup"><span data-stu-id="63e2c-135">The same data file is used as a source for multiple tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="63e2c-136">El archivo de datos tiene un número de campos distinto al de columnas de la tabla de destino; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="63e2c-136">The data file has a different number of fields that the target table has columns; for example:</span></span>  
  
    -   <span data-ttu-id="63e2c-137">La tabla de destino contiene como mínimo una columna para la que se ha definido un valor predeterminado o se admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="63e2c-137">The target table contains at least one column for which either a default value is defined or NULL is allowed.</span></span>  
  
    -   <span data-ttu-id="63e2c-138">Los usuarios no tienen permisos SELECT/INSERT en una o más columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="63e2c-138">The users do not have SELECT/INSERT permissions on one or more columns in the table.</span></span>  
  
    -   <span data-ttu-id="63e2c-139">Se utiliza un único archivo de datos con dos o más tablas que tienen esquemas distintos.</span><span class="sxs-lookup"><span data-stu-id="63e2c-139">A single data file is used with two or more tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="63e2c-140">El orden de columnas del archivo de datos y de la tabla es distinto.</span><span class="sxs-lookup"><span data-stu-id="63e2c-140">The column order is different for the data file and table.</span></span>  
  
-   <span data-ttu-id="63e2c-141">Los caracteres de terminación o las longitudes de prefijo no coinciden entre las columnas del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="63e2c-141">The terminating characters or prefix lengths differ among the columns of the data file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63e2c-142">En caso de no disponer de ningún archivo de formato, si un comando **bcp** especifica un modificador de formato de datos ( **-n**, **-c**, **-w**o **-N**) o una operación BULK INSERT especifica la opción DATAFILETYPE, se usará el formato de datos especificado como método predeterminado para interpretar los campos del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="63e2c-142">In the absence of a format file, if a **bcp** command specifies a data-format switch (**-n**, **-c**, **-w**, or **-N**) or a BULK INSERT operation specifies the DATAFILETYPE option, the specified data format is used as the default method of interpreting the fields of the data file.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="63e2c-143">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="63e2c-143">Related Tasks</span></span>  
  
-   [<span data-ttu-id="63e2c-144">Crear un archivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63e2c-144">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="63e2c-145">Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63e2c-145">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="63e2c-146">Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63e2c-146">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="63e2c-147">Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63e2c-147">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="63e2c-148">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63e2c-148">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="63e2c-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63e2c-149">See Also</span></span>  
 <span data-ttu-id="63e2c-150">[Archivos de formato no XML &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="63e2c-150">[Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span></span>  
 <span data-ttu-id="63e2c-151">[XML, archivos de formato &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="63e2c-151">[XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="63e2c-152">Formatos de datos para importación en bloque o exportación masiva &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="63e2c-152">Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;</span></span>](data-formats-for-bulk-import-or-bulk-export-sql-server.md)  
  
  
