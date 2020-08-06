---
title: Mantenimiento de valores NULL o uso de valores predeterminados durante la importación en bloque (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], null values
- bulk importing [SQL Server], default values
- data formats [SQL Server], null values
- bulk rowset providers [SQL Server]
- bcp utility [SQL Server], null values
- BULK INSERT statement
- default values
- OPENROWSET function, bulk importing
- data formats [SQL Server], default values
ms.assetid: 6b91d762-337b-4345-a159-88abb3e64a81
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 856aa12f6ad5e5094324e0df65941bc63d611451
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749950"
---
# <a name="keep-nulls-or-use-default-values-during-bulk-import-sql-server"></a><span data-ttu-id="a519d-102">Mantener valores NULL o usar valores predeterminados durante la importación masiva (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="a519d-102">Keep Nulls or Use Default Values During Bulk Import (SQL Server)</span></span>
  <span data-ttu-id="a519d-103">De manera predeterminada, cuando se importan datos en una tabla, el comando **BCP** y la instrucción BULK INSERT aplican los valores predeterminados definidos para las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a519d-103">By default, when data is imported into a table, the **bcp** command and BULK INSERT statement observe any defaults that are defined for the columns in the table.</span></span> <span data-ttu-id="a519d-104">Por ejemplo, si un archivo de datos contiene un campo NULL, en su lugar, se cargará el valor predeterminado para la columna.</span><span class="sxs-lookup"><span data-stu-id="a519d-104">For example, if there is a null field in a data file, the default value for the column is loaded instead.</span></span> <span data-ttu-id="a519d-105">El comando **BCP** y la instrucción BULK INSERT permiten especificar que se mantengan los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a519d-105">The **bcp** command and BULK INSERT statement both allow you to specify that nulls values be retained.</span></span>  
  
 <span data-ttu-id="a519d-106">Por el contrario, una instrucción INSERT normal mantiene el valor NULL en lugar de insertar un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a519d-106">In contrast, a regular INSERT statement retains the null value instead of inserting a default value.</span></span> <span data-ttu-id="a519d-107">La instrucción INSERT ... La instrucción SELECT \* FROM OPENROWSET(BULK...) proporciona el mismo comportamiento básico que la instrucción INSERT regular, pero además admite una sugerencia de tabla para insertar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a519d-107">The INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement provides the same basic behavior as regular INSERT but additionally supports a table hint for inserting the default values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a519d-108">En los archivos de formato de ejemplo que omiten una columna de tabla, vea [Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a519d-108">For sample format files that skip a table column, see [Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="a519d-109">Tabla y archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a519d-109">Sample Table and Data File</span></span>  
 <span data-ttu-id="a519d-110">Para ejecutar los ejemplos de este tema, es necesario crear una tabla y un archivo de datos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a519d-110">To run the examples in this topic, you need to create a sample table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="a519d-111">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a519d-111">Sample Table</span></span>  
 <span data-ttu-id="a519d-112">Los ejemplos requieren la creación de una tabla denominada **MyTestDefaultCol2** en la base de datos de ejemplo **AdventureWorks** , bajo el esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="a519d-112">The examples require that a table named **MyTestDefaultCol2** be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="a519d-113">Para crear esta tabla, en el [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Editor de consultas, ejecute:</span><span class="sxs-lookup"><span data-stu-id="a519d-113">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE MyTestDefaultCol2   
(Col1 smallint,  
Col2 nvarchar(50) DEFAULT 'Default value of Col2',  
Col3 nvarchar(50)   
);  
GO  
  
```  
  
 <span data-ttu-id="a519d-114">Tenga en cuenta que la segunda columna de la tabla, `Col2`, tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a519d-114">Notice that the second table column, `Col2`, has a default value.</span></span>  
  
### <a name="sample-format-file"></a><span data-ttu-id="a519d-115">Archivo de formato de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a519d-115">Sample Format File</span></span>  
 <span data-ttu-id="a519d-116">Algunos de los ejemplos de importación masiva utilizan un archivo de formato no XML, `MyTestDefaultCol2-f-c.Fmt`, que corresponde exactamente a la tabla `MyTestDefaultCol2`.</span><span class="sxs-lookup"><span data-stu-id="a519d-116">Some of the bulk-import examples use a non-XML format file, `MyTestDefaultCol2-f-c.Fmt` that corresponds exactly to the `MyTestDefaultCol2` table.</span></span> <span data-ttu-id="a519d-117">Para crear este archivo de formato, en el símbolo del sistema de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, especifique:</span><span class="sxs-lookup"><span data-stu-id="a519d-117">To create this format file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 format nul -c -f C:\MyTestDefaultCol2-f-c.Fmt -t, -r\n -T  
  
```  
  
 <span data-ttu-id="a519d-118">Para obtener más información sobre cómo crear archivos de formato, vea [Crear un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="a519d-118">For more information about creating format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="a519d-119">Archivo de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a519d-119">Sample Data File</span></span>  
 <span data-ttu-id="a519d-120">El ejemplo utiliza un archivo de datos de ejemplo, `MyTestEmptyField2-c.Dat`, que no contiene valores en el segundo campo.</span><span class="sxs-lookup"><span data-stu-id="a519d-120">The example uses a sample data file, `MyTestEmptyField2-c.Dat`, that contains no values in the second field.</span></span> <span data-ttu-id="a519d-121">El archivo de datos `MyTestEmptyField2-c.Dat` contiene los siguientes registros.</span><span class="sxs-lookup"><span data-stu-id="a519d-121">The `MyTestEmptyField2-c.Dat` data file contains the following records.</span></span>  
  
```  
1,,DataField3  
2,,DataField3  
  
```  
  
## <a name="keeping-null-values-with-bcp-or-bulk-insert"></a><span data-ttu-id="a519d-122">Mantener valores NULL con bcp o BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="a519d-122">Keeping Null Values with bcp or BULK INSERT</span></span>  
 <span data-ttu-id="a519d-123">Los siguientes calificadores especifican que un campo vacío del archivo de datos mantiene su valor NULL durante la operación de importación masiva, en lugar de heredar un valor predeterminado (si existe) para las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="a519d-123">The following qualifiers specify that an empty field in the data file retains its null value during the bulk-import operation, rather than inheriting a default value (if any) for the table columns.</span></span>  
  
|<span data-ttu-id="a519d-124">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a519d-124">Command</span></span>|<span data-ttu-id="a519d-125">Qualifier</span><span class="sxs-lookup"><span data-stu-id="a519d-125">Qualifier</span></span>|<span data-ttu-id="a519d-126">Tipo de calificador</span><span class="sxs-lookup"><span data-stu-id="a519d-126">Qualifier type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="a519d-127">**bcp**</span><span class="sxs-lookup"><span data-stu-id="a519d-127">**bcp**</span></span>|`-k`|<span data-ttu-id="a519d-128">Switch</span><span class="sxs-lookup"><span data-stu-id="a519d-128">Switch</span></span>|  
|<span data-ttu-id="a519d-129">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="a519d-129">BULK INSERT</span></span>|<span data-ttu-id="a519d-130">KEEPNULLS<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a519d-130">KEEPNULLS<sup>1</sup></span></span>|<span data-ttu-id="a519d-131">Argumento</span><span class="sxs-lookup"><span data-stu-id="a519d-131">Argument</span></span>|  
  
 <span data-ttu-id="a519d-132"><sup>1</sup> para Bulk Insert, si los valores predeterminados no están disponibles, se debe definir la columna de la tabla para permitir valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a519d-132"><sup>1</sup> For BULK INSERT, if default values are not available, the table column must be defined to allow null values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a519d-133">Estos calificadores deshabilitan la comprobación de definiciones DEFAULT en una tabla mediante los comandos de importación masiva.</span><span class="sxs-lookup"><span data-stu-id="a519d-133">These qualifiers disable checking of DEFAULT definitions on a table by these bulk-import commands.</span></span> <span data-ttu-id="a519d-134">Sin embargo, para cualquier instrucción INSERT simultánea, se esperan definiciones DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="a519d-134">However, for any concurrent INSERT statements, DEFAULT definitions are expected.</span></span>  
  
 <span data-ttu-id="a519d-135">Para obtener más información, vea [bcp (utilidad)](../../tools/bcp-utility.md) y [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a519d-135">For more information, see [bcp Utility](../../tools/bcp-utility.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a519d-136">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a519d-136">Examples</span></span>  
 <span data-ttu-id="a519d-137">Los ejemplos de esta sección realizan importaciones masivas mediante **bcp** o BULK INSERT y mantienen los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a519d-137">The examples in this section bulk import using **bcp** or BULK INSERT and keep null values.</span></span>  
  
 <span data-ttu-id="a519d-138">La segunda columna de la tabla, **Col2**, tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a519d-138">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="a519d-139">El campo correspondiente del archivo de datos contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a519d-139">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="a519d-140">De forma predeterminada, cuando se usa **bcp** o BULK INSERT para importar datos de este archivo de datos en la tabla **MyTestDefaultCol2** , se inserta el valor predeterminado de **Col2** , obteniéndose el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a519d-140">By default, when **bcp** or BULK INSERT is used to import data from this data file into the **MyTestDefaultCol2** table, the default value of **Col2** is inserted, producing the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`Default value of Col2`|`DataField3`|  
|`2`|`Default value of Col2`|`DataField3`|  
  
 <span data-ttu-id="a519d-141">Para insertar " `NULL` " en lugar de " `Default value of Col2` ", debe usar la `-k` opción switch o KEEPNULL, tal y como se muestra en los siguientes ejemplos de **BCP** y Bulk Insert.</span><span class="sxs-lookup"><span data-stu-id="a519d-141">To insert "`NULL`" instead of "`Default value of Col2`", you need to use the `-k` switch or KEEPNULL option, as demonstrated in the following **bcp** and BULK INSERT examples.</span></span>  
  
#### <a name="using-bcp-and-keeping-null-values"></a><span data-ttu-id="a519d-142">Usar bcp y mantener valores NULL</span><span class="sxs-lookup"><span data-stu-id="a519d-142">Using bcp and Keeping Null Values</span></span>  
 <span data-ttu-id="a519d-143">En el siguiente ejemplo se muestra cómo mantener valores NULL en un comando **bcp** .</span><span class="sxs-lookup"><span data-stu-id="a519d-143">The following example demonstrates how to keep null values in a **bcp** command.</span></span> <span data-ttu-id="a519d-144">El comando **BCP** contiene los siguientes modificadores:</span><span class="sxs-lookup"><span data-stu-id="a519d-144">The **bcp** command contains the following switches:</span></span>  
  
|<span data-ttu-id="a519d-145">Switch</span><span class="sxs-lookup"><span data-stu-id="a519d-145">Switch</span></span>|<span data-ttu-id="a519d-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="a519d-146">Description</span></span>|  
|------------|-----------------|  
|`-f`|<span data-ttu-id="a519d-147">Especifica que el comando utiliza un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="a519d-147">Specifies that the command is using a format file..</span></span>|  
|`-k`|<span data-ttu-id="a519d-148">Especifica que las columnas vacías deben conservar un valor NULL durante la operación, en vez de tener valores predeterminados para las columnas insertadas.</span><span class="sxs-lookup"><span data-stu-id="a519d-148">Specifies that empty columns should retain a null value during the operation, rather than have any default values for the columns inserted.</span></span>|  
|`-T`|<span data-ttu-id="a519d-149">Especifica que la utilidad bcp se conecte a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante una conexión de confianza.</span><span class="sxs-lookup"><span data-stu-id="a519d-149">Specifies that the bcp utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="a519d-150">En el símbolo del sistema de Windows, escriba:</span><span class="sxs-lookup"><span data-stu-id="a519d-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 in C:\MyTestEmptyField2-c.Dat -f C:\MyTestDefaultCol2-f-c.Fmt -k -T  
  
```  
  
#### <a name="using-bulk-insert-and-keeping-null-values"></a><span data-ttu-id="a519d-151">Usar BULK INSERT y mantener valores NULL</span><span class="sxs-lookup"><span data-stu-id="a519d-151">Using BULK INSERT and Keeping Null Values</span></span>  
 <span data-ttu-id="a519d-152">En el siguiente ejemplo se muestra el uso de la opción KEEPNULLS en una instrucción BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="a519d-152">The following example demonstrates how to use the KEEPNULLS option in a BULK INSERT statement.</span></span> <span data-ttu-id="a519d-153">En una herramienta de consulta, como el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="a519d-153">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT MyTestDefaultCol2  
   FROM 'C:\MyTestEmptyField2-c.Dat'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      KEEPNULLS  
   );  
GO  
  
```  
  
## <a name="keeping-default-values-with-insert--select--from-openrowsetbulk"></a><span data-ttu-id="a519d-154">Manteniendo los valores predeterminados con INSERT... SELECT \* FROM OPENROWSET (BULK...)</span><span class="sxs-lookup"><span data-stu-id="a519d-154">Keeping Default Values with INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
 <span data-ttu-id="a519d-155">De forma predeterminada, las columnas que no se especifican en la operación de carga masiva se establecen en NULL mediante INSERT... SELECT \* FROM OPENROWSET (BULK...). Sin embargo, puede especificar que para un campo vacío del archivo de datos, la columna de la tabla correspondiente utilice su valor predeterminado (si existe).</span><span class="sxs-lookup"><span data-stu-id="a519d-155">By default, any columns that are not specified in the bulk-load operation are set to NULL by INSERT ... SELECT \* FROM OPENROWSET(BULK...). However, you can specify that for an empty field in the data file, the corresponding table column uses its default value (if any).</span></span> <span data-ttu-id="a519d-156">Para usar los valores predeterminados, especifique la siguiente sugerencia de tabla:</span><span class="sxs-lookup"><span data-stu-id="a519d-156">To use default values, specify the following table hint:</span></span>  
  
|<span data-ttu-id="a519d-157">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a519d-157">Command</span></span>|<span data-ttu-id="a519d-158">Qualifier</span><span class="sxs-lookup"><span data-stu-id="a519d-158">Qualifier</span></span>|<span data-ttu-id="a519d-159">Tipo de calificador</span><span class="sxs-lookup"><span data-stu-id="a519d-159">Qualifier Type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="a519d-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="a519d-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="a519d-161">WITH(KEEPDEFAULTS)</span><span class="sxs-lookup"><span data-stu-id="a519d-161">WITH(KEEPDEFAULTS)</span></span>|<span data-ttu-id="a519d-162">Sugerencia de tabla</span><span class="sxs-lookup"><span data-stu-id="a519d-162">Table hint</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="a519d-163">para obtener más información, vea [INSERT &#40;Transact-sql&#41;](/sql/t-sql/statements/insert-transact-sql), [Select &#40;transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)y [sugerencias de tabla &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span><span class="sxs-lookup"><span data-stu-id="a519d-163">for more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span></span>  
  
### <a name="examples"></a><span data-ttu-id="a519d-164">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a519d-164">Examples</span></span>  
 <span data-ttu-id="a519d-165">La siguiente instrucción INSERT... El ejemplo SELECT \* FROM OPENROWSET (BULK...) realiza importaciones masivas de datos y mantiene los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a519d-165">The following INSERT ... SELECT \* FROM OPENROWSET(BULK...) example bulk imports data and keeps the default values.</span></span>  
  
 <span data-ttu-id="a519d-166">Para ejecutar los ejemplos es necesario crear la tabla de ejemplo **MyTestDefaultCol2** y el archivo de datos `MyTestEmptyField2-c.Dat` y usar un archivo de formato, `MyTestDefaultCol2-f-c.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="a519d-166">To run the examples, you need to create the **MyTestDefaultCol2** sample table, the `MyTestEmptyField2-c.Dat` data file, and use a format file, `MyTestDefaultCol2-f-c.Fmt`.</span></span> <span data-ttu-id="a519d-167">Para obtener más información acerca de la creación de estos ejemplos, vea "Tabla y archivo de datos de ejemplo", más arriba en este tema.</span><span class="sxs-lookup"><span data-stu-id="a519d-167">For information on creating these samples, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="a519d-168">La segunda columna de la tabla, **Col2**, tiene un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a519d-168">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="a519d-169">El campo correspondiente del archivo de datos contiene una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="a519d-169">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="a519d-170">Cuando INSERT... SELECT \* from OPENROWSET (bulk...) importar los campos de este archivo de datos en la tabla **MyTestDefaultCol2** , de forma predeterminada, NULL se inserta en **Col2** en lugar del valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a519d-170">When INSERT ... SELECT \* FROM OPENROWSET(BULK...) import the fields of this data file into the **MyTestDefaultCol2** table, by default, NULL is inserted into **Col2** instead of the default value.</span></span> <span data-ttu-id="a519d-171">Este comportamiento predeterminado genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a519d-171">This default behavior produces the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`NULL`|`DataField3`|  
|`2`|`NULL`|`DataField3`|  
  
 <span data-ttu-id="a519d-172">Para insertar el valor predeterminado, "`Default value of Col2`", en lugar de "`NULL`", es necesario usar la sugerencia de tabla KEEPDEFAULTS, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a519d-172">To insert the default value, "`Default value of Col2`", instead of "`NULL`", you need to use KEEPDEFAULTS table hint, as demonstrated in the following example.</span></span> <span data-ttu-id="a519d-173">En una herramienta de consulta, como el Editor de consultas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="a519d-173">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
INSERT INTO MyTestDefaultCol2  
    WITH (KEEPDEFAULTS)  
    SELECT *  
      FROM OPENROWSET(BULK  'C:\MyTestEmptyField2-c.Dat',  
      FORMATFILE='C:\MyTestDefaultCol2-f-c.Fmt'       
      ) as t1 ;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a519d-174">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="a519d-174">Related Tasks</span></span>  
  
-   [<span data-ttu-id="a519d-175">Mantener valores de identidad al importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-175">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="a519d-176">Preparar los datos para exportar o importar en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-176">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="a519d-177">**Para usar un archivo de formato**</span><span class="sxs-lookup"><span data-stu-id="a519d-177">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="a519d-178">Crear un archivo de formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-178">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="a519d-179">Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-179">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="a519d-180">Usar un archivo de formato para asignar columnas de tabla a campos de un archivo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-180">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="a519d-181">Usar un archivo de formato para omitir un campo de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-181">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="a519d-182">Usar un archivo de formato para omitir una columna de tabla &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-182">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="a519d-183">**Para usar formatos de datos para la importación o exportación masivas**</span><span class="sxs-lookup"><span data-stu-id="a519d-183">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="a519d-184">Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="a519d-184">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="a519d-185">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-185">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a519d-186">Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-186">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a519d-187">Usar el formato de caracteres Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a519d-188">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="a519d-189">**Para especificar formatos de datos por razones de compatibilidad cuando se usa bcp**</span><span class="sxs-lookup"><span data-stu-id="a519d-189">**To specify data formats for compatibility when using bcp**</span></span>  
  
-   [<span data-ttu-id="a519d-190">Especificar terminadores de campo y de fila &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-190">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="a519d-191">Especificar la longitud de prefijo en los archivos de datos mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-191">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="a519d-192">Especificar el tipo de almacenamiento en archivo mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-192">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="a519d-193">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a519d-193">See Also</span></span>  
 <span data-ttu-id="a519d-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a519d-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="a519d-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a519d-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="a519d-196">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="a519d-196">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="a519d-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a519d-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="a519d-198">Sugerencias de tabla &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a519d-198">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
