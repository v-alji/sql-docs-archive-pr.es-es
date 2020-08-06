---
title: Usar el formato de caracteres Unicode para importar o exportar datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], Unicode character
- Unicode [SQL Server], bulk importing and exporting
ms.assetid: 74342a11-c1c0-4746-b482-7f3537744a70
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 520ce1b4eed8dc11d6d3fe038969257aea1e90fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749930"
---
# <a name="use-unicode-character-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="eb026-102">Usar el formato de caracteres Unicode para importar o exportar datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="eb026-102">Use Unicode Character Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="eb026-103">El formato de caracteres Unicode se recomienda para las transferencias masivas de datos entre varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante un archivo de datos que contenga caracteres DBCS o extendidos.</span><span class="sxs-lookup"><span data-stu-id="eb026-103">Unicode character format is recommended for bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended/DBCS characters.</span></span> <span data-ttu-id="eb026-104">El formato de datos de caracteres Unicode permite exportar datos desde un servidor mediante una página de códigos utilizada por el cliente que está realizando la operación.</span><span class="sxs-lookup"><span data-stu-id="eb026-104">The Unicode character data format allows data to be exported from a server by using a code page that differs from the code page used by the client that is performing the operation.</span></span> <span data-ttu-id="eb026-105">En esos casos, el uso del formato de caracteres Unicode tiene las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="eb026-105">In such cases, use of Unicode character format has the following advantages:</span></span>  
  
-   <span data-ttu-id="eb026-106">Si los datos de origen y destino son de tipo Unicode, el uso del formato de caracteres Unicode mantiene todos los datos de los caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb026-106">If the source and destination data are Unicode data types, use of Unicode character format preserves all of the character data.</span></span>  
  
-   <span data-ttu-id="eb026-107">Si los datos de origen y destino no son de tipo Unicode, el uso del formato de caracteres Unicode minimiza la pérdida de caracteres extendidos en los datos de origen que no pueden representarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="eb026-107">if the source and destination data are not Unicode data types, use of Unicode character format minimizes the loss of extended characters in the source data that cannot be represented at the destination.</span></span>  
  
 <span data-ttu-id="eb026-108">Los archivos de datos con formato de caracteres Unicode utilizan las convenciones de los archivos Unicode.</span><span class="sxs-lookup"><span data-stu-id="eb026-108">Unicode character format data files follow the conventions for Unicode files.</span></span> <span data-ttu-id="eb026-109">Los primeros dos bytes del archivo son los números hexadecimales 0xFFFE.</span><span class="sxs-lookup"><span data-stu-id="eb026-109">The first two bytes of the file are hexadecimal numbers, 0xFFFE.</span></span> <span data-ttu-id="eb026-110">Estos bytes funcionan como marcas de orden de bytes, ya que especifican si el byte de orden alto se almacena el primero o el último en el archivo.</span><span class="sxs-lookup"><span data-stu-id="eb026-110">These bytes serve as byte-order marks, specifying whether the high-order byte is stored first or last in the file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eb026-111">Para que un archivo de formato trabaje con un archivo de datos de caracteres Unicode, todos los campos de entrada deben ser cadenas de texto Unicode (es decir, de tamaño fijo o cadenas Unicode terminadas en caracteres).</span><span class="sxs-lookup"><span data-stu-id="eb026-111">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
 <span data-ttu-id="eb026-112">Los datos `sql_variant` almacenados en un archivo de datos con formato de caracteres Unicode funcionan de la misma forma que en un archivo de datos en modo de caracteres, con la excepción de que los datos se almacenan como `nchar` en lugar de `char`.</span><span class="sxs-lookup"><span data-stu-id="eb026-112">The `sql_variant` data that is stored in a Unicode character-format data file operates in the same way it operates in a character-format data file, except that the data is stored as `nchar` instead of `char` data.</span></span> <span data-ttu-id="eb026-113">Para obtener más información sobre el formato de caracteres, consulte [Compatibilidad con la intercalación y Unicode](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="eb026-113">For more information about character format, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="eb026-114">Para usar un terminador de campo o de fila distinto al predeterminado que se proporciona con el formato de caracteres Unicode, vea [Especificar terminadores de campo y de fila &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb026-114">To use a field or row terminator other than the default that is provided with Unicode character format, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
## <a name="command-options-for-unicode-character-format"></a><span data-ttu-id="eb026-115">Opciones de comando para el formato de caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="eb026-115">Command Options for Unicode Character Format</span></span>  
 <span data-ttu-id="eb026-116">Puede importar datos con formato de caracteres Unicode en una tabla mediante **BCP**, Bulk Insert o INSERT... SELECT \* from OPENROWSET (bulk...). Para un comando **BCP** o una instrucción BULK INSERT, puede especificar el formato de datos en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="eb026-116">You can import Unicode character format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="eb026-117">Para una instrucción INSERT ... SELECT \* FROM OPENROWSET(BULK...), debe especificar el formato de datos en un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="eb026-117">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="eb026-118">El formato de caracteres Unicode puede usarse con las siguientes opciones de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="eb026-118">Unicode character format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="eb026-119">Get-Help</span><span class="sxs-lookup"><span data-stu-id="eb026-119">Command</span></span>|<span data-ttu-id="eb026-120">Opción</span><span class="sxs-lookup"><span data-stu-id="eb026-120">Option</span></span>|<span data-ttu-id="eb026-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb026-121">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="eb026-122">**bcp**</span><span class="sxs-lookup"><span data-stu-id="eb026-122">**bcp**</span></span>|<span data-ttu-id="eb026-123">**-w**</span><span class="sxs-lookup"><span data-stu-id="eb026-123">**-w**</span></span>|<span data-ttu-id="eb026-124">Usa el formato de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="eb026-124">Uses the Unicode character format.</span></span>|  
|<span data-ttu-id="eb026-125">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="eb026-125">BULK INSERT</span></span>|<span data-ttu-id="eb026-126">DATAFILETYPE **= '** WideChar **'**</span><span class="sxs-lookup"><span data-stu-id="eb026-126">DATAFILETYPE **='** widechar **'**</span></span>|<span data-ttu-id="eb026-127">Utiliza el formato de caracteres Unicode al importar datos masivamente.</span><span class="sxs-lookup"><span data-stu-id="eb026-127">Uses Unicode character format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="eb026-128">Para obtener más información, vea [bcp (utilidad)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) u [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb026-128">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb026-129">Otra posibilidad es especificar el formato por campo en un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="eb026-129">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="eb026-130">Para obtener más información, vea [Archivos de formato para importar o exportar datos &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb026-130">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="eb026-131">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="eb026-131">Examples</span></span>  
 <span data-ttu-id="eb026-132">En los siguientes ejemplos se muestra el modo de exportar datos de forma masiva con formato de datos de caracteres Unicode mediante **bcp** e importar masivamente los mismos datos mediante BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="eb026-132">The following examples demonstrate how to bulk export Unicode character data using **bcp** and to bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="eb026-133">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb026-133">Sample Table</span></span>  
 <span data-ttu-id="eb026-134">Los ejemplos requieren la creación de una tabla denominada `myTestUniCharData` en la base de datos de ejemplo [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] , bajo el esquema `dbo` .</span><span class="sxs-lookup"><span data-stu-id="eb026-134">The examples require that a table named `myTestUniCharData` table be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="eb026-135">Antes de poder ejecutar los ejemplos, debe crear esta tabla.</span><span class="sxs-lookup"><span data-stu-id="eb026-135">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="eb026-136">Para crear esta tabla, en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , ejecute:</span><span class="sxs-lookup"><span data-stu-id="eb026-136">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestUniCharData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="eb026-137">Para rellenar esta tabla y ver el contenido resultante, ejecute las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="eb026-137">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniCharData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3')   
        ,(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
  
```  
  
### <a name="using-bcp-to-bulk-export-unicode-character-data"></a><span data-ttu-id="eb026-138">Usar bcp para exportar masivamente datos con formato de datos de caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="eb026-138">Using bcp to Bulk Export Unicode Character Data</span></span>  
 <span data-ttu-id="eb026-139">Para exportar datos de la tabla a un archivo de datos, use **bcp** con la opción **out** y los siguientes calificadores:</span><span class="sxs-lookup"><span data-stu-id="eb026-139">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="eb026-140">Calificadores</span><span class="sxs-lookup"><span data-stu-id="eb026-140">Qualifiers</span></span>|<span data-ttu-id="eb026-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb026-141">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="eb026-142">**-w**</span><span class="sxs-lookup"><span data-stu-id="eb026-142">**-w**</span></span>|<span data-ttu-id="eb026-143">Especifica el formato de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="eb026-143">Specifies Unicode character format.</span></span>|  
|<span data-ttu-id="eb026-144">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="eb026-144">**-t** `,`</span></span>|<span data-ttu-id="eb026-145">Especifica una coma (`,`) como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="eb026-145">Specifies a comma (`,`) as the field terminator.</span></span><br /><br /> <span data-ttu-id="eb026-146">Nota: el terminador de campo predeterminado es el carácter Unicode de tabulación (\t).</span><span class="sxs-lookup"><span data-stu-id="eb026-146">Note: The default field terminator is the tab Unicode character (\t).</span></span> <span data-ttu-id="eb026-147">Para obtener más información, vea [Especificar terminadores de campo y de fila &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb026-147">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>|  
|<span data-ttu-id="eb026-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="eb026-148">**-T**</span></span>|<span data-ttu-id="eb026-149">Especifica que la utilidad **bcp** se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una conexión de confianza utilizando la seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="eb026-149">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="eb026-150">Si no se especifica **-T** , es necesario especificar **-U** y **-P** para iniciar sesión correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb026-150">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="eb026-151">En el siguiente ejemplo se exportan masivamente datos en formato de caracteres Unicode desde la tabla `myTestUniCharData` en un nuevo archivo de datos denominado `myTestUniCharData-w.Dat` que usa la coma (`,`) como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="eb026-151">The following example bulk exports data in Unicode character format from the `myTestUniCharData` table into a new data file named `myTestUniCharData-w.Dat` data file that uses the comma (`,`) as the field terminator.</span></span> <span data-ttu-id="eb026-152">En el símbolo del sistema de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, especifique:</span><span class="sxs-lookup"><span data-stu-id="eb026-152">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestUniCharData out C:\myTestUniCharData-w.Dat -w -t, -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-unicode-character-data"></a><span data-ttu-id="eb026-153">Usar BULK INSERT para importar masivamente datos con formato de caracteres Unicode</span><span class="sxs-lookup"><span data-stu-id="eb026-153">Using BULK INSERT to Bulk Import Unicode Character Data</span></span>  
 <span data-ttu-id="eb026-154">En el siguiente ejemplo se utiliza `BULK INSERT` para importar los datos del archivo de datos `myTestUniCharData-w.Dat` a la tabla `myTestUniCharData`.</span><span class="sxs-lookup"><span data-stu-id="eb026-154">The following example uses `BULK INSERT` to import the data in the `myTestUniCharData-w.Dat` data file into the `myTestUniCharData` table.</span></span> <span data-ttu-id="eb026-155">Es necesario declarar en la instrucción el terminador de campo no predeterminado (`,`).</span><span class="sxs-lookup"><span data-stu-id="eb026-155">The nondefault field terminator (`,`) must be declared in the statement.</span></span> <span data-ttu-id="eb026-156">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="eb026-156">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestUniCharData   
   FROM 'C:\myTestUniCharData-w.Dat'   
   WITH (  
      DATAFILETYPE='widechar',  
      FIELDTERMINATOR=','  
   );   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="eb026-157">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="eb026-157">Related Tasks</span></span>  
 <span data-ttu-id="eb026-158">**Para usar formatos de datos para la importación o exportación masivas**</span><span class="sxs-lookup"><span data-stu-id="eb026-158">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="eb026-159">Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb026-159">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="eb026-160">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb026-160">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="eb026-161">Usar el formato nativo para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb026-161">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="eb026-162">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="eb026-162">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb026-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb026-163">See Also</span></span>  
 <span data-ttu-id="eb026-164">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="eb026-164">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="eb026-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb026-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="eb026-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb026-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="eb026-167">[Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb026-167">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="eb026-168">Compatibilidad con la intercalación y Unicode</span><span class="sxs-lookup"><span data-stu-id="eb026-168">Collation and Unicode Support</span></span>](../collations/collation-and-unicode-support.md)  
  
  
