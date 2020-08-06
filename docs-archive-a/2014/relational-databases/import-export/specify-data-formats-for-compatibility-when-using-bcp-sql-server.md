---
title: Especificar formatos de datos por razones de compatibilidad mediante bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], compatibility
- bulk importing [SQL Server], compatibility
- compatibility [SQL Server], data formats
- data formats [SQL Server], compatibility
- bcp utility [SQL Server], compatibility
ms.assetid: cd5fc8c8-eab1-4165-9468-384f31e53f0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d12456760f32ddbd8cc434d474aebb0e0ecf141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748804"
---
# <a name="specify-data-formats-for-compatibility-when-using-bcp-sql-server"></a><span data-ttu-id="4243f-102">Especificar formatos de datos por razones de compatibilidad mediante bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4243f-102">Specify Data Formats for Compatibility when Using bcp (SQL Server)</span></span>
  <span data-ttu-id="4243f-103">En este tema se describen los atributos de formato de datos, los mensajes específicos de los campos y el almacenamiento de datos campo por campo en un archivo de formato no XML del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `bcp` comando.</span><span class="sxs-lookup"><span data-stu-id="4243f-103">This topic describes the data-format attributes, field-specific prompts, and storing field-by-field data in a non-xml format file of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`bcp` command.</span></span> <span data-ttu-id="4243f-104">Comprenderlo puede ser útil cuando se realiza una exportación masiva datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para importarlos masivamente en otro programas, como por ejemplo otro programa de base de datos.</span><span class="sxs-lookup"><span data-stu-id="4243f-104">Understanding these can be helpful when you bulk export [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data for bulk import into another program, such as another database program.</span></span> <span data-ttu-id="4243f-105">Los formatos de datos predeterminados (nativo, carácter o Unicode) de la tabla de origen podrían ser incompatibles con la disposición de los datos esperada por el otro programa. Si existe una incompatibilidad, al exportar los datos, debe describirse su disposición.</span><span class="sxs-lookup"><span data-stu-id="4243f-105">The default data formats (native, character, or Unicode) in the source table might be incompatible with the data layout expected by the other program If an incompatibility exists, when you export the data, you must describe the data layout.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4243f-106">Si no está familiarizado con los formatos de datos para importarlos o exportarlos, vea [Formatos de datos para importación en bloque o exportación masiva &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4243f-106">If you are unfamiliar with data formats for importing or exporting data, see [Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span></span>  
  
 <span data-ttu-id="4243f-107">**En este tema:**</span><span class="sxs-lookup"><span data-stu-id="4243f-107">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="4243f-108">Atributos de formato de datos BCP</span><span class="sxs-lookup"><span data-stu-id="4243f-108">bcp Data-Format Attributes</span></span>](#bcpDataFormatAttr)  
  
-   [<span data-ttu-id="4243f-109">Información general de los mensajes específicos del campo</span><span class="sxs-lookup"><span data-stu-id="4243f-109">Overview of the Field-Specific Prompts</span></span>](#FieldSpecificPrompts)  
  
-   [<span data-ttu-id="4243f-110">Almacenar datos campo a campo en un archivo de formato no XML</span><span class="sxs-lookup"><span data-stu-id="4243f-110">Storing Field-by-Field Data in a Non-XML Format File</span></span>](#FieldByFieldNonXmlFF)  
  
-   [<span data-ttu-id="4243f-111">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4243f-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="bcp-data-format-attributes"></a><a name="bcpDataFormatAttr"></a> <span data-ttu-id="4243f-112">Atributo de formato de datos bcp</span><span class="sxs-lookup"><span data-stu-id="4243f-112">bcp Data-Format Attributes</span></span>  
 <span data-ttu-id="4243f-113">El comando `bcp` permite especificar la estructura de cada campo en función de los siguientes atributos de formato de datos:</span><span class="sxs-lookup"><span data-stu-id="4243f-113">The `bcp` command allows you to specify the structure of each field in a data file in terms of the following data-format attributes:</span></span>  
  
-   <span data-ttu-id="4243f-114">tipo de almacenamiento en archivo</span><span class="sxs-lookup"><span data-stu-id="4243f-114">File storage type</span></span>  
  
     <span data-ttu-id="4243f-115">El *tipo de almacenamiento en archivo* describe cómo se almacenan los datos en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="4243f-115">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="4243f-116">La información se puede exportar a un archivo de datos como el tipo de tabla de base de datos correspondiente (formato nativo), como su representación en caracteres (formato de caracteres) o como cualquier tipo de datos que admita la conversión implícita (por ejemplo, si copia datos `smallint` como datos `int`).</span><span class="sxs-lookup"><span data-stu-id="4243f-116">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="4243f-117">Los tipos de datos definidos por el usuario se exportan como sus tipos base correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4243f-117">User-defined data types are exported as their base types.</span></span> <span data-ttu-id="4243f-118">Para obtener más información, vea [Especificar el tipo de almacenamiento en archivo mediante bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4243f-118">For more information, see [Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="4243f-119">Longitud del prefijo</span><span class="sxs-lookup"><span data-stu-id="4243f-119">Prefix length</span></span>  
  
     <span data-ttu-id="4243f-120">Para proporcionar el almacenamiento en archivo más compacto para exportar de forma masiva datos en formato nativo a un archivo de datos, el comando `bcp` precede cada campo con uno o varios caracteres que indican la longitud del campo.</span><span class="sxs-lookup"><span data-stu-id="4243f-120">To provide the most compact file storage for the bulk export of data in native format to a data file, the `bcp` command precedes each field with one or more characters that indicates the length of the field.</span></span> <span data-ttu-id="4243f-121">Estos caracteres se denominan *caracteres de prefijo de longitud*.</span><span class="sxs-lookup"><span data-stu-id="4243f-121">These characters are called *length prefix characters*.</span></span> <span data-ttu-id="4243f-122">Para obtener más información, vea [Especificar la longitud de prefijo en los archivos de datos mediante bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4243f-122">For more information, see [Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="4243f-123">Longitud de campo</span><span class="sxs-lookup"><span data-stu-id="4243f-123">Field length</span></span>  
  
     <span data-ttu-id="4243f-124">La longitud de campo indica el número máximo de caracteres necesarios para representar los datos en formato de carácter.</span><span class="sxs-lookup"><span data-stu-id="4243f-124">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="4243f-125">La longitud de campo ya se conoce si los datos se almacenan en el formato nativo.</span><span class="sxs-lookup"><span data-stu-id="4243f-125">The field length is already known if the data is stored in the native format.</span></span> <span data-ttu-id="4243f-126">Para obtener más información, vea [Especificar la longitud de campo mediante bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4243f-126">For more information, see [Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="4243f-127">Terminador de campo</span><span class="sxs-lookup"><span data-stu-id="4243f-127">Field terminator</span></span>  
  
     <span data-ttu-id="4243f-128">En el caso de campos de datos de caracteres, los caracteres de terminación le permiten marcar el final de cada campo en un archivo de datos (usando un *terminador de campo*) y el final de cada fila (usando un *terminador de fila*).</span><span class="sxs-lookup"><span data-stu-id="4243f-128">For character data fields, optional terminating characters allow you to mark the end of each field in a data file (using a *field terminator*) and the end of each row (using a *row terminator*).</span></span> <span data-ttu-id="4243f-129">Los caracteres de terminación son un modo de indicar a los programas que leen el archivo de datos dónde termina un campo o una fila y dónde comienza otro.</span><span class="sxs-lookup"><span data-stu-id="4243f-129">Terminating characters are one way to indicate to programs reading the data file where one field or row ends and another begins.</span></span> <span data-ttu-id="4243f-130">Para obtener más información, vea [Especificar terminadores de campo y de fila &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4243f-130">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
##  <a name="overview-of-the-field-specific-prompts"></a><a name="FieldSpecificPrompts"></a> <span data-ttu-id="4243f-131">Información general acerca de peticiones específicas de campos</span><span class="sxs-lookup"><span data-stu-id="4243f-131">Overview of the Field-Specific Prompts</span></span>  
 <span data-ttu-id="4243f-132">Si un `bcp` comando interactivo contiene la **opción in** o **out** pero no contiene también el modificador de archivo de formato **(-f**) o un modificador de formato de datos (**-n**, **-c**, **-w**o **-n**), cada columna de la tabla de origen o de destino, el comando solicita cada uno de los atributos anteriores a su vez.</span><span class="sxs-lookup"><span data-stu-id="4243f-132">If an interactive `bcp` command contains the **in** or **out** option but does not also contain either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**),  each column in the source or target table, the command prompts for each of the preceding attributes, in turn.</span></span> <span data-ttu-id="4243f-133">En cada mensaje, el comando `bcp` proporciona un valor predeterminado basado en el tipo de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4243f-133">In each prompt, the `bcp` command provides a default value based on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the table column.</span></span> <span data-ttu-id="4243f-134">Si acepta el valor predeterminado de todos los mensajes, se obtiene el mismo resultado que si especifica un formato nativo ( **-n**) en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="4243f-134">Accepting the default value for all of the prompts produces the same result as specifying native format (**-n**) on the command line.</span></span> <span data-ttu-id="4243f-135">Cada mensaje muestra un valor predeterminado entre corchetes: [*default*].</span><span class="sxs-lookup"><span data-stu-id="4243f-135">Each prompt displays a default value in brackets: [*default*].</span></span> <span data-ttu-id="4243f-136">Para aceptar el valor predeterminado que se muestra, presione la tecla ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="4243f-136">Pressing ENTER accepts the displayed default.</span></span> <span data-ttu-id="4243f-137">Para especificar un valor distinto del predeterminado, escriba el nuevo valor cuando en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="4243f-137">To specify a value other than the default, enter the new value at the prompt.</span></span>  
  
### <a name="example"></a><span data-ttu-id="4243f-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4243f-138">Example</span></span>  
 <span data-ttu-id="4243f-139">El siguiente ejemplo usa el comando `bcp` para exportar masivamente datos masivos desde la tabla `HumanResources.myTeam` interactivamente al archivo `myTeam.txt`.</span><span class="sxs-lookup"><span data-stu-id="4243f-139">The following example uses the `bcp` command to bulk export data from the `HumanResources.myTeam` table interactively to the `myTeam.txt` file.</span></span> <span data-ttu-id="4243f-140">Antes de que pueda ejecutar el ejemplo, debe crear esta tabla.</span><span class="sxs-lookup"><span data-stu-id="4243f-140">Before you can run the example, you must create this table.</span></span> <span data-ttu-id="4243f-141">Para obtener más información sobre la tabla y cómo crearla, vea [Tabla de ejemplo HumanResources.myTeam &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4243f-141">For information about the table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
 <span data-ttu-id="4243f-142">El comando no especifica ni un archivo de formato ni un tipo de datos, lo que ocasiona que `bcp` solicite información acerca del formato de los datos.</span><span class="sxs-lookup"><span data-stu-id="4243f-142">The command specifies neither a format file nor a data type, causing `bcp` to prompt for data-format information.</span></span> <span data-ttu-id="4243f-143">En el símbolo del sistema de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, especifique:</span><span class="sxs-lookup"><span data-stu-id="4243f-143">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam out myTeam.txt -T  
```  
  
 <span data-ttu-id="4243f-144">Para cada columna, bcp solicita los valores específicos de los campos.</span><span class="sxs-lookup"><span data-stu-id="4243f-144">For each column, bcp prompts for field-specific values.</span></span> <span data-ttu-id="4243f-145">El siguiente ejemplo muestra las peticiones específicas de los campos de las columnas `EmployeeID` y `Name` de la tabla y sugiere el tipo de almacenamiento de archivo predeterminado (el formato nativo) para cada columna.</span><span class="sxs-lookup"><span data-stu-id="4243f-145">The following example shows the field-specific prompts for the `EmployeeID` and `Name` columns of the table, and suggests the default file storage type (the native format) for each column.</span></span> <span data-ttu-id="4243f-146">Las longitudes de prefijo de la columna `EmployeeID` y `Name` son 0 y 2, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4243f-146">The prefix lengths of the `EmployeeID` and `Name` column are 0 and 2, respectively.</span></span> <span data-ttu-id="4243f-147">El usuario especifica una coma (`,`) como terminador de cada campo.</span><span class="sxs-lookup"><span data-stu-id="4243f-147">The user specifies a comma (`,`) as the terminator of each field.</span></span>  
  
 `Enter the file storage type of field EmployeeID [smallint]:`  
  
 `Enter prefix-length of field EmployeeID [0]:`  
  
 `Enter field terminator [none]:,`  
  
 `Enter the file storage type of field Name [nvarchar]:`  
  
 `Enter prefix length of field Name [2]:`  
  
 `Enter field terminator [none]:,`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 <span data-ttu-id="4243f-148">Se muestran en orden peticiones equivalentes (cuando se necesitan) para cada una de las columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="4243f-148">Equivalent prompts (as needed) are displayed for each of the table columns in order.</span></span>  
  
##  <a name="storing-field-by-field-data-in-a-non-xml-format-file"></a><a name="FieldByFieldNonXmlFF"></a> <span data-ttu-id="4243f-149">Almacenar datos campo a campo en un formato de archivo no XML</span><span class="sxs-lookup"><span data-stu-id="4243f-149">Storing Field-by-Field Data in a Non-XML Format File</span></span>  
 <span data-ttu-id="4243f-150">Después de especificar todas las columnas de una tabla, el comando `bcp` le solicita que genere, si lo desea, un archivo de formato no XML para almacenar la información campo a campo recientemente suministrada (vea el ejemplo procedente).</span><span class="sxs-lookup"><span data-stu-id="4243f-150">After all of the table columns are specified, the `bcp` command prompts you to optionally generate a non-XML format file that stores the field-by-field information just supplied (see the preceding example).</span></span> <span data-ttu-id="4243f-151">Si elige generar un archivo de formato, puede hacerlo siempre que exporte datos fuera de esa tabla o importe datos estructurados de manera similar en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4243f-151">If you choose to generate a format file, you can whenever you export data out of that table or import like-structured data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4243f-152">Puede utilizar el archivo de formato para importar datos de manera masiva desde el archivo de datos en una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o para exportar datos de manera masiva desde la tabla sin la necesidad de volver a especificar el formato.</span><span class="sxs-lookup"><span data-stu-id="4243f-152">You can use the format file to bulk import data from the data file into an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to bulk export data from the table, without needing to respecify the format.</span></span> <span data-ttu-id="4243f-153">Para obtener más información, vea [Archivos de formato para importar o exportar datos &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4243f-153">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="4243f-154">En el siguiente ejemplo se crea un archivo de formato no XML llamado `myFormatFile.fmt`:</span><span class="sxs-lookup"><span data-stu-id="4243f-154">The following example creates a non-XML format file named `myFormatFile.fmt`:</span></span>  
  
 `Do you want to save this format information in a file? [Y/n] y`  
  
 `Host filename: [bcp.fmt]myFormatFile.fmt`  
  
 <span data-ttu-id="4243f-155">El nombre predeterminado del archivo de formato es bcp.fmt, pero puede especificar un nombre de archivo diferente si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="4243f-155">The default name for the format file is bcp.fmt, but you can specify a different file name if you choose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4243f-156">En el caso de un archivo de datos que use un solo formato de datos para su tipo de almacenamiento de archivo, por ejemplo, un formato de caracteres o un formato nativo, puede crear rápidamente un archivo de formato sin exportar o importar datos usando la opción **format** .</span><span class="sxs-lookup"><span data-stu-id="4243f-156">For a data file that uses a single data format for its file-storage type, such as character or native format, you can quickly create a format file without exporting or importing data by using the **format** option.</span></span> <span data-ttu-id="4243f-157">Este enfoque tiene las ventajas de resultar sencillo y permitirle crear un archivo de formato XML o no XML.</span><span class="sxs-lookup"><span data-stu-id="4243f-157">This approach has the advantages of being easy and of allowing you to create either an XML format file or a non-XML format file.</span></span> <span data-ttu-id="4243f-158">Para obtener más información, vea [Crear un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4243f-158">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4243f-159">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4243f-159">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4243f-160">Especificar el tipo de almacenamiento en archivo mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4243f-160">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="4243f-161">Especificar la longitud de prefijo en los archivos de datos mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4243f-161">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="4243f-162">Especificar la longitud de campo mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4243f-162">Specify Field Length by Using bcp &#40;SQL Server&#41;</span></span>](specify-field-length-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="4243f-163">Especificar terminadores de campo y de fila &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4243f-163">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="4243f-164">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="4243f-164">Related Content</span></span>  
 <span data-ttu-id="4243f-165">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4243f-165">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4243f-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4243f-166">See Also</span></span>  
 <span data-ttu-id="4243f-167">[Importar y exportar datos en bloque &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4243f-167">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="4243f-168">[Formatos de datos para importación en bloque o exportación masiva &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4243f-168">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 <span data-ttu-id="4243f-169">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="4243f-169">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="4243f-170">Tipos de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4243f-170">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
