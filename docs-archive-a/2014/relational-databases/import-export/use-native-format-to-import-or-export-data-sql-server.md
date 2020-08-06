---
title: Usar el formato nativo para importar o exportar datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- data formats [SQL Server], native
ms.assetid: eb279b2f-0f1f-428f-9b8f-2a7fc495b79f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab42ba3eb6468aac3da2fa780d371818c8776690
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749934"
---
# <a name="use-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="619d1-102">Usar el formato nativo para importar o exportar datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="619d1-102">Use Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="619d1-103">Se recomienda usar el formato nativo cuando se realice una transferencia masiva de datos entre varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando un archivo de datos que no contiene caracteres extendidos o de doble byte (DBCS).</span><span class="sxs-lookup"><span data-stu-id="619d1-103">Native format is recommended when you bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using a data file that does not contain any extended/double-byte character set (DBCS) characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="619d1-104">Para realizar una transferencia masiva de datos entre varias instancias de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando un archivo de datos que contenga caracteres extendidos o DBCS, debe utilizar el formato nativo Unicode.</span><span class="sxs-lookup"><span data-stu-id="619d1-104">To bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters, you should use the Unicode native format.</span></span> <span data-ttu-id="619d1-105">Para obtener más información, vea [Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="619d1-105">For more information, see [Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="619d1-106">El formato nativo mantiene los tipos de datos nativos de una base de datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-106">Native format maintains the native data types of a database.</span></span> <span data-ttu-id="619d1-107">Está pensado para transferencias de datos de alta velocidad entre tablas de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="619d1-107">Native format is intended for high-speed data transfer of data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="619d1-108">Si utiliza un archivo de formato, las tablas de origen y destino no tienen que ser idénticas.</span><span class="sxs-lookup"><span data-stu-id="619d1-108">If you use a format file, the source and target tables do not need to be identical.</span></span> <span data-ttu-id="619d1-109">La transferencia de datos implica dos pasos:</span><span class="sxs-lookup"><span data-stu-id="619d1-109">The data transfer involves two steps:</span></span>  
  
1.  <span data-ttu-id="619d1-110">Exportación masiva de datos de una tabla de origen a un archivo de datos</span><span class="sxs-lookup"><span data-stu-id="619d1-110">Bulk exporting the data from a source table into a data file</span></span>  
  
2.  <span data-ttu-id="619d1-111">Importación masiva de datos de un archivo de datos a una tabla de destino</span><span class="sxs-lookup"><span data-stu-id="619d1-111">Bulk importing the data from the data file into the target table</span></span>  
  
 <span data-ttu-id="619d1-112">El uso del formato nativo entre tablas idénticas evita la conversión innecesaria de tipos de datos a y desde el formato de caracteres, lo que ahorra tiempo y espacio.</span><span class="sxs-lookup"><span data-stu-id="619d1-112">The use of native format between identical tables avoids unnecessary conversion of data types to and from character format, saving time and space.</span></span> <span data-ttu-id="619d1-113">No obstante, para obtener la velocidad de transferencia óptima, se realizan algunas comprobaciones relativas al formato de los datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-113">To achieve the optimum transfer rate, however, few checks are performed regarding data formatting.</span></span> <span data-ttu-id="619d1-114">Para evitar problemas con los datos cargados, vea la siguiente lista de restricciones.</span><span class="sxs-lookup"><span data-stu-id="619d1-114">To prevent problems with the loaded data, see the following restrictions list.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="619d1-115">Restricciones</span><span class="sxs-lookup"><span data-stu-id="619d1-115">Restrictions</span></span>  
 <span data-ttu-id="619d1-116">Para importar datos con formato nativo correctamente, asegúrese de lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="619d1-116">To import data in native format successfully, ensure that:</span></span>  
  
-   <span data-ttu-id="619d1-117">El archivo de datos tiene formato nativo.</span><span class="sxs-lookup"><span data-stu-id="619d1-117">The data file is in native format.</span></span>  
  
-   <span data-ttu-id="619d1-118">O bien la tabla de destino debe ser compatible con el archivo de datos (tiene el mismo número de columnas, el mismo tipo de datos, la misma longitud, el estado NULL, etc.) o bien debe utilizar un archivo de formato para asignar cada campo a las columnas correspondientes.</span><span class="sxs-lookup"><span data-stu-id="619d1-118">Either the target table must be compatible with the data file (having the correct number of columns, data type, length, NULL status, and so forth), or you must use a format file to map each field to its corresponding columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="619d1-119">Si importa datos de un archivo que no coincide con la tabla de destino, la operación de importación puede ser correcta pero, probablemente, los valores de los datos insertados en la tabla de destino son incorrectos.</span><span class="sxs-lookup"><span data-stu-id="619d1-119">If you import data from a file that is mismatched with the target table, the import operation might succeed but the data values inserted into the target table are likely to be incorrect.</span></span> <span data-ttu-id="619d1-120">Esto se debe a que los datos del archivo se interpretan utilizando el formato de la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="619d1-120">This is because the data from the file is interpreted by using the format of the target table.</span></span> <span data-ttu-id="619d1-121">Por tanto, si hay alguna incoherencia, se insertan valores incorrectos.</span><span class="sxs-lookup"><span data-stu-id="619d1-121">Therefore, any mismatch results in the insertion of incorrect values.</span></span> <span data-ttu-id="619d1-122">No obstante, en ningún caso puede tal incoherencia dar lugar a incoherencias lógicas o físicas en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-122">However, under no circumstances can such a mismatch cause logical or physical inconsistencies in the database.</span></span>  
  
     <span data-ttu-id="619d1-123">Para obtener más información sobre cómo usar archivos de formato, vea [Archivos de formato para importar o exportar datos &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="619d1-123">For information on using format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="619d1-124">Una importación correcta no daña la tabla de destino.</span><span class="sxs-lookup"><span data-stu-id="619d1-124">A successful import will not corrupt the target table.</span></span>  
  
## <a name="how-bcp-handles-data-in-native-format"></a><span data-ttu-id="619d1-125">Cómo trata bcp los datos con formato nativo</span><span class="sxs-lookup"><span data-stu-id="619d1-125">How bcp Handles Data in Native Format</span></span>  
 <span data-ttu-id="619d1-126">Esta sección aborda una serie de consideraciones especiales sobre el modo en que la utilidad **bcp** exporta e importa datos con formato nativo.</span><span class="sxs-lookup"><span data-stu-id="619d1-126">This section discusses special considerations for how the **bcp** utility exports and imports data in native format.</span></span>  
  
-   <span data-ttu-id="619d1-127">Datos que no son caracteres</span><span class="sxs-lookup"><span data-stu-id="619d1-127">Noncharacter data</span></span>  
  
     <span data-ttu-id="619d1-128">La utilidad bcp utiliza el formato de datos binario interno de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para escribir datos que no son caracteres de una tabla en un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-128">The bcp utility uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format to write noncharacter data from a table to a data file.</span></span>  
  
-   <span data-ttu-id="619d1-129">Datos `char` o `varchar`</span><span class="sxs-lookup"><span data-stu-id="619d1-129">`char` or `varchar` data</span></span>  
  
     <span data-ttu-id="619d1-130">Al principio de cada `char` campo o `varchar` , **BCP** agrega la longitud del prefijo.</span><span class="sxs-lookup"><span data-stu-id="619d1-130">At the beginning of each `char` or `varchar` field, **bcp** adds the prefix length.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="619d1-131">Cuando se utiliza el modo nativo, de forma predeterminada, la utilidad **BCP** convierte los caracteres de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en caracteres OEM antes de copiarlos en un archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-131">When native mode is used, by default, the **bcp** utility converts characters from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to OEM characters before it copies them to a data file.</span></span> <span data-ttu-id="619d1-132">La utilidad **BCP** convierte los caracteres de un archivo de datos en caracteres ANSI antes de importarlos de forma masiva en una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla.</span><span class="sxs-lookup"><span data-stu-id="619d1-132">The **bcp** utility converts characters from a data file to ANSI characters before it bulk imports them into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="619d1-133">Durante estas conversiones, se pueden perder datos que tengan caracteres extendidos.</span><span class="sxs-lookup"><span data-stu-id="619d1-133">During these conversions, extended character data can be lost.</span></span> <span data-ttu-id="619d1-134">Para caracteres extendidos, utilice el formato nativo Unicode o especifique una página de códigos.</span><span class="sxs-lookup"><span data-stu-id="619d1-134">For extended characters, either use Unicode native format or specify a code page.</span></span>  
  
-   <span data-ttu-id="619d1-135">Datos `sql_variant`</span><span class="sxs-lookup"><span data-stu-id="619d1-135">`sql_variant` data</span></span>  
  
     <span data-ttu-id="619d1-136">Si se almacenan datos `sql_variant` como SQLVARIANT en un archivo de datos con formato nativo, los datos mantienen todas sus características.</span><span class="sxs-lookup"><span data-stu-id="619d1-136">If `sql_variant` data is stored as a SQLVARIANT in a native-format data file, the data maintains all of its characteristics.</span></span> <span data-ttu-id="619d1-137">Los metadatos que registran el tipo de datos de cada valor de datos se almacenan junto con el valor de los datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-137">The metadata that records the data type of each data value is stored along with the data value.</span></span> <span data-ttu-id="619d1-138">Estos metadatos se utilizan para crear de nuevo el valor de los datos con el mismo tipo de datos en una columna `sql_variant` de destino.</span><span class="sxs-lookup"><span data-stu-id="619d1-138">This metadata is used to re-create the data value with the same data type in a destination `sql_variant` column.</span></span>  
  
     <span data-ttu-id="619d1-139">Si el tipo de datos de la columna de destino no es `sql_variant`, cada valor de dato se convierte al tipo de datos de la columna de destino, con las reglas normales de conversión implícita de datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-139">If the data type of the destination column is not `sql_variant`, each data value is converted to the data type of the destination column, following the normal rules of implicit data conversion.</span></span> <span data-ttu-id="619d1-140">Si se produce un error durante la conversión de los datos, se revierte el lote actual.</span><span class="sxs-lookup"><span data-stu-id="619d1-140">If an error occurs during data conversion, the current batch is rolled back.</span></span> <span data-ttu-id="619d1-141">Los valores `char` y `varchar` que se transfieren entre columnas `sql_variant` pueden tener problemas de conversión de página de códigos.</span><span class="sxs-lookup"><span data-stu-id="619d1-141">Any `char` and `varchar` values that are transferred between `sql_variant` columns may have code page conversion issues.</span></span>  
  
     <span data-ttu-id="619d1-142">Para obtener más información sobre la conversión de datos, vea [Conversiones de tipos de datos &#40;motor de base de datos&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span><span class="sxs-lookup"><span data-stu-id="619d1-142">For more information about data conversion, see [Data Type Conversion &#40;Database Engine&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span></span>  
  
## <a name="command-options-for-native-format"></a><span data-ttu-id="619d1-143">Opciones de comando para el formato nativo</span><span class="sxs-lookup"><span data-stu-id="619d1-143">Command Options for Native Format</span></span>  
 <span data-ttu-id="619d1-144">Puede importar datos con formato nativo a una tabla mediante **BCP**, Bulk Insert o INSERT... SELECT \* from OPENROWSET (bulk...). Para un comando **BCP** o una instrucción BULK INSERT, puede especificar el formato de datos en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="619d1-144">You can import native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="619d1-145">Para una instrucción INSERT ... SELECT \* FROM OPENROWSET(BULK...), debe especificar el formato de datos en un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="619d1-145">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="619d1-146">Las siguientes opciones de la línea de comandos admiten el formato nativo:</span><span class="sxs-lookup"><span data-stu-id="619d1-146">Native format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="619d1-147">Get-Help</span><span class="sxs-lookup"><span data-stu-id="619d1-147">Command</span></span>|<span data-ttu-id="619d1-148">Opción</span><span class="sxs-lookup"><span data-stu-id="619d1-148">Option</span></span>|<span data-ttu-id="619d1-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="619d1-149">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="619d1-150">**bcp**</span><span class="sxs-lookup"><span data-stu-id="619d1-150">**bcp**</span></span>|<span data-ttu-id="619d1-151">**-n**</span><span class="sxs-lookup"><span data-stu-id="619d1-151">**-n**</span></span>|<span data-ttu-id="619d1-152">Hace que la utilidad **BCP** use los tipos de datos nativos de los datos. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="619d1-152">Causes the **bcp** utility to use the native data types of the data.<sup>1</sup></span></span>|  
|<span data-ttu-id="619d1-153">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="619d1-153">BULK INSERT</span></span>|<span data-ttu-id="619d1-154">DATAFILETYPE **= '** Native **'**</span><span class="sxs-lookup"><span data-stu-id="619d1-154">DATAFILETYPE **='** native **'**</span></span>|<span data-ttu-id="619d1-155">Utiliza los tipos de datos nativos o nativos anchos de los datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-155">Uses the native or wide native data types of the data.</span></span> <span data-ttu-id="619d1-156">Tenga en cuenta que DATAFILETYPE no es necesario si el archivo de formato especifica los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="619d1-156">Note that DATAFILETYPE is not needed if a format file specifies the data types.</span></span>|  
  
 <span data-ttu-id="619d1-157"><sup>1</sup> para cargar datos nativos (**-n**) en un formato compatible con versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clientes de, use el modificador **-V** .</span><span class="sxs-lookup"><span data-stu-id="619d1-157"><sup>1</sup> To load native (**-n**) data to a format compatible with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients, use the **-V** switch.</span></span> <span data-ttu-id="619d1-158">Para obtener más información, vea [Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="619d1-158">For more information, see [Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span></span>  
  
 <span data-ttu-id="619d1-159">Para obtener más información, vea [bcp (utilidad)](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) u [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="619d1-159">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="619d1-160">Otra posibilidad es especificar el formato por campo en un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="619d1-160">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="619d1-161">Para obtener más información, vea [Archivos de formato para importar o exportar datos &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="619d1-161">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="619d1-162">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="619d1-162">Examples</span></span>  
 <span data-ttu-id="619d1-163">En los siguientes ejemplos se muestra el modo de exportar masivamente datos nativos con **bcp** e importar masivamente los mismos datos mediante BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="619d1-163">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="619d1-164">Tabla de ejemplo</span><span class="sxs-lookup"><span data-stu-id="619d1-164">Sample Table</span></span>  
 <span data-ttu-id="619d1-165">Los ejemplos requieren que se cree una tabla denominada **myTestNativeData** en la base de datos de ejemplo **AdventureWorks** , bajo el esquema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="619d1-165">The examples require that a table named **myTestNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="619d1-166">Antes de poder ejecutar los ejemplos, debe crear esta tabla.</span><span class="sxs-lookup"><span data-stu-id="619d1-166">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="619d1-167">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="619d1-167">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="619d1-168">Para rellenar esta tabla y ver el contenido resultante, ejecute las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="619d1-168">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="619d1-169">Usar bcp para exportar masivamente datos nativos</span><span class="sxs-lookup"><span data-stu-id="619d1-169">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="619d1-170">Para exportar datos de la tabla a un archivo de datos, use **bcp** con la opción **out** y los siguientes calificadores:</span><span class="sxs-lookup"><span data-stu-id="619d1-170">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="619d1-171">Calificadores</span><span class="sxs-lookup"><span data-stu-id="619d1-171">Qualifiers</span></span>|<span data-ttu-id="619d1-172">Descripción</span><span class="sxs-lookup"><span data-stu-id="619d1-172">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="619d1-173">**-n**</span><span class="sxs-lookup"><span data-stu-id="619d1-173">**-n**</span></span>|<span data-ttu-id="619d1-174">Especifica tipos de datos nativos.</span><span class="sxs-lookup"><span data-stu-id="619d1-174">Specifies native data types.</span></span>|  
|<span data-ttu-id="619d1-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="619d1-175">**-T**</span></span>|<span data-ttu-id="619d1-176">Especifica que la utilidad **bcp** se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una conexión de confianza utilizando la seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="619d1-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="619d1-177">Si no se especifica **-T** , es necesario especificar **-U** y **-P** para iniciar sesión correctamente.</span><span class="sxs-lookup"><span data-stu-id="619d1-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="619d1-178">En el siguiente ejemplo se exportan masivamente datos en formato nativo desde la tabla `myTestNativeData` a un nuevo archivo de datos denominado `myTestNativeData-n.Dat`.</span><span class="sxs-lookup"><span data-stu-id="619d1-178">The following example bulk exports data in native format from the `myTestNativeData` table into a new data file named `myTestNativeData-n.Dat` data file.</span></span> <span data-ttu-id="619d1-179">En el símbolo del sistema de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, especifique:</span><span class="sxs-lookup"><span data-stu-id="619d1-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestNativeData out C:\myTestNativeData-n.Dat -n -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="619d1-180">Usar BULK INSERT para importar masivamente datos nativos</span><span class="sxs-lookup"><span data-stu-id="619d1-180">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="619d1-181">En el siguiente ejemplo se utiliza BULK INSERT para importar los datos del archivo de datos `myTestNativeData-n.Dat` en la tabla `myTestNativeData` .</span><span class="sxs-lookup"><span data-stu-id="619d1-181">The following example uses BULK INSERT to import the data in the `myTestNativeData-n.Dat` data file into the `myTestNativeData` table.</span></span> <span data-ttu-id="619d1-182">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], ejecute:</span><span class="sxs-lookup"><span data-stu-id="619d1-182">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestNativeData   
    FROM 'C:\myTestNativeData-n.Dat'   
   WITH (DATAFILETYPE='native');   
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="619d1-183">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="619d1-183">Related Tasks</span></span>  
 <span data-ttu-id="619d1-184">**Para usar formatos de datos para la importación o exportación masivas**</span><span class="sxs-lookup"><span data-stu-id="619d1-184">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="619d1-185">Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server</span><span class="sxs-lookup"><span data-stu-id="619d1-185">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="619d1-186">Usar el formato de caracteres para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="619d1-186">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="619d1-187">Usar el formato de caracteres Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="619d1-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="619d1-188">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="619d1-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="619d1-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="619d1-189">See Also</span></span>  
 <span data-ttu-id="619d1-190">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="619d1-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="619d1-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="619d1-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="619d1-192">[Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="619d1-192">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="619d1-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="619d1-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span></span>  
 <span data-ttu-id="619d1-194">[Importar datos con formato nativo y de caracteres de versiones anteriores de SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="619d1-194">[Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span></span>  
 <span data-ttu-id="619d1-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="619d1-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="619d1-196">Usar el formato nativo Unicode para importar o exportar datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="619d1-196">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
  
