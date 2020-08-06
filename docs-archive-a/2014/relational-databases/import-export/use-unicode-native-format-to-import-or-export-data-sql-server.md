---
title: Usar el formato nativo Unicode para importar o exportar datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- Unicode [SQL Server], bulk importing and exporting
- data formats [SQL Server], Unicode native
ms.assetid: a6213308-f3d5-406e-9029-19d8bb3367f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: beae2f836de16dedf3be6d8c196910c53be02266
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749921"
---
# <a name="use-unicode-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="aba38-102">Usar el formato nativo Unicode para importar o exportar datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="aba38-102">Use Unicode Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="aba38-103">El formato nativo Unicode es útil cuando se debe copiar información de una instalación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en otra.</span><span class="sxs-lookup"><span data-stu-id="aba38-103">Unicode native format is helpful when information must be copied from one [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation to another.</span></span> <span data-ttu-id="aba38-104">El uso del formato nativo para datos que no son caracteres permite ahorrar tiempo, además de evitar la conversión innecesaria de tipos de datos a y desde el formato de caracteres.</span><span class="sxs-lookup"><span data-stu-id="aba38-104">The use of native format for noncharacter data saves time, eliminating unnecessary conversion of data types to and from character format.</span></span> <span data-ttu-id="aba38-105">El uso del formato de caracteres Unicode para todos los datos de caracteres evita la pérdida de caracteres extendidos durante la transferencia masiva de datos entre servidores que utilizan páginas de códigos diferentes.</span><span class="sxs-lookup"><span data-stu-id="aba38-105">The use of Unicode character format for all character data prevents loss of any extended characters during bulk transfer of data between servers using different code pages.</span></span> <span data-ttu-id="aba38-106">Los archivos de datos en formato nativo Unicode se pueden leer en cualquier método de importación masiva.</span><span class="sxs-lookup"><span data-stu-id="aba38-106">A data file in Unicode native format can be read by any bulk-import method.</span></span>  
  
 <span data-ttu-id="aba38-107">El formato nativo Unicode se recomienda para la transferencia masiva de datos entre varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante un archivo de datos que contenga caracteres extendidos o DBCS.</span><span class="sxs-lookup"><span data-stu-id="aba38-107">Unicode native format is recommended for the bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span> <span data-ttu-id="aba38-108">Para los datos que no son caracteres, el formato nativo Unicode utiliza tipos de datos nativos (de base de datos).</span><span class="sxs-lookup"><span data-stu-id="aba38-108">For noncharacter data, Unicode native format uses native (database) data types.</span></span> <span data-ttu-id="aba38-109">Para los datos de caracteres, como `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)` y `ntext`, el formato nativo Unicode utiliza el formato de datos de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="aba38-109">For character data, such as `char`, `nchar`, `varchar`, `nvarchar`, `text`, `varchar(max)`, `nvarchar(max)`, and `ntext`, the Unicode native format uses Unicode character data format.</span></span>  
  
 <span data-ttu-id="aba38-110">Los datos `sql_variant` que se almacenan como SQLVARIANT en un archivo de datos en formato nativo Unicode funcionan de la misma manera que en un archivo de datos en formato nativo, con la excepción de que los valores `char` y `varchar` se convierten en `nchar` y `nvarchar`, lo que duplica la cantidad de espacio necesario para las columnas afectadas.</span><span class="sxs-lookup"><span data-stu-id="aba38-110">The `sql_variant` data that is stored as a SQLVARIANT in a Unicode native-format data file operates in the same manner as it does in a native-format data file, except that `char` and `varchar` values are converted to `nchar` and `nvarchar`, which doubles the amount of storage required for the affected columns.</span></span> <span data-ttu-id="aba38-111">Los metadatos originales se conservan y los valores se convierten de nuevo al tipo de datos `char` y `varchar` original cuando se importan masivamente en la columna de una tabla.</span><span class="sxs-lookup"><span data-stu-id="aba38-111">The original metadata is preserved, and the values are converted back to their original `char` and `varchar` data type when bulk imported into a table column.</span></span>  
  
## <a name="command-options-for-unicode-native-format"></a><span data-ttu-id="aba38-112">Opciones de comandos para el formato nativo Unicode</span><span class="sxs-lookup"><span data-stu-id="aba38-112">Command Options for Unicode Native Format</span></span>  
 <span data-ttu-id="aba38-113">Puede importar datos con formato nativo Unicode en una tabla mediante **BCP**, Bulk Insert o INSERT... SELECT \* from OPENROWSET (bulk...). Para un comando **BCP** o una instrucción BULK INSERT, puede especificar el formato de datos en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aba38-113">You can import Unicode native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="aba38-114">Para una instrucción INSERT ... SELECT \* FROM OPENROWSET(BULK...), debe especificar el formato de datos en un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="aba38-114">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="aba38-115">El formato nativo Unicode puede usarse con las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aba38-115">Unicode native format is supported by the following options:</span></span>  
  
|<span data-ttu-id="aba38-116">Get-Help</span><span class="sxs-lookup"><span data-stu-id="aba38-116">Command</span></span>|<span data-ttu-id="aba38-117">Opción</span><span class="sxs-lookup"><span data-stu-id="aba38-117">Option</span></span>|<span data-ttu-id="aba38-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="aba38-118">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="aba38-119">**bcp**</span><span class="sxs-lookup"><span data-stu-id="aba38-119">**bcp**</span></span>|<span data-ttu-id="aba38-120">**-N**</span><span class="sxs-lookup"><span data-stu-id="aba38-120">**-N**</span></span>|<span data-ttu-id="aba38-121">Hace que la utilidad **BCP** use el formato nativo Unicode, que utiliza tipos de datos nativos (de base de datos) para todos los datos que no son caracteres y el formato de datos de caracteres Unicode para todos los datos de caracteres ( `char` , `nchar` ,, `varchar` `nvarchar` , `text` y `ntext` ).</span><span class="sxs-lookup"><span data-stu-id="aba38-121">Causes the **bcp** utility to use the Unicode native format, which uses native (database) data types for all noncharacter data and Unicode character data format for all character (`char`, `nchar`, `varchar`, `nvarchar`, `text`, and `ntext`) data.</span></span>|  
|<span data-ttu-id="aba38-122">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="aba38-122">BULK INSERT</span></span>|<span data-ttu-id="aba38-123">DATAFILETYPE **= '** widenative **'**</span><span class="sxs-lookup"><span data-stu-id="aba38-123">DATAFILETYPE **='** widenative **'**</span></span>|<span data-ttu-id="aba38-124">Utilice el formato nativo Unicode al importar datos masivamente.</span><span class="sxs-lookup"><span data-stu-id="aba38-124">Use Unicode native format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="aba38-125">Para obtener más información, vea [bcp (utilidad)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) u [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="aba38-125">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aba38-126">Otra posibilidad es especificar el formato por campo en un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="aba38-126">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="aba38-127">Para obtener más información, vea [Archivos de formato para importar o exportar datos &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="aba38-127">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="aba38-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="aba38-128">Examples</span></span>  
 <span data-ttu-id="aba38-129">En los siguientes ejemplos se muestra el modo de exportar masivamente datos nativos con **bcp** e importar masivamente los mismos datos mediante BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="aba38-129">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="aba38-130">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aba38-130">Sample Table</span></span>  
 <span data-ttu-id="aba38-131">Los ejemplos requieren que se cree una tabla denominada **myTestUniNativeData** en la base de datos de ejemplo **AdventureWorks** , bajo el esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="aba38-131">The examples require that a table named **myTestUniNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="aba38-132">Antes de poder ejecutar los ejemplos, debe crear esta tabla.</span><span class="sxs-lookup"><span data-stu-id="aba38-132">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="aba38-133">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="aba38-133">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestUniNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="aba38-134">Para rellenar esta tabla y ver el contenido resultante, ejecute las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="aba38-134">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestUniNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="aba38-135">Usar bcp para exportar masivamente datos nativos</span><span class="sxs-lookup"><span data-stu-id="aba38-135">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="aba38-136">Para exportar datos de la tabla a un archivo de datos, use **bcp** con la opción **out** y los siguientes calificadores:</span><span class="sxs-lookup"><span data-stu-id="aba38-136">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="aba38-137">Calificadores</span><span class="sxs-lookup"><span data-stu-id="aba38-137">Qualifiers</span></span>|<span data-ttu-id="aba38-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="aba38-138">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="aba38-139">**-N**</span><span class="sxs-lookup"><span data-stu-id="aba38-139">**-N**</span></span>|<span data-ttu-id="aba38-140">Especifica tipos de datos nativos.</span><span class="sxs-lookup"><span data-stu-id="aba38-140">Specifies native data types.</span></span>|  
|<span data-ttu-id="aba38-141">**-T**</span><span class="sxs-lookup"><span data-stu-id="aba38-141">**-T**</span></span>|<span data-ttu-id="aba38-142">Especifica que la utilidad **bcp** se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una conexión de confianza utilizando la seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="aba38-142">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="aba38-143">Si no se especifica **-T** , es necesario especificar **-U** y **-P** para iniciar sesión correctamente.</span><span class="sxs-lookup"><span data-stu-id="aba38-143">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="aba38-144">En el siguiente ejemplo se exportan masivamente datos en formato nativo desde la tabla `myTestUniNativeData` a un nuevo archivo de datos denominado `myTestUniNativeData-N.Dat`.</span><span class="sxs-lookup"><span data-stu-id="aba38-144">The following example bulk exports data in native format from the `myTestUniNativeData` table into a new data file named `myTestUniNativeData-N.Dat` data file.</span></span> <span data-ttu-id="aba38-145">En el símbolo del sistema de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, especifique:</span><span class="sxs-lookup"><span data-stu-id="aba38-145">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestUniNativeData out C:\myTestUniNativeData-N.Dat -N -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="aba38-146">Usar BULK INSERT para importar masivamente datos nativos</span><span class="sxs-lookup"><span data-stu-id="aba38-146">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="aba38-147">En el siguiente ejemplo se utiliza BULK INSERT para importar los datos del archivo de datos `myTestUniNativeData-N.Dat` en la tabla `myTestUniNativeData` .</span><span class="sxs-lookup"><span data-stu-id="aba38-147">The following example uses BULK INSERT to import the data in the `myTestUniNativeData-N.Dat` data file into the `myTestUniNativeData` table.</span></span> <span data-ttu-id="aba38-148">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="aba38-148">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestUniNativeData   
    FROM 'C:\myTestUniNativeData-N.Dat'   
   WITH (DATAFILETYPE='widenative');   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniNativeData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="aba38-149">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="aba38-149">Related Tasks</span></span>  
 <span data-ttu-id="aba38-150">**Para usar formatos de datos para la importación o exportación masivas**</span><span class="sxs-lookup"><span data-stu-id="aba38-150">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="aba38-151">Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="aba38-151">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="aba38-152">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aba38-152">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="aba38-153">Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aba38-153">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="aba38-154">Usar el formato de caracteres Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="aba38-154">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="aba38-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aba38-155">See Also</span></span>  
 <span data-ttu-id="aba38-156">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="aba38-156">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="aba38-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aba38-157">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="aba38-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aba38-158">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="aba38-159">Tipos de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aba38-159">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
