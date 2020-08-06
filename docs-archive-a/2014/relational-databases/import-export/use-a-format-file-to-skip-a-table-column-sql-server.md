---
title: Usar un archivo de formato para omitir una columna de tabla (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- skipping columns when importing
- format files [SQL Server], skipping columns
ms.assetid: 30e0e7b9-d131-46c7-90a4-6ccf77e3d4f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 153ef21209ff4261020e26aca3bc52d28dc852a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678183"
---
# <a name="use-a-format-file-to-skip-a-table-column-sql-server"></a><span data-ttu-id="33c6b-102">Usar un archivo de formato para omitir una columna de tabla  (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="33c6b-102">Use a Format File to Skip a Table Column (SQL Server)</span></span>
  <span data-ttu-id="33c6b-103">En este tema se describen los archivos de formato.</span><span class="sxs-lookup"><span data-stu-id="33c6b-103">This topic describes format files.</span></span> <span data-ttu-id="33c6b-104">Se puede utilizar un archivo de formato para omitir la importación de una columna de tabla cuando el campo no existe en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="33c6b-104">You can use a format file to skip importing a table column when the field does not exist in the data file.</span></span> <span data-ttu-id="33c6b-105">Un archivo de datos solo puede contener menos campos que el número de columnas en la tabla si las columnas omitidas tienen un valor nulo y/o contienen un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="33c6b-105">A data file can contain fewer fields than the number of columns in the table only if the skipped columns are nullable and/or have default value.</span></span>

## <a name="sample-table-and-data-file"></a><span data-ttu-id="33c6b-106">Tabla y archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="33c6b-106">Sample Table and Data File</span></span>
 <span data-ttu-id="33c6b-107">Los siguientes ejemplos requieren una tabla denominada `myTestSkipCol` en la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] bajo el esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="33c6b-107">The following examples require a table named `myTestSkipCol` in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="33c6b-108">Para crear esta tabla, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="33c6b-108">Create this table as follows:</span></span>

```
USE AdventureWorks2012;
GO
CREATE TABLE myTestSkipCol 
   (
   Col1 smallint,
   Col2 nvarchar(50) NULL,
   Col3 nvarchar(50) not NULL
   );
GO
```

 <span data-ttu-id="33c6b-109">En los siguientes ejemplos se utiliza un archivo de datos de ejemplo, `myTestSkipCol2.dat`, que solo contiene dos campos, aunque la tabla correspondiente contiene tres columnas:</span><span class="sxs-lookup"><span data-stu-id="33c6b-109">The following examples use a sample data file, `myTestSkipCol2.dat`, which contains only two fields, although the corresponding table contains three columns:</span></span>

```
1,DataForColumn3
1,DataForColumn3
1,DataForColumn3

```

 <span data-ttu-id="33c6b-110">Para realizar importaciones masivas de datos desde `myTestSkipCol2.dat` en la tabla `myTestSkipCol` , el archivo de formato debe asignar el primer campo de datos a `Col1`, el segundo campo a `Col3`, omitiendo `Col2`.</span><span class="sxs-lookup"><span data-stu-id="33c6b-110">To bulk import data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col1`, the second field to `Col3`, skipping `Col2`.</span></span>

## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="33c6b-111">Usar un archivo de formato no XML</span><span class="sxs-lookup"><span data-stu-id="33c6b-111">Using a Non-XML Format File</span></span>
 <span data-ttu-id="33c6b-112">Puede modificar un archivo de formato no XML para omitir una columna de tabla.</span><span class="sxs-lookup"><span data-stu-id="33c6b-112">You can modify a non-XML format file to skip a table column.</span></span> <span data-ttu-id="33c6b-113">Normalmente, esto implica el uso de la utilidad **bcp** para crear un archivo de formato no XML predeterminado y la modificación del archivo predeterminado en un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="33c6b-113">Typically, this involves using the **bcp** utility to create a default non-XML format file and the modifying the default file in a text editor.</span></span> <span data-ttu-id="33c6b-114">El archivo de formato modificado debe asignar cada uno de los campos existentes a su columna de tabla correspondiente e indicar las columnas que se deben omitir.</span><span class="sxs-lookup"><span data-stu-id="33c6b-114">The modified format file must map each existing fields to its corresponding table column and indicate which table column or columns to skip.</span></span> <span data-ttu-id="33c6b-115">Para modificar un archivo de datos de formato no XML predeterminado existen dos alternativas.</span><span class="sxs-lookup"><span data-stu-id="33c6b-115">Two alternatives exist for modifying a default non-XML data file.</span></span> <span data-ttu-id="33c6b-116">Cada alternativa indica que el campo de datos no existe en el archivo de datos y que no se insertará ningún dato en la columna correspondiente de la tabla.</span><span class="sxs-lookup"><span data-stu-id="33c6b-116">Either alternative indicates that the data field does not exist in the data file and that no data will be inserted into the corresponding table column.</span></span>

### <a name="creating-a-default-non-xml-format-file"></a><span data-ttu-id="33c6b-117">Crear un archivo de formato no XML predeterminado</span><span class="sxs-lookup"><span data-stu-id="33c6b-117">Creating a Default Non-XML Format File</span></span>
 <span data-ttu-id="33c6b-118">En este tema se usa el archivo de formato no XML predeterminado que se creó para la tabla de ejemplo `myTestSkipCol` mediante el siguiente comando **bcp** :</span><span class="sxs-lookup"><span data-stu-id="33c6b-118">This topic uses the default non-XML format file that was created for the `myTestSkipCol` sample table by using the following **bcp** command:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.fmt -c -T
```

 <span data-ttu-id="33c6b-119">En el ejemplo anterior se crea un archivo de formato no XML, `myTestSkipCol_Default.fmt`.</span><span class="sxs-lookup"><span data-stu-id="33c6b-119">The previous command creates a non-XML format file, `myTestSkipCol_Default.fmt`.</span></span> <span data-ttu-id="33c6b-120">Este formato de archivo se denomina *archivo de formato predeterminado* porque es el formulario generado por **bcp**.</span><span class="sxs-lookup"><span data-stu-id="33c6b-120">This format file is called a *default format file* because it is the form generated by **bcp**.</span></span> <span data-ttu-id="33c6b-121">Normalmente, un archivo de formato predeterminado describe una correspondencia uno a uno entre los campos de archivo de datos y las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="33c6b-121">Typically, a default format file describes a one-to-one correspondence between data-file fields and table columns.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="33c6b-122">Es posible que deba especificar el nombre de la instancia de servidor a la que se va a conectar.</span><span class="sxs-lookup"><span data-stu-id="33c6b-122">You might have to specify the name of the server instance to which you are connecting.</span></span> <span data-ttu-id="33c6b-123">También es posible que deba especificar el nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="33c6b-123">Also, you might have to specify the user name and password.</span></span> <span data-ttu-id="33c6b-124">Para obtener más información, consulte [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="33c6b-124">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>

 <span data-ttu-id="33c6b-125">En la siguiente ilustración se muestran los valores de estos archivos de formato predeterminados de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="33c6b-125">The following illustration shows the values in this sample default format files.</span></span> <span data-ttu-id="33c6b-126">La ilustración también muestra el nombre de cada campo de archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="33c6b-126">The illustration also shows the name of each format-file field.</span></span>

 <span data-ttu-id="33c6b-127">![archivo predeterminado de formato no XML para myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "archivo predeterminado de formato no XML para myTestSkipCol")</span><span class="sxs-lookup"><span data-stu-id="33c6b-127">![default non-XML format file for myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "default non-XML format file for myTestSkipCol")</span></span>

> [!NOTE]
>  <span data-ttu-id="33c6b-128">Para obtener más información sobre los campos de archivo de formato, vea [Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33c6b-128">For more information about the format-file fields, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="methods-for-modifying-a-non-xml-format-file"></a><span data-ttu-id="33c6b-129">Métodos para modificar un archivo de formato no XML</span><span class="sxs-lookup"><span data-stu-id="33c6b-129">Methods for Modifying a Non-XML Format File</span></span>
 <span data-ttu-id="33c6b-130">Para omitir una columna de tabla, edite el archivo de formato no XML predeterminado y modifíquelo utilizando uno de los siguientes métodos alternativos:</span><span class="sxs-lookup"><span data-stu-id="33c6b-130">To skip a table column, edit the default non-XML format file and modify the file by using one of the following alternative methods:</span></span>

-   <span data-ttu-id="33c6b-131">El método preferido consta de tres pasos básicos.</span><span class="sxs-lookup"><span data-stu-id="33c6b-131">The preferred method involves three basic steps.</span></span> <span data-ttu-id="33c6b-132">Primero, elimine cualquier fila de archivo de formato que describa un campo que no esté en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="33c6b-132">First, delete any format-file row that describes a field that is missing from the data file.</span></span> <span data-ttu-id="33c6b-133">A continuación, reduzca el valor "Orden de campo del archivo host" de cada fila de archivo de formato antecedida por una fila eliminada.</span><span class="sxs-lookup"><span data-stu-id="33c6b-133">Then, reduce the "Host file field order" value of each format-file row that follows a deleted row.</span></span> <span data-ttu-id="33c6b-134">El objetivo es tener valores "Orden de campo del archivo host" secuenciales, de 1 a *n*, que reflejen la posición real de cada campo de datos del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="33c6b-134">The goal is sequential "Host file field order" values, 1 through *n*, that reflect the actual position of each data field in the data file.</span></span> <span data-ttu-id="33c6b-135">Por último, reduzca el valor del campo "Número de columnas" para que se ajuste al número real de campos del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="33c6b-135">Finally, reduce the value in the "Number of columns" field to reflect the actual number of fields in the data file.</span></span>

     <span data-ttu-id="33c6b-136">El ejemplo siguiente se basa en el archivo de formato predeterminado para la tabla `myTestSkipCol` , que se creó en "Crear un archivo de formato no XML predeterminado", anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="33c6b-136">The following example is based on the default format file for the `myTestSkipCol` table, which is created in "Creating a Default Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="33c6b-137">Este archivo de formato modificado asigna el primer campo de datos a `Col1`, omite `Col2`y asigna el segundo campo de datos a `Col3`.</span><span class="sxs-lookup"><span data-stu-id="33c6b-137">This modified format file maps the first data field to `Col1`, skips `Col2`, and maps the second data field to `Col3`.</span></span> <span data-ttu-id="33c6b-138">La fila para `Col2` se ha eliminado.</span><span class="sxs-lookup"><span data-stu-id="33c6b-138">The row for `Col2` has been deleted.</span></span> <span data-ttu-id="33c6b-139">Otras modificaciones se indican en negrita: </span><span class="sxs-lookup"><span data-stu-id="33c6b-139">Other modifications are indicated in bold:</span></span>

    ```
    9.0
    2
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

-   <span data-ttu-id="33c6b-140">Como alternativa, para omitir una columna de tabla, puede modificar la definición de la fila de archivo de formato que corresponda a la columna de tabla.</span><span class="sxs-lookup"><span data-stu-id="33c6b-140">Alternatively, to skip a table column, you can modify the definition of the format-file row that corresponds to the table column.</span></span> <span data-ttu-id="33c6b-141">En esta fila de formato de archivo los valores "prefix length", "host file data length" y "server column order" deben estar configurados en 0.</span><span class="sxs-lookup"><span data-stu-id="33c6b-141">In this format-file row, the "prefix length," "host file data length," and "server column order" values must be set to 0.</span></span> <span data-ttu-id="33c6b-142">Además, los campos "terminator" y "column collation" deben estar establecidos en "" (NULL).</span><span class="sxs-lookup"><span data-stu-id="33c6b-142">Also, the "terminator" and "column collation" fields must be set to "" (NULL).</span></span>

     <span data-ttu-id="33c6b-143">El valor "nombre de columna de servidor" requiere una cadena que no esté en blanco, aunque el nombre de columna real no es necesario.</span><span class="sxs-lookup"><span data-stu-id="33c6b-143">The "server column name" value requires a nonblank string, though the actual column name is not necessary.</span></span> <span data-ttu-id="33c6b-144">Los campos de formato restantes requieren los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="33c6b-144">The remaining format fields require their default values.</span></span>

     <span data-ttu-id="33c6b-145">El siguiente ejemplo también se deriva del archivo de formato predeterminado para la tabla `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="33c6b-145">The following example is also derived from the default format file for the `myTestSkipCol` table.</span></span> <span data-ttu-id="33c6b-146">Los valores que deben ser 0 o NULL se indican en negrita.</span><span class="sxs-lookup"><span data-stu-id="33c6b-146">Values that must be 0 or NULL are indicated in bold.</span></span>

    ```
    9.0
    3
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       00""0     Col2         ""
    3       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

### <a name="examples"></a><span data-ttu-id="33c6b-147">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="33c6b-147">Examples</span></span>
 <span data-ttu-id="33c6b-148">Los siguientes ejemplos también se basan en la tabla de ejemplo `myTestSkipCol` y el archivo de datos de ejemplo `myTestSkipCol2.dat` que se crearon en "Tabla y archivo de datos de ejemplo" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="33c6b-148">The following examples are also based on the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span>

#### <a name="using-bulk-insert"></a><span data-ttu-id="33c6b-149">Usar BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="33c6b-149">Using BULK INSERT</span></span>
 <span data-ttu-id="33c6b-150">Este ejemplo funciona con cualquiera de los archivos de formato no XML modificados que se crearon en "Métodos para modificar un archivo de formato no XML" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="33c6b-150">This example works by using either of the modified non-XML format files created in "Methods for Modifying a Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="33c6b-151">En este ejemplo, el archivo de formato modificado se llama `C:\myTestSkipCol2.fmt`.</span><span class="sxs-lookup"><span data-stu-id="33c6b-151">In this example, the modified format file is named `C:\myTestSkipCol2.fmt`.</span></span> <span data-ttu-id="33c6b-152">Para usar `BULK INSERT` a fin de importar de forma masiva el archivo de datos `myTestSkipCol2.dat` , en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="33c6b-152">To use `BULK INSERT` to bulk import the `myTestSkipCol2.dat` data file, in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
BULK INSERT myTestSkipCol 
   FROM 'C:\myTestSkipCol2.dat' 
   WITH (FORMATFILE = 'C:\myTestSkipCol2.fmt');
GO
SELECT * FROM myTestSkipCol;
GO
```

## <a name="using-an-xml-format-file"></a><span data-ttu-id="33c6b-153">Usar un archivo de formato XML</span><span class="sxs-lookup"><span data-stu-id="33c6b-153">Using an XML Format File</span></span>
 <span data-ttu-id="33c6b-154">Con un archivo de formato XML, no se puede omitir una columna cuando se importa directamente a una tabla mediante el comando **bcp** o una instrucción BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="33c6b-154">With an XML format file, you cannot skip a column when you are importing directly into a table by using a **bcp** command or a BULK INSERT statement.</span></span> <span data-ttu-id="33c6b-155">Sin embargo, se puede importar en todas las columnas de una tabla, excepto en la última columna.</span><span class="sxs-lookup"><span data-stu-id="33c6b-155">However, you can import into all but the last column of a table.</span></span> <span data-ttu-id="33c6b-156">Si se tienen que omitir todas las columnas excepto la última, se debe crear una vista de la tabla de destino que contenga únicamente las columnas incluidas en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="33c6b-156">If you have to skip any but the last column, you must create a view of the target table that contains only the columns contained in the data file.</span></span> <span data-ttu-id="33c6b-157">De esta forma, se puede realizar una importación masiva de los datos de ese archivo en la vista.</span><span class="sxs-lookup"><span data-stu-id="33c6b-157">Then, you can bulk import data from that file into the view.</span></span>

 <span data-ttu-id="33c6b-158">Para utilizar un archivo de formato XML para omitir una columna de la tabla mediante OPENROWSET(BULK...), debe proporcionar una lista explícita de las columnas en la lista de selección y en la tabla de destino de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="33c6b-158">To use an XML format file to skip a table column by using OPENROWSET(BULK...), you have to provide explicit list of columns in the select list and also in the target table, as follows:</span></span>

 <span data-ttu-id="33c6b-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="33c6b-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span></span>

### <a name="creating-a-default-xml-format-file"></a><span data-ttu-id="33c6b-160">Crear un archivo de formato XML predeterminado</span><span class="sxs-lookup"><span data-stu-id="33c6b-160">Creating a Default XML Format File</span></span>
 <span data-ttu-id="33c6b-161">Los ejemplos de archivos de formato modificado se basan en la tabla `myTestSkipCol` y el archivo de datos de ejemplo que se crearon en "Tabla y archivo de datos de ejemplo" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="33c6b-161">The examples of modified format files are based on the `myTestSkipCol` sample table and data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="33c6b-162">El siguiente comando **bcp** crea un archivo de formato XML predeterminado para la tabla `myTestSkipCol` :</span><span class="sxs-lookup"><span data-stu-id="33c6b-162">The following **bcp** command creates a default XML format file for the `myTestSkipCol` table:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.xml -c -x -T
```

 <span data-ttu-id="33c6b-163">El archivo de formato no XML predeterminado resultante describe una correspondencia uno a uno entre los archivos de campos de datos y las columnas de la tabla, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="33c6b-163">The resulting default non-XML format file describes a one-to-one correspondence between data-file fields and table columns, as follows:</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

> [!NOTE]
>  <span data-ttu-id="33c6b-164">Para obtener más información sobre la estructura de los archivos de formato XML, vea [XML, archivos de formato &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33c6b-164">For information about the structure of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="examples"></a><span data-ttu-id="33c6b-165">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="33c6b-165">Examples</span></span>
 <span data-ttu-id="33c6b-166">Los ejemplos de esta sección utilizan la tabla de ejemplo `myTestSkipCol` y el archivo de datos de ejemplo `myTestSkipCol2.dat` que se crearon en "Tabla de ejemplo y archivo de datos" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="33c6b-166">The examples in this section use the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="33c6b-167">Para importar datos desde `myTestSkipCol2.dat` a la tabla `myTestSkipCol` , los ejemplos utilizan el siguiente archivo de formato XML modificado, `myTestSkipCol2-x.xml`.</span><span class="sxs-lookup"><span data-stu-id="33c6b-167">To import the data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the examples use the following modified XML format file, `myTestSkipCol2-x.xml`.</span></span> <span data-ttu-id="33c6b-168">Esto se basa en el archivo de formato que se creó en "Crear un archivo de formato XML predeterminado", anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="33c6b-168">This is based on the format file that is created in "Creating a Default XML Format File," earlier in this topic.</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

#### <a name="using-openrowsetbulk"></a><span data-ttu-id="33c6b-169">Usar OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="33c6b-169">Using OPENROWSET(BULK...)</span></span>
 <span data-ttu-id="33c6b-170">En el siguiente ejemplo se utiliza el proveedor de conjuntos de filas BULK `OPENROWSET` y el archivo de formato `myTestSkipCol2.xml` .</span><span class="sxs-lookup"><span data-stu-id="33c6b-170">The following example uses the `OPENROWSET` bulk rowset provider and the `myTestSkipCol2.xml` format file.</span></span> <span data-ttu-id="33c6b-171">En el ejemplo se importa masivamente el archivo de datos `myTestSkipCol2.dat` a la tabla `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="33c6b-171">The example bulk imports the `myTestSkipCol2.dat` data file into the `myTestSkipCol` table.</span></span> <span data-ttu-id="33c6b-172">La instrucción contiene una lista explícita de las columnas en la lista de selección y también en la tabla de destino, según convenga.</span><span class="sxs-lookup"><span data-stu-id="33c6b-172">The statement contains an explicit list of columns in the select list and also in the target table, as required.</span></span>

 <span data-ttu-id="33c6b-173">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="33c6b-173">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
INSERT INTO myTestSkipCol
  (Col1,Col3)
    SELECT Col1,Col3
      FROM  OPENROWSET(BULK  'C:\myTestSkipCol2.Dat',
      FORMATFILE='C:\myTestSkipCol2.Xml'  
       ) as t1 ;
GO
```

#### <a name="using-bulk-import-on-a-view"></a><span data-ttu-id="33c6b-174">Utilizar BULK IMPORT en una vista</span><span class="sxs-lookup"><span data-stu-id="33c6b-174">Using BULK IMPORT on a View</span></span>
 <span data-ttu-id="33c6b-175">En el siguiente ejemplo se crea `v_myTestSkipCol` en la tabla `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="33c6b-175">The following example creates the `v_myTestSkipCol` on the `myTestSkipCol` table.</span></span> <span data-ttu-id="33c6b-176">Esta vista omite la segunda columna de la tabla, `Col2`.</span><span class="sxs-lookup"><span data-stu-id="33c6b-176">This view skips the second table column, `Col2`.</span></span> <span data-ttu-id="33c6b-177">Después, en el ejemplo se usa `BULK INSERT` para importar el archivo de datos `myTestSkipCol2.dat` a la vista.</span><span class="sxs-lookup"><span data-stu-id="33c6b-177">The example then uses `BULK INSERT` to import the `myTestSkipCol2.dat` data file into this view.</span></span>

 <span data-ttu-id="33c6b-178">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="33c6b-178">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
CREATE VIEW v_myTestSkipCol AS
    SELECT Col1,Col3
    FROM myTestSkipCol;
GO

USE AdventureWorks2012;
GO
BULK INSERT v_myTestSkipCol
FROM 'C:\myTestSkipCol2.dat'
WITH (FORMATFILE='C:\myTestSkipCol2.xml');
GO
```

## <a name="see-also"></a><span data-ttu-id="33c6b-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="33c6b-179">See Also</span></span>
 <span data-ttu-id="33c6b-180">[utilidad bcp](../../tools/bcp-utility.md) [Bulk Insert &#40;transact-sql&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [usar un archivo de formato para omitir un campo de datos](use-a-format-file-to-skip-a-data-field-sql-server.md) &#40;SQL Server&#41;[usar un archivo de formato para asignar columnas de tabla a campos de archivo de datos &#40;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) SQL Server&#41;[usar un archivo de formato para importar datos de forma masiva &#40;](use-a-format-file-to-bulk-import-data-sql-server.md) SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="33c6b-180">[bcp Utility](../../tools/bcp-utility.md) [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md) [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md)</span></span>


