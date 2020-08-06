---
title: Especificar el tipo de almacenamiento en archivo mediante bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], file storage types
- importing data, file storage types
- native data format [SQL Server]
- file storage types [SQL Server]
- data formats [SQL Server], file storage types
ms.assetid: 85e12df8-1be7-4bdc-aea9-05aade085c06
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c1f3ad2a94ffe3e0f1db19a8e66f85497e7143dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663477"
---
# <a name="specify-file-storage-type-by-using-bcp-sql-server"></a><span data-ttu-id="53ef4-102">Especificar el tipo de almacenamiento de archivos mediante bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="53ef4-102">Specify File Storage Type by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="53ef4-103">El *tipo de almacenamiento en archivo* describe cómo se almacenan los datos en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="53ef4-103">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="53ef4-104">La información se puede exportar a un archivo de datos como el tipo de tabla de base de datos correspondiente (formato nativo), como su representación en caracteres (formato de caracteres) o como cualquier tipo de datos que admita la conversión implícita (por ejemplo, si copia datos `smallint` como datos `int`).</span><span class="sxs-lookup"><span data-stu-id="53ef4-104">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="53ef4-105">Los tipos de datos definidos por el usuario se exportan como sus tipos base correspondientes.</span><span class="sxs-lookup"><span data-stu-id="53ef4-105">User-defined data types are exported as their base types.</span></span>  
  
## <a name="the-bcp-prompt-for-file-storage-type"></a><span data-ttu-id="53ef4-106">Comando bcp para el tipo de almacenamiento en archivo</span><span class="sxs-lookup"><span data-stu-id="53ef4-106">The bcp Prompt for File Storage Type</span></span>  
 <span data-ttu-id="53ef4-107">Si un comando **bcp** interactivo contiene la opción **in** u **out** sin el modificador de archivo de formato ( **-f**) o un modificador de formato de datos ( **-n**, **-c**, **-w**o **-N**), el comando solicita el tipo de almacenamiento de archivos de cada campo de datos, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="53ef4-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the file storage type of each data field, as follows:</span></span>  
  
 `Enter the file storage type of field <field_name> [<default>]:`  
  
 <span data-ttu-id="53ef4-108">Su respuesta a este mensaje depende de la tarea que realice:</span><span class="sxs-lookup"><span data-stu-id="53ef4-108">Your response to this prompt depends on the task you perform, as follows:</span></span>  
  
-   <span data-ttu-id="53ef4-109">Para exportar datos de forma masiva desde una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un archivo de datos con el almacenamiento más compacto posible (formato de datos nativo), acepte los tipos de almacenamiento de archivos predeterminados que proporciona **bcp**.</span><span class="sxs-lookup"><span data-stu-id="53ef4-109">To bulk export data from an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in the most compact storage possible (native data format), accept the default file storage types that are provided by **bcp**.</span></span> <span data-ttu-id="53ef4-110">Para obtener una lista de los tipos de almacenamiento en archivo nativos, vea "Tipos de almacenamiento en archivo nativos", más adelante en este mismo tema.</span><span class="sxs-lookup"><span data-stu-id="53ef4-110">For a list of the native file storage types, see "Native File Storage Types," later in this topic.</span></span>  
  
-   <span data-ttu-id="53ef4-111">Para exportar datos de forma masiva desde una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un archivo de datos en formato de caracteres, especifique `char` como el tipo de almacenamiento en archivo para todas las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="53ef4-111">To bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file in character format, specify `char` as the file storage type for all columns in the table.</span></span>  
  
-   <span data-ttu-id="53ef4-112">Para importar datos de forma masiva a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] desde un archivo de datos, especifique el tipo de almacenamiento en archivo como `char` para los tipos almacenados en formato de caracteres y, para los datos almacenados en formato de tipo de datos nativo, especifique uno de los siguientes tipos de almacenamiento en archivo, según corresponda:</span><span class="sxs-lookup"><span data-stu-id="53ef4-112">To bulk import data to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a data file, specify the file storage type as `char` for types stored in character format and, for data stored in native data type format, specify one of the file storage types, as appropriate:</span></span>  
  
    |<span data-ttu-id="53ef4-113">tipo de almacenamiento en archivo</span><span class="sxs-lookup"><span data-stu-id="53ef4-113">File storage type</span></span>|<span data-ttu-id="53ef4-114">Escriba en el símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="53ef4-114">Enter at command prompt</span></span>|  
    |-----------------------|-----------------------------|  
    |<span data-ttu-id="53ef4-115">`char`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="53ef4-115">`char` <sup>1</sup></span></span>|<span data-ttu-id="53ef4-116">`c`[`har`]</span><span class="sxs-lookup"><span data-stu-id="53ef4-116">`c`[`har`]</span></span>|  
    |`varchar`|`c[har]`|  
    |`nchar`|`w`|  
    |`nvarchar`|`w`|  
    |<span data-ttu-id="53ef4-117">`text`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53ef4-117">`text` <sup>2</sup></span></span>|<span data-ttu-id="53ef4-118">`T`[`ext`]</span><span class="sxs-lookup"><span data-stu-id="53ef4-118">`T`[`ext`]</span></span>|  
    |`ntext2`|`W`|  
    |`binary`|`x`|  
    |`varbinary`|`x`|  
    |<span data-ttu-id="53ef4-119">`image`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53ef4-119">`image` <sup>2</sup></span></span>|<span data-ttu-id="53ef4-120">`I`[`mage`]</span><span class="sxs-lookup"><span data-stu-id="53ef4-120">`I`[`mage`]</span></span>|  
    |`datetime`|<span data-ttu-id="53ef4-121">**d[ate]**</span><span class="sxs-lookup"><span data-stu-id="53ef4-121">**d[ate]**</span></span>|  
    |`smalldatetime`|`D`|  
    |`time`|`te`|  
    |`date`|`de`|  
    |`datetime2`|`d2`|  
    |`datetimeoffset`|`do`|  
    |`decimal`|`n`|  
    |`numeric`|`n`|  
    |`float`|<span data-ttu-id="53ef4-122">**f[loat]**</span><span class="sxs-lookup"><span data-stu-id="53ef4-122">**f[loat]**</span></span>|  
    |`real`|`r`|  
    |`Int`|<span data-ttu-id="53ef4-123">**i[nt]**</span><span class="sxs-lookup"><span data-stu-id="53ef4-123">**i[nt]**</span></span>|  
    |`bigint`|`B[igint]`|  
    |`smallint`|<span data-ttu-id="53ef4-124">**s[mallint]**</span><span class="sxs-lookup"><span data-stu-id="53ef4-124">**s[mallint]**</span></span>|  
    |`tinyint`|<span data-ttu-id="53ef4-125">**t[inyint]**</span><span class="sxs-lookup"><span data-stu-id="53ef4-125">**t[inyint]**</span></span>|  
    |`money`|<span data-ttu-id="53ef4-126">**m[oney]**</span><span class="sxs-lookup"><span data-stu-id="53ef4-126">**m[oney]**</span></span>|  
    |`smallmoney`|`M`|  
    |`bit`|`b[it]`|  
    |`uniqueidentifier`|`u`|  
    |`sql_variant`|`V[ariant]`|  
    |`timestamp`|`x`|  
    |<span data-ttu-id="53ef4-127">`UDT`(un tipo de datos definido por el usuario)</span><span class="sxs-lookup"><span data-stu-id="53ef4-127">`UDT` (a user-defined data type)</span></span>|`U`|  
    |`XML`|`X`|  
  
     <span data-ttu-id="53ef4-128"><sup>1</sup> la interacción de longitud de campo, longitud de prefijo y terminadores determina la cantidad de espacio de almacenamiento que se asigna en un archivo de datos para datos que no son de caracteres que se exporta como `char` tipo de almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="53ef4-128"><sup>1</sup> The interaction of field length, prefix length, and terminators determines the amount of storage space that is allocated in a data file for noncharacter data that is exported as the `char` file storage type.</span></span>  
  
     <span data-ttu-id="53ef4-129"><sup>2</sup> los `ntext` `text` tipos de datos, y se `image` quitarán en una versión futura de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="53ef4-129"><sup>2</sup> The `ntext`, `text`, and `image` data types will be removed in a future version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="53ef4-130">En proyectos de desarrollo nuevos evite el uso de estos tipos de datos y planee la modificación de las aplicaciones que los utilicen actualmente.</span><span class="sxs-lookup"><span data-stu-id="53ef4-130">In new development work, avoid using these data types, and plan to modify applications that currently use them.</span></span> <span data-ttu-id="53ef4-131">`nvarchar(max)` `varchar(max)` En su lugar, use, y `varbinary(max)` .</span><span class="sxs-lookup"><span data-stu-id="53ef4-131">Use `nvarchar(max)`, `varchar(max)`, and `varbinary(max)` instead.</span></span>  
  
## <a name="native-file-storage-types"></a><span data-ttu-id="53ef4-132">Tipos de almacenamiento en archivo nativos</span><span class="sxs-lookup"><span data-stu-id="53ef4-132">Native File Storage Types</span></span>  
 <span data-ttu-id="53ef4-133">Cada tipo de almacenamiento en archivo nativo se registra en el archivo de formato como el tipo de datos de archivo host correspondiente.</span><span class="sxs-lookup"><span data-stu-id="53ef4-133">Each native file storage type is recorded in the format file as a corresponding host file data type.</span></span>  
  
|<span data-ttu-id="53ef4-134">tipo de almacenamiento en archivo</span><span class="sxs-lookup"><span data-stu-id="53ef4-134">File storage type</span></span>|<span data-ttu-id="53ef4-135">Tipo de datos del archivo host</span><span class="sxs-lookup"><span data-stu-id="53ef4-135">Host file data type</span></span>|  
|-----------------------|-------------------------|  
|<span data-ttu-id="53ef4-136">`char`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="53ef4-136">`char` <sup>1</sup></span></span>|<span data-ttu-id="53ef4-137">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="53ef4-137">SQLCHAR</span></span>|  
|`varchar`|<span data-ttu-id="53ef4-138">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="53ef4-138">SQLCHAR</span></span>|  
|`nchar`|<span data-ttu-id="53ef4-139">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="53ef4-139">SQLNCHAR</span></span>|  
|`nvarchar`|<span data-ttu-id="53ef4-140">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="53ef4-140">SQLNCHAR</span></span>|  
|<span data-ttu-id="53ef4-141">`text`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53ef4-141">`text` <sup>2</sup></span></span>|<span data-ttu-id="53ef4-142">SQLCHAR</span><span class="sxs-lookup"><span data-stu-id="53ef4-142">SQLCHAR</span></span>|  
|<span data-ttu-id="53ef4-143">`ntext`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53ef4-143">`ntext` <sup>2</sup></span></span>|<span data-ttu-id="53ef4-144">SQLNCHAR</span><span class="sxs-lookup"><span data-stu-id="53ef4-144">SQLNCHAR</span></span>|  
|`binary`|<span data-ttu-id="53ef4-145">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="53ef4-145">SQLBINARY</span></span>|  
|`varbinary`|<span data-ttu-id="53ef4-146">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="53ef4-146">SQLBINARY</span></span>|  
|<span data-ttu-id="53ef4-147">`image`<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="53ef4-147">`image` <sup>2</sup></span></span>|<span data-ttu-id="53ef4-148">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="53ef4-148">SQLBINARY</span></span>|  
|`datetime`|<span data-ttu-id="53ef4-149">SQLDATETIME</span><span class="sxs-lookup"><span data-stu-id="53ef4-149">SQLDATETIME</span></span>|  
|`smalldatetime`|<span data-ttu-id="53ef4-150">SQLDATETIM4</span><span class="sxs-lookup"><span data-stu-id="53ef4-150">SQLDATETIM4</span></span>|  
|`decimal`|<span data-ttu-id="53ef4-151">SQLDECIMAL</span><span class="sxs-lookup"><span data-stu-id="53ef4-151">SQLDECIMAL</span></span>|  
|`numeric`|<span data-ttu-id="53ef4-152">SQLNUMERIC</span><span class="sxs-lookup"><span data-stu-id="53ef4-152">SQLNUMERIC</span></span>|  
|`float`|<span data-ttu-id="53ef4-153">SQLFLT8</span><span class="sxs-lookup"><span data-stu-id="53ef4-153">SQLFLT8</span></span>|  
|`real`|<span data-ttu-id="53ef4-154">SQLFLT4</span><span class="sxs-lookup"><span data-stu-id="53ef4-154">SQLFLT4</span></span>|  
|`int`|<span data-ttu-id="53ef4-155">SQLINT</span><span class="sxs-lookup"><span data-stu-id="53ef4-155">SQLINT</span></span>|  
|`bigint`|<span data-ttu-id="53ef4-156">SQLBIGINT</span><span class="sxs-lookup"><span data-stu-id="53ef4-156">SQLBIGINT</span></span>|  
|`smallint`|<span data-ttu-id="53ef4-157">SQLSMALLINT</span><span class="sxs-lookup"><span data-stu-id="53ef4-157">SQLSMALLINT</span></span>|  
|`tinyint`|<span data-ttu-id="53ef4-158">SQLTINYINT</span><span class="sxs-lookup"><span data-stu-id="53ef4-158">SQLTINYINT</span></span>|  
|`money`|<span data-ttu-id="53ef4-159">SQLMONEY</span><span class="sxs-lookup"><span data-stu-id="53ef4-159">SQLMONEY</span></span>|  
|`smallmoney`|<span data-ttu-id="53ef4-160">SQLMONEY4</span><span class="sxs-lookup"><span data-stu-id="53ef4-160">SQLMONEY4</span></span>|  
|`bit`|<span data-ttu-id="53ef4-161">SQLBIT</span><span class="sxs-lookup"><span data-stu-id="53ef4-161">SQLBIT</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="53ef4-162">SQLUNIQUEID</span><span class="sxs-lookup"><span data-stu-id="53ef4-162">SQLUNIQUEID</span></span>|  
|`sql_variant`|<span data-ttu-id="53ef4-163">SQLVARIANT</span><span class="sxs-lookup"><span data-stu-id="53ef4-163">SQLVARIANT</span></span>|  
|`timestamp`|<span data-ttu-id="53ef4-164">SQLBINARY</span><span class="sxs-lookup"><span data-stu-id="53ef4-164">SQLBINARY</span></span>|  
|<span data-ttu-id="53ef4-165">UDT (un tipo de datos definido por el usuario)</span><span class="sxs-lookup"><span data-stu-id="53ef4-165">UDT (a user-defined data type)</span></span>|<span data-ttu-id="53ef4-166">SQLUDT</span><span class="sxs-lookup"><span data-stu-id="53ef4-166">SQLUDT</span></span>|  
  
 <span data-ttu-id="53ef4-167"><sup>1</sup> los archivos de datos que se almacenan en formato de caracteres utilizan `char` como tipo de almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="53ef4-167"><sup>1</sup> Data files that are stored in character format use `char` as the file storage type.</span></span> <span data-ttu-id="53ef4-168">Por consiguiente, para archivos de datos de caracteres, SQLCHAR es el único tipo de datos que aparece en un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="53ef4-168">Therefore, for character data files, SQLCHAR is the only data type that appears in a format file.</span></span>  
  
 <span data-ttu-id="53ef4-169"><sup>2</sup> no se pueden importar datos de `text` forma masiva en `ntext` columnas, y `image` que tengan valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="53ef4-169"><sup>2</sup> You cannot bulk import data into `text`, `ntext`, and `image` columns that have DEFAULT values.</span></span>  
  
## <a name="additional-considerations-for-file-storage-types"></a><span data-ttu-id="53ef4-170">Consideraciones adicionales para los tipos de almacenamiento de archivos</span><span class="sxs-lookup"><span data-stu-id="53ef4-170">Additional Considerations for File Storage Types</span></span>  
 <span data-ttu-id="53ef4-171">Cuando exporta datos de forma masiva desde una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a un archivo de datos:</span><span class="sxs-lookup"><span data-stu-id="53ef4-171">When you bulk export data from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to a data file:</span></span>  
  
-   <span data-ttu-id="53ef4-172">Siempre puede especificar `char` como tipo de almacenamiento en archivo.</span><span class="sxs-lookup"><span data-stu-id="53ef4-172">You can always specify `char` as the file storage type.</span></span>  
  
-   <span data-ttu-id="53ef4-173">Si especifica un tipo de almacenamiento en archivo que representa una conversión implícita no válida, se produce un error en **BCP** ; por ejemplo, aunque puede especificar `int` para los `smallint` datos, si especifica `smallint` para los `int` datos, se producirán errores de desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="53ef4-173">If you enter a file storage type that represents an invalid implicit conversion, **bcp** fails; for example, though you can specify `int` for `smallint` data, if you specify `smallint` for `int` data, overflow errors result.</span></span>  
  
-   <span data-ttu-id="53ef4-174">Si se almacenan tipos de datos que no son de caracteres (por ejemplo, `float`, `money`, `datetime` o `int` como los tipos de bases de datos correspondientes, los datos se escribirán con el formato nativo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="53ef4-174">When noncharacter data types such as `float`, `money`, `datetime`, or `int` are stored as their database types, the data is written to the data file in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native format.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="53ef4-175">Después de que se especifiquen de forma interactiva todos los campos de un comando **bcp**, el comando solicita que guarde sus respuestas para cada campo en un archivo que no tenga el formato XML.</span><span class="sxs-lookup"><span data-stu-id="53ef4-175">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="53ef4-176">Para obtener más información sobre los archivos con formato distinto de XML, vea [Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="53ef4-176">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53ef4-177">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53ef4-177">See Also</span></span>  
 <span data-ttu-id="53ef4-178">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="53ef4-178">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="53ef4-179">[Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="53ef4-179">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="53ef4-180">[Especificar la longitud de campo mediante bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="53ef4-180">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="53ef4-181">[Especificar terminadores de campo y de fila &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="53ef4-181">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 [<span data-ttu-id="53ef4-182">Especificar la longitud de prefijo en los archivos de datos mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="53ef4-182">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
  
