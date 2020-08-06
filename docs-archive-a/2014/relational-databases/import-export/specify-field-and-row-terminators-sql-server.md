---
title: Especificar terminadores de campo y de fila (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bcp utility [SQL Server], terminators
- field terminators [SQL Server]
- data formats [SQL Server], terminators
- row terminators [SQL Server]
- terminators [SQL Server]
ms.assetid: f68b6782-f386-4947-93c4-e89110800704
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 548beeae68f5585c5cf2ba56b67027532ab43b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749941"
---
# <a name="specify-field-and-row-terminators-sql-server"></a><span data-ttu-id="0469b-102">Especificar terminadores de campo y de fila (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0469b-102">Specify Field and Row Terminators (SQL Server)</span></span>
  <span data-ttu-id="0469b-103">En los campos de datos de caracteres, los caracteres de terminación opcionales permiten marcar el final de cada campo de un archivo de datos con un *terminador de campo* y el final de cada fila con un *terminador de fila*.</span><span class="sxs-lookup"><span data-stu-id="0469b-103">For character data fields, optional terminating characters allow you to mark the end of each field in a data file with a *field terminator* and the end of each row with a *row terminator*.</span></span> <span data-ttu-id="0469b-104">Los caracteres de terminación son una forma de indicar a los programas que leen el archivo de datos dónde termina un campo o una fila y dónde comienza otro.</span><span class="sxs-lookup"><span data-stu-id="0469b-104">Terminating characters are one way to indicate to programs that read the data file where one field or row ends and another field or row begins.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0469b-105">Cuando utilice el formato nativo o nativo Unicode, use prefijos de longitud en lugar de terminadores de campo.</span><span class="sxs-lookup"><span data-stu-id="0469b-105">When you use native or Unicode native format, use length prefixes rather than field terminators.</span></span> <span data-ttu-id="0469b-106">Los datos de formato nativo pueden entrar en conflicto con los terminadores, ya que un archivo de datos de formato nativo se almacena en el formato de datos binario interno de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0469b-106">Native format data can conflict with terminators because a native-format data file is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format.</span></span>  
  
## <a name="characters-supported-as-terminators"></a><span data-ttu-id="0469b-107">Caracteres admitidos como terminadores</span><span class="sxs-lookup"><span data-stu-id="0469b-107">Characters Supported As Terminators</span></span>  
 <span data-ttu-id="0469b-108">El comando **bcp** , la instrucción BULK INSERT y el proveedor de conjuntos de filas BULK OPENROWSET admiten una serie de caracteres como terminadores de campo o de fila y siempre buscan la primera instancia de cada terminador.</span><span class="sxs-lookup"><span data-stu-id="0469b-108">The **bcp** command, BULK INSERT statement, and the OPENROWSET bulk rowset provider support a variety of characters as field or row terminators and always look for the first instance of each terminator.</span></span> <span data-ttu-id="0469b-109">La siguiente tabla enumera los caracteres admitidos como terminadores.</span><span class="sxs-lookup"><span data-stu-id="0469b-109">The following table lists the supported characters for terminators.</span></span>  
  
|<span data-ttu-id="0469b-110">Carácter de terminación</span><span class="sxs-lookup"><span data-stu-id="0469b-110">Terminating character</span></span>|<span data-ttu-id="0469b-111">Indicado por</span><span class="sxs-lookup"><span data-stu-id="0469b-111">Indicated by</span></span>|  
|---------------------------|------------------|  
|<span data-ttu-id="0469b-112">Pestaña</span><span class="sxs-lookup"><span data-stu-id="0469b-112">Tab</span></span>|<span data-ttu-id="0469b-113">\t</span><span class="sxs-lookup"><span data-stu-id="0469b-113">\t</span></span><br /><br /> <span data-ttu-id="0469b-114">Terminador de campo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0469b-114">This is the default field terminator.</span></span>|  
|<span data-ttu-id="0469b-115">Carácter de nueva línea</span><span class="sxs-lookup"><span data-stu-id="0469b-115">Newline character</span></span>|<span data-ttu-id="0469b-116">\n</span><span class="sxs-lookup"><span data-stu-id="0469b-116">\n</span></span><br /><br /> <span data-ttu-id="0469b-117">Terminador de fila predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0469b-117">This is the default row terminator.</span></span>|  
|<span data-ttu-id="0469b-118">Retorno de carro/avance de línea</span><span class="sxs-lookup"><span data-stu-id="0469b-118">Carriage return/line feed</span></span>|<span data-ttu-id="0469b-119">\r</span><span class="sxs-lookup"><span data-stu-id="0469b-119">\r</span></span>|  
|<span data-ttu-id="0469b-120">Barra diagonal inversa<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0469b-120">Backslash<sup>1</sup></span></span>|\\\|  
|<span data-ttu-id="0469b-121">Terminador null (terminador no visible)<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="0469b-121">Null terminator (nonvisible terminator)<sup>2</sup></span></span>|<span data-ttu-id="0469b-122">\0</span><span class="sxs-lookup"><span data-stu-id="0469b-122">\0</span></span>|  
|<span data-ttu-id="0469b-123">Cualquier carácter imprimible (los caracteres de control no se pueden imprimir, excepto los valores NULL, tabulaciones, caracteres de nueva línea y retornos de carro)</span><span class="sxs-lookup"><span data-stu-id="0469b-123">Any printable character (control characters are not printable, except null, tab, newline, and carriage return)</span></span>|<span data-ttu-id="0469b-124">(\*, A, t, l, etc.)</span><span class="sxs-lookup"><span data-stu-id="0469b-124">(\*, A, t, l, and so on)</span></span>|  
|<span data-ttu-id="0469b-125">Una cadena de hasta 10 caracteres imprimibles, incluidos algunos o todos los terminadores enumerados anteriormente</span><span class="sxs-lookup"><span data-stu-id="0469b-125">String of up to 10 printable characters, including some or all of the terminators listed earlier</span></span>|<span data-ttu-id="0469b-126">(\*\*\t\*\*, end, !!!!!!!!!!, \t-\n, etc.)</span><span class="sxs-lookup"><span data-stu-id="0469b-126">(\*\*\t\*\*, end, !!!!!!!!!!, \t-\n, and so on)</span></span>|  
  
 <span data-ttu-id="0469b-127"><sup>1</sup> solo los caracteres t, n, r, 0 y ' \ 0 ' funcionan con el carácter de escape de barra diagonal inversa para generar un carácter de control.</span><span class="sxs-lookup"><span data-stu-id="0469b-127"><sup>1</sup> Only the t, n, r, 0 and '\0' characters work with the backslash escape character to produce a control character.</span></span>  
  
 <span data-ttu-id="0469b-128"><sup>2</sup> aunque el carácter de control null (\ 0) no es visible cuando se imprime, es un carácter distinto en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="0469b-128"><sup>2</sup> Even though the null control character (\0) is not visible when printed, it is a distinct character in the data file.</span></span> <span data-ttu-id="0469b-129">Esto significa que el uso del carácter de control NULL como terminador de campo o de fila es diferente a no tener ningún terminador de campo o de fila.</span><span class="sxs-lookup"><span data-stu-id="0469b-129">This means that using the null control character as a field or row terminator is different than having no field or row terminator at all.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0469b-130">Si en los datos hay un carácter terminador, se interpreta como un terminador, no como datos, y se interpreta que los datos posteriores a ese carácter pertenecen al campo o registro siguiente.</span><span class="sxs-lookup"><span data-stu-id="0469b-130">If a terminator character occurs within the data, it is interpreted as a terminator, not as data, and the data after that character is interpreted as belonging to the next field or record.</span></span> <span data-ttu-id="0469b-131">Por lo tanto, elija los terminadores con atención para asegurarse de que nunca aparezcan en los datos.</span><span class="sxs-lookup"><span data-stu-id="0469b-131">Therefore, choose your terminators carefully to make sure that they never appear in your data.</span></span> <span data-ttu-id="0469b-132">Por ejemplo, un terminador de campo que funcione como suplente inferior no resultaría una buena opción para un terminador de campo si los datos contienen dicho suplente inferior.</span><span class="sxs-lookup"><span data-stu-id="0469b-132">For example, a low surrogate field terminator would not be a good choice for a field terminator if the data contains that low surrogate.</span></span>  
  
## <a name="using-row-terminators"></a><span data-ttu-id="0469b-133">Usar terminadores de fila</span><span class="sxs-lookup"><span data-stu-id="0469b-133">Using Row Terminators</span></span>  
 <span data-ttu-id="0469b-134">El terminador de fila puede ser el mismo carácter que el terminador del último campo.</span><span class="sxs-lookup"><span data-stu-id="0469b-134">The row terminator can be the same character as the terminator for the last field.</span></span> <span data-ttu-id="0469b-135">Sin embargo, normalmente resulta útil un terminador de fila distinto.</span><span class="sxs-lookup"><span data-stu-id="0469b-135">Generally, however, a distinct row terminator is useful.</span></span> <span data-ttu-id="0469b-136">Por ejemplo, para generar un resultado en formato tabular, termine el último campo de cada fila con el carácter de nueva línea (\n) y todos los demás campos con el carácter de tabulación (\t).</span><span class="sxs-lookup"><span data-stu-id="0469b-136">For example, to produce tabular output, terminate the last field in each row with the newline character (\n) and all other fields with the tab character (\t).</span></span> <span data-ttu-id="0469b-137">Para colocar cada registro de datos en su propia línea en el archivos de datos, especifique la combinación \r\n como terminador de fila.</span><span class="sxs-lookup"><span data-stu-id="0469b-137">To place each data record on its own line in the data file, specify the combination \r\n as the row terminator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0469b-138">Cuando usa **bcp** en modo interactivo y especifica \n (nueva línea) como terminador de fila, **bcp** antepondrá automáticamente el carácter \r (retorno de carro) como prefijo, lo que genera un terminador de fila \r\n.</span><span class="sxs-lookup"><span data-stu-id="0469b-138">When you use **bcp** interactively and specify \n (newline) as the row terminator, **bcp** automatically prefixes it with a \r (carriage return) character, which results in a row terminator of \r\n.</span></span>  
  
## <a name="specifying-terminators-for-bulk-export"></a><span data-ttu-id="0469b-139">Especificar terminadores para la exportación masiva</span><span class="sxs-lookup"><span data-stu-id="0469b-139">Specifying Terminators for Bulk Export</span></span>  
 <span data-ttu-id="0469b-140">Cuando realiza una exportación masiva de `char` `nchar` datos o y desea usar un terminador no predeterminado, debe especificar el terminador en el comando **BCP** .</span><span class="sxs-lookup"><span data-stu-id="0469b-140">When you bulk export `char` or `nchar` data, and want to use a non-default terminator, you must specify the terminator to the **bcp** command.</span></span> <span data-ttu-id="0469b-141">Los terminadores se pueden especificar de cualquiera de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="0469b-141">You can specify terminators in any of the following ways:</span></span>  
  
-   <span data-ttu-id="0469b-142">Con un archivo de formato que especifica el terminador campo a campo.</span><span class="sxs-lookup"><span data-stu-id="0469b-142">With a format file that specifies the terminator on a field-by-field basis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0469b-143">Para obtener más información sobre cómo usar archivos de formato, vea [Archivos de formato para importar o exportar datos &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0469b-143">For information about how to use format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
-   <span data-ttu-id="0469b-144">Sin un archivo de formato, existen las alternativas siguientes:</span><span class="sxs-lookup"><span data-stu-id="0469b-144">Without a format file, the following alternatives exist:</span></span>  
  
    -   <span data-ttu-id="0469b-145">Usar el modificador **-t** para especificar el terminador de fila en todos los campos, excepto el último campo de la fila, y usar el modificador **-r** para especificar un terminador de fila.</span><span class="sxs-lookup"><span data-stu-id="0469b-145">Using the **-t** switch to specify the row terminator for all the fields except the last field in the row and using the **-r** switch to specify a row terminator.</span></span>  
  
    -   <span data-ttu-id="0469b-146">Usar un modificador de formato de caracteres ( **-c** o **-w**) sin el modificador **-t** , lo que establece el carácter de tabulación, \t, como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="0469b-146">Using a character-format switch (**-c** or **-w**) without the **-t** switch, which sets the field terminator to the tab character, \t.</span></span> <span data-ttu-id="0469b-147">Esto equivale a especificar **-t**\t.</span><span class="sxs-lookup"><span data-stu-id="0469b-147">This is the same as specifying **-t**\t.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0469b-148">Si se especifica el modificador **-n** (datos nativos) o **-N** (nativos Unicode), no se insertan los terminadores.</span><span class="sxs-lookup"><span data-stu-id="0469b-148">If you specify the **-n** (native data) or **-N** (Unicode native) switch, terminators are not inserted.</span></span>  
  
    -   <span data-ttu-id="0469b-149">Si un comando **bcp** interactivo contiene la opción **in** o **out** sin el modificador de archivo de formato ( **-f**) ni un modificador de formato de datos ( **-n**, **-c**, **-w**o **-N**), y ha decidido no especificar la longitud de prefijo ni la longitud de campo, el comando solicita el terminador de cada campo, con el valor predeterminado "none":</span><span class="sxs-lookup"><span data-stu-id="0469b-149">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), and you have chosen not to specify prefix length and field length, the command prompts for the field terminator of each field, with a default of none:</span></span>  
  
         `Enter field terminator [none]:`  
  
         <span data-ttu-id="0469b-150">Generalmente, el valor predeterminado es una opción apropiada.</span><span class="sxs-lookup"><span data-stu-id="0469b-150">Generally, the default is a suitable choice.</span></span> <span data-ttu-id="0469b-151">Sin embargo, para los campos de datos `char` o `nchar`, vea la siguiente subsección, "Directrices para utilizar terminadores".</span><span class="sxs-lookup"><span data-stu-id="0469b-151">However, for `char` or `nchar` data fields, see the following subsection, "Guidelines for Using Terminators."</span></span> <span data-ttu-id="0469b-152">Para obtener un ejemplo que muestra esta solicitud en contexto, vea [Especificar formatos de datos por razones de compatibilidad mediante bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0469b-152">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0469b-153">Después de que se especifiquen de forma interactiva todos los campos de un comando **bcp**, el comando solicita que guarde sus respuestas para cada campo en un archivo que no tenga el formato XML.</span><span class="sxs-lookup"><span data-stu-id="0469b-153">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="0469b-154">Para obtener más información sobre los archivos de formato no XML, vea [Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0469b-154">For more information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="guidelines-for-using-terminators"></a><span data-ttu-id="0469b-155">Directrices para utilizar terminadores</span><span class="sxs-lookup"><span data-stu-id="0469b-155">Guidelines for Using Terminators</span></span>  
 <span data-ttu-id="0469b-156">En algunas situaciones, un terminador resulta útil para un campo de datos `char` o `nchar`.</span><span class="sxs-lookup"><span data-stu-id="0469b-156">In some situations, a terminator is useful for a `char` or `nchar` data field.</span></span> <span data-ttu-id="0469b-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0469b-157">For example:</span></span>  
  
-   <span data-ttu-id="0469b-158">En el caso de una columna de datos que contiene un valor NULL de un archivo de datos que se va a importar a un programa que no entiende la información sobre la longitud de prefijo.</span><span class="sxs-lookup"><span data-stu-id="0469b-158">For a data column that contains a null value in a data file that will be imported into a program that does not understand the prefix length information.</span></span>  
  
     <span data-ttu-id="0469b-159">Cualquier columna de datos que contenga un valor NULL se considera de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="0469b-159">Any data column that contains a null value is considered variable length.</span></span> <span data-ttu-id="0469b-160">En ausencia de longitudes de prefijo, se necesita un terminador para identificar el final de un campo NULL, lo que garantiza la correcta interpretación de los datos.</span><span class="sxs-lookup"><span data-stu-id="0469b-160">In the absence of prefix lengths, a terminator is necessary to identify the end of a null field, making sure that the data is correctly interpreted.</span></span>  
  
-   <span data-ttu-id="0469b-161">En el caso de una columna de longitud fija larga cuyo espacio solo se utiliza parcialmente en numerosas filas.</span><span class="sxs-lookup"><span data-stu-id="0469b-161">For a long fixed-length column whose space is only partially used by many rows.</span></span>  
  
     <span data-ttu-id="0469b-162">En este caso, si se especifica un terminador, se puede minimizar el espacio de almacenamiento, lo que permitiría que el campo fuera tratado como un campo de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="0469b-162">In this situation, specifying a terminator can minimize storage space allowing the field to be treated as a variable-length field.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0469b-163">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0469b-163">Examples</span></span>  
 <span data-ttu-id="0469b-164">En este ejemplo se exportan de forma masiva los datos de la tabla `AdventureWorks``HumanResources.Department` al archivo de datos `Department-c-t.txt` usando el formato de caracteres, con una coma como terminador de campo y el carácter de nueva línea (\n) como terminador de fila.</span><span class="sxs-lookup"><span data-stu-id="0469b-164">This example bulk exports the data from the `AdventureWorks``HumanResources.Department` table to the `Department-c-t.txt` data file using character format, with a comma as a field terminator and the newline character (\n) as the row terminator.</span></span>  
  
 <span data-ttu-id="0469b-165">El comando **bcp** contiene los siguientes modificadores.</span><span class="sxs-lookup"><span data-stu-id="0469b-165">The **bcp** command contains the following switches.</span></span>  
  
|<span data-ttu-id="0469b-166">Switch</span><span class="sxs-lookup"><span data-stu-id="0469b-166">Switch</span></span>|<span data-ttu-id="0469b-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="0469b-167">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0469b-168">**-c**</span><span class="sxs-lookup"><span data-stu-id="0469b-168">**-c**</span></span>|<span data-ttu-id="0469b-169">Especifica que los campos de datos se cargarán como datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0469b-169">Specifies that the data fields be loaded as character data.</span></span>|  
|<span data-ttu-id="0469b-170">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="0469b-170">**-t** `,`</span></span>|<span data-ttu-id="0469b-171">Especifica una coma (,) como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="0469b-171">Specifies a comma (,) as the field terminator.</span></span>|  
|<span data-ttu-id="0469b-172">**-r** \n</span><span class="sxs-lookup"><span data-stu-id="0469b-172">**-r** \n</span></span>|<span data-ttu-id="0469b-173">Especifica el terminador de fila como un carácter de nueva línea.</span><span class="sxs-lookup"><span data-stu-id="0469b-173">Specifies the row terminator as a newline character.</span></span> <span data-ttu-id="0469b-174">Terminador de fila predeterminado, por lo que especificarlo es opcional.</span><span class="sxs-lookup"><span data-stu-id="0469b-174">This is the default row terminator, so specifying it is optional.</span></span>|  
|<span data-ttu-id="0469b-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="0469b-175">**-T**</span></span>|<span data-ttu-id="0469b-176">Especifica que la utilidad **bcp** se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una conexión de confianza utilizando la seguridad integrada.</span><span class="sxs-lookup"><span data-stu-id="0469b-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="0469b-177">Si no se especifica **-T** , es necesario especificar **-U** y **-P** para iniciar sesión correctamente.</span><span class="sxs-lookup"><span data-stu-id="0469b-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="0469b-178">Para obtener más información, consulte [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="0469b-178">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="0469b-179">En el símbolo del sistema de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, especifique:</span><span class="sxs-lookup"><span data-stu-id="0469b-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.Department out C:\myDepartment-c-t.txt -c -t, -r \n -T  
```  
  
 <span data-ttu-id="0469b-180">Esto crea `Department-c-t.txt`, que contiene 16 registros con cuatro campos cada uno.</span><span class="sxs-lookup"><span data-stu-id="0469b-180">This creates `Department-c-t.txt`, which contains 16 records with four fields each.</span></span> <span data-ttu-id="0469b-181">Los campos se separan mediante una coma.</span><span class="sxs-lookup"><span data-stu-id="0469b-181">The fields are separated by a comma.</span></span>  
  
## <a name="specifying-terminators-for-bulk-import"></a><span data-ttu-id="0469b-182">Especificar terminadores para la importación masiva</span><span class="sxs-lookup"><span data-stu-id="0469b-182">Specifying Terminators for Bulk Import</span></span>  
 <span data-ttu-id="0469b-183">Cuando realice una importación masiva de datos `char` o `nchar`, el comando de importación masiva debe reconocer los terminadores que se utilizan en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="0469b-183">When you bulk import `char` or `nchar` data, the bulk-import command must recognize the terminators that are used in the data file.</span></span> <span data-ttu-id="0469b-184">La forma de especificar los terminadores depende del comando de importación masiva, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="0469b-184">How terminators can be specified depends on the bulk-import command, as follows:</span></span>  
  
-   <span data-ttu-id="0469b-185">**bcp**</span><span class="sxs-lookup"><span data-stu-id="0469b-185">**bcp**</span></span>  
  
     <span data-ttu-id="0469b-186">La especificación de terminadores para una operación de importación utiliza la misma sintaxis que para una operación de exportación.</span><span class="sxs-lookup"><span data-stu-id="0469b-186">Specifying terminators for an import operation uses the same syntax as for an export operation.</span></span> <span data-ttu-id="0469b-187">Para obtener más información, vea "Especificar terminadores para la exportación masiva" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="0469b-187">For more information, see "Specifying Terminators for Bulk Export," earlier in this topic.</span></span>  
  
-   <span data-ttu-id="0469b-188">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="0469b-188">BULK INSERT</span></span>  
  
     <span data-ttu-id="0469b-189">Los terminadores se pueden especificar para campos individuales en un archivo de formato o para todo el archivo de datos mediante los calificadores que figuran en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="0469b-189">Terminators can be specified for individual fields in a format file or for the whole data file by using the qualifiers shown in the following table.</span></span>  
  
    |<span data-ttu-id="0469b-190">Qualifier</span><span class="sxs-lookup"><span data-stu-id="0469b-190">Qualifier</span></span>|<span data-ttu-id="0469b-191">Descripción</span><span class="sxs-lookup"><span data-stu-id="0469b-191">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="0469b-192">FIELDTERMINATOR **= ' *`field_terminator`* '**</span><span class="sxs-lookup"><span data-stu-id="0469b-192">FIELDTERMINATOR **='*`field_terminator`*'**</span></span>|<span data-ttu-id="0469b-193">Especifica el terminador de campo que se utilizará para los archivos de caracteres y de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="0469b-193">Specifies the field terminator to be used for character and Unicode character data files.</span></span><br /><br /> <span data-ttu-id="0469b-194">El valor predeterminado es \t (carácter de tabulación).</span><span class="sxs-lookup"><span data-stu-id="0469b-194">The default is \t (tab character).</span></span>|  
    |<span data-ttu-id="0469b-195">ROWTERMINATOR **= ' *`row_terminator`* '**</span><span class="sxs-lookup"><span data-stu-id="0469b-195">ROWTERMINATOR **='*`row_terminator`*'**</span></span>|<span data-ttu-id="0469b-196">Especifica el terminador de fila que se utilizará para los archivos de caracteres y de caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="0469b-196">Specifies the row terminator to be used for character and Unicode character data files.</span></span><br /><br /> <span data-ttu-id="0469b-197">El valor predeterminado es \n (carácter de nueva línea).</span><span class="sxs-lookup"><span data-stu-id="0469b-197">The default is \n (newline character).</span></span>|  
  
     <span data-ttu-id="0469b-198">Para obtener más información, vea [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0469b-198">For more information, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
-   <span data-ttu-id="0469b-199">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="0469b-199">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
     <span data-ttu-id="0469b-200">Para el proveedor de conjuntos de filas BULK OPENROWSET, los terminadores solo se pueden especificar en el archivo de formato (necesario excepto para tipos de datos de objetos grandes).</span><span class="sxs-lookup"><span data-stu-id="0469b-200">For the OPENROWSET bulk rowset provider, terminators can be specified only in the format file (which is required except for large-object data types).</span></span> <span data-ttu-id="0469b-201">Si un archivo de caracteres utiliza un terminador no predeterminado, debe definirse en el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="0469b-201">If a character data file uses a non-default terminator, it must be defined in the format file.</span></span> <span data-ttu-id="0469b-202">Para obtener más información, vea [Crear un archivo de formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md) y [Usar un archivo de formato para importar datos en bloque &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0469b-202">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md) and [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
     <span data-ttu-id="0469b-203">Para obtener más información sobre la cláusula OPENROWSET BULK, vea [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0469b-203">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="0469b-204">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0469b-204">Examples</span></span>  
 <span data-ttu-id="0469b-205">En los ejemplos de esta sección se importan de forma masiva caracteres del archivo de datos `Department-c-t.txt` creado en el ejemplo anterior en la tabla `myDepartment` de la base de datos de ejemplo [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0469b-205">The examples in this section bulk import character data form the `Department-c-t.txt` data file created in the preceding example into the `myDepartment` table in the [!INCLUDE[ssSampleDBUserInputNonLocal](../../includes/sssampledbuserinputnonlocal-md.md)] sample database.</span></span> <span data-ttu-id="0469b-206">Antes de poder ejecutar los ejemplos, debe crear esta tabla.</span><span class="sxs-lookup"><span data-stu-id="0469b-206">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="0469b-207">Para crear esta tabla en el esquema **dbo** , en el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="0469b-207">To create this table under the **dbo** schema, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks;  
GO  
DROP TABLE myDepartment;  
CREATE TABLE myDepartment   
(DepartmentID smallint,  
Name nvarchar(50),  
GroupName nvarchar(50) NULL,  
ModifiedDate datetime not NULL CONSTRAINT DF_AddressType_ModifiedDate DEFAULT (GETDATE())  
);  
GO  
  
```  
  
#### <a name="a-using-bcp-to-interactively-specify-terminators"></a><span data-ttu-id="0469b-208">A.</span><span class="sxs-lookup"><span data-stu-id="0469b-208">A.</span></span> <span data-ttu-id="0469b-209">Usar bcp para especificar terminadores interactivamente</span><span class="sxs-lookup"><span data-stu-id="0469b-209">Using bcp to interactively specify terminators</span></span>  
 <span data-ttu-id="0469b-210">En el ejemplo siguiente se importa de forma masiva el archivo de datos `Department-c-t.txt` mediante un comando `bcp` .</span><span class="sxs-lookup"><span data-stu-id="0469b-210">The following example bulk imports the `Department-c-t.txt` data file using a `bcp` command.</span></span> <span data-ttu-id="0469b-211">Este comando utiliza los mismos modificadores de comando que el comando de exportación masiva.</span><span class="sxs-lookup"><span data-stu-id="0469b-211">This command uses the same command switches as the bulk export command.</span></span> <span data-ttu-id="0469b-212">Para obtener más información, vea "Especificar terminadores para la exportación masiva" anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="0469b-212">For more information, see "Specifying Terminators for Bulk Export," earlier in this topic.</span></span>  
  
 <span data-ttu-id="0469b-213">En el símbolo del sistema de Windows, especifique:</span><span class="sxs-lookup"><span data-stu-id="0469b-213">At the Windows command prompt enter:</span></span>  
  
```  
bcp AdventureWorks..myDepartment in C:\myDepartment-c-t.txt -c -t , -r \n -T  
```  
  
#### <a name="b-using-bulk-insert-to-interactively-specify-terminators"></a><span data-ttu-id="0469b-214">B.</span><span class="sxs-lookup"><span data-stu-id="0469b-214">B.</span></span> <span data-ttu-id="0469b-215">Usar BULK INSERT para especificar terminadores interactivamente</span><span class="sxs-lookup"><span data-stu-id="0469b-215">Using BULK INSERT to interactively specify terminators</span></span>  
 <span data-ttu-id="0469b-216">En el ejemplo siguiente se importa de forma masiva el archivo de datos `Department-c-t.txt` mediante una instrucción `BULK INSERT` que utiliza los calificadores que figuran en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="0469b-216">The following example bulk imports the `Department-c-t.txt` data file using a `BULK INSERT` statement that uses the qualifiers shown in the following table.</span></span>  
  
|<span data-ttu-id="0469b-217">Opción</span><span class="sxs-lookup"><span data-stu-id="0469b-217">Option</span></span>|<span data-ttu-id="0469b-218">Atributo</span><span class="sxs-lookup"><span data-stu-id="0469b-218">Attribute</span></span>|  
|------------|---------------|  
|<span data-ttu-id="0469b-219">DATAFILETYPE **= ' `char` '**</span><span class="sxs-lookup"><span data-stu-id="0469b-219">DATAFILETYPE **='`char`'**</span></span>|<span data-ttu-id="0469b-220">Especifica que los campos de datos se cargarán como datos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="0469b-220">Specifies that the data fields be loaded as character data.</span></span>|  
|<span data-ttu-id="0469b-221">FIELDTERMINATOR **='** `,` **'**</span><span class="sxs-lookup"><span data-stu-id="0469b-221">FIELDTERMINATOR **='**`,`**'**</span></span>|<span data-ttu-id="0469b-222">Especifica una coma (`,`) como terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="0469b-222">Specifies a comma (`,`) as the field terminator.</span></span>|  
|<span data-ttu-id="0469b-223">ROWTERMINATOR **='** `\n` **'**</span><span class="sxs-lookup"><span data-stu-id="0469b-223">ROWTERMINATOR **='**`\n`**'**</span></span>|<span data-ttu-id="0469b-224">Especifica el terminador de fila como un carácter de nueva línea.</span><span class="sxs-lookup"><span data-stu-id="0469b-224">Specifies the row terminator as a newline character.</span></span>|  
  
 <span data-ttu-id="0469b-225">En el Editor de consultas de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] , ejecute el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="0469b-225">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myDepartment FROM 'C:\myDepartment-c-t.txt'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      ROWTERMINATOR = '\n'  
);  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="0469b-226">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0469b-226">See Also</span></span>  
 <span data-ttu-id="0469b-227">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="0469b-227">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="0469b-228">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0469b-228">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="0469b-229">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0469b-229">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="0469b-230">[Especificar la longitud de campo mediante bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0469b-230">[Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="0469b-231">[Especificar la longitud de prefijo en los archivos de datos mediante bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0469b-231">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="0469b-232">Especificar el tipo de almacenamiento en archivo mediante bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0469b-232">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
  
