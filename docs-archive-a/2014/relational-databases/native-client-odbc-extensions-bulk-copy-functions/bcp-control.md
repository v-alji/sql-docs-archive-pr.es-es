---
title: bcp_control | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_control
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_control function
ms.assetid: 32187282-1385-4c52-9134-09f061eb44f5
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ea5d60da8069707a53f3bdf2de53345cd11090f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662001"
---
# <a name="bcp_control"></a><span data-ttu-id="c1bd8-102">bcp_control</span><span class="sxs-lookup"><span data-stu-id="c1bd8-102">bcp_control</span></span>
  <span data-ttu-id="c1bd8-103">Cambia la configuración predeterminada de varios parámetros de control para una copia masiva entre un archivo y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1bd8-103">Changes the default settings for various control parameters for a bulk copy between a file and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1bd8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1bd8-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_control (  
HDBC   
hdbc  
,  
INT   
eOption  
,  
void*   
iValue  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c1bd8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c1bd8-105">Arguments</span></span>  
 <span data-ttu-id="c1bd8-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="c1bd8-106">*hdbc*</span></span>  
 <span data-ttu-id="c1bd8-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="c1bd8-108">*eOption*</span><span class="sxs-lookup"><span data-stu-id="c1bd8-108">*eOption*</span></span>  
 <span data-ttu-id="c1bd8-109">Es uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="c1bd8-109">Is one of the following:</span></span>  
  
 <span data-ttu-id="c1bd8-110">BCPABORT</span><span class="sxs-lookup"><span data-stu-id="c1bd8-110">BCPABORT</span></span>  
 <span data-ttu-id="c1bd8-111">Detiene una operación de copia masiva que ya está en curso.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-111">Stops a bulk-copy operation that is already in progress.</span></span> <span data-ttu-id="c1bd8-112">Llame a **bcp_control** con un *eOption* de BCPABORT desde otro subproceso para detener una operación de copia masiva en ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-112">Call **bcp_control** with an *eOption* of BCPABORT from another thread to stop a running bulk copy operation.</span></span> <span data-ttu-id="c1bd8-113">Se omite el parámetro *iValue* .</span><span class="sxs-lookup"><span data-stu-id="c1bd8-113">The *iValue* parameter is ignored.</span></span>  
  
 <span data-ttu-id="c1bd8-114">BCPBATCH</span><span class="sxs-lookup"><span data-stu-id="c1bd8-114">BCPBATCH</span></span>  
 <span data-ttu-id="c1bd8-115">Es el número de filas por lote.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-115">Is the number of rows per batch.</span></span> <span data-ttu-id="c1bd8-116">El valor predeterminado es 0, que indica todas las filas de una tabla, cuando se extraen los datos, o todas las filas del archivo de datos del usuario, cuando los datos se copian en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1bd8-116">The default is 0, which indicates either all rows in a table, when data is being extracted, or all rows in the user data file, when data is being copied to an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c1bd8-117">Un valor inferior a 1 restablece el valor predeterminado para BCPBATCH.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-117">A value less than 1 resets BCPBATCH to the default.</span></span>  
  
 <span data-ttu-id="c1bd8-118">BCPDELAYREADFMT</span><span class="sxs-lookup"><span data-stu-id="c1bd8-118">BCPDELAYREADFMT</span></span>  
 <span data-ttu-id="c1bd8-119">Un valor booleano, si se establece en true, hará que [bcp_readfmt](bcp-readfmt.md) lea en la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-119">A Boolean, if set to true, will cause [bcp_readfmt](bcp-readfmt.md) to read at execution.</span></span> <span data-ttu-id="c1bd8-120">Si es false (valor predeterminado), bcp_readfmt leerá inmediatamente el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-120">If false (the default), bcp_readfmt will immediately read the format file.</span></span> <span data-ttu-id="c1bd8-121">Se producirá un error de secuencia si BCPDELAYREADFMT es true y se llama a bcp_columns o bcp_setcolfmt.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-121">A sequence error will occur if BCPDELAYREADFMT is true and you call bcp_columns or bcp_setcolfmt.</span></span>  
  
 <span data-ttu-id="c1bd8-122">También se producirá un error de secuencia si se llama a `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)FALSE)` después de llamar a `bcp_control(hdbc,` BCPDELAYREADFMT `, (void *)TRUE)` y bcp_writefmt.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-122">A sequence error will also occur if you call `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)FALSE)` after calling `bcp_control(hdbc,` BCPDELAYREADFMT`, (void *)TRUE)` and bcp_writefmt.</span></span>  
  
 <span data-ttu-id="c1bd8-123">Para obtener más información, vea [Detección de metadatos](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="c1bd8-123">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
 <span data-ttu-id="c1bd8-124">BCPFILECP</span><span class="sxs-lookup"><span data-stu-id="c1bd8-124">BCPFILECP</span></span>  
 <span data-ttu-id="c1bd8-125">*iValue* contiene el número de la página de códigos para el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-125">*iValue* contains the number of the code page for the data file.</span></span> <span data-ttu-id="c1bd8-126">Puede especificar el número de la página de códigos, como 1252 o 850, o uno de estos valores:</span><span class="sxs-lookup"><span data-stu-id="c1bd8-126">You can specify the number of the code page, such as 1252 or 850, or one of these values:</span></span>  
  
 <span data-ttu-id="c1bd8-127">BCPFILE_ACP: los datos del archivo están en Microsoft Windows?</span><span class="sxs-lookup"><span data-stu-id="c1bd8-127">BCPFILE_ACP: data in the file is in the Microsoft Windows??</span></span> <span data-ttu-id="c1bd8-128">Página de códigos del cliente.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-128">code page of the client.</span></span>  
  
 <span data-ttu-id="c1bd8-129">BCPFILE_OEMCP: los datos del archivo están en la página de códigos OEM del cliente (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="c1bd8-129">BCPFILE_OEMCP: data in the file is in the OEM code page of the client (default).</span></span>  
  
 <span data-ttu-id="c1bd8-130">BCPFILE_RAW: los datos del archivo están en la página de códigos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1bd8-130">BCPFILE_RAW: data in the file is in the code page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c1bd8-131">BCPFILEFMT</span><span class="sxs-lookup"><span data-stu-id="c1bd8-131">BCPFILEFMT</span></span>  
 <span data-ttu-id="c1bd8-132">Número de versión del formato de archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-132">The version number of the data file format.</span></span> <span data-ttu-id="c1bd8-133">Puede ser 80 ( [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] ), 90 ( [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ), 100 ( [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] o [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] ), 110 ( [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ) o 120 ( [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="c1bd8-133">This can be 80 ([!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]), 90 ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]), 100 ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]), 110 ([!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]), or 120 ([!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="c1bd8-134">120 es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-134">120 is the default.</span></span> <span data-ttu-id="c1bd8-135">Esto resulta útil para exportar e importar datos en formatos admitidos en versiones anteriores del servidor.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-135">This is useful for exporting and importing data in formats that were supported by earlier version of the server.</span></span> <span data-ttu-id="c1bd8-136">Por ejemplo, para importar datos obtenidos de una columna de texto en un [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] servidor en una columna **VARCHAR (Max)** en un [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] servidor de o posterior, debe especificar 80.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-136">For example, to import data that was obtained from a text column in a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server into a **varchar(max)** column in a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or later server, you should specify 80.</span></span> <span data-ttu-id="c1bd8-137">Del mismo modo, si se especifica 80 al exportar datos de una columna **VARCHAR (Max)** , se guardarán igual que las columnas de texto se guardan en el [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] formato y se pueden importar en una columna de texto de un [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] servidor.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-137">Similarly, if you specify 80 when exporting data from a **varchar(max)** column, it will be saved just like text columns are saved in the [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] format, and can be imported into a text column of a [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] server.</span></span>  
  
 <span data-ttu-id="c1bd8-138">BCPFIRST</span><span class="sxs-lookup"><span data-stu-id="c1bd8-138">BCPFIRST</span></span>  
 <span data-ttu-id="c1bd8-139">Es la primera fila de datos del archivo o la tabla que va a copiarse.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-139">Is the first row of data to file or table to copy.</span></span> <span data-ttu-id="c1bd8-140">El valor predeterminado es 1; un valor menor que 1 reinicializa esta opción a su valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-140">The default is 1; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="c1bd8-141">BCPFIRSTEX</span><span class="sxs-lookup"><span data-stu-id="c1bd8-141">BCPFIRSTEX</span></span>  
 <span data-ttu-id="c1bd8-142">En operaciones de salida de BCP, especifica la primera fila de la tabla de base de datos que se copia en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-142">For BCP out operations, specifies the first row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="c1bd8-143">En operaciones de entrada de BCP, especifica la primera fila del archivo de datos que se copia en la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-143">For BCP in operations, specifies the first row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="c1bd8-144">Se espera que el parámetro *iValue* sea la dirección de un entero de 64 bits con signo que contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-144">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="c1bd8-145">El valor máximo que puede pasarse a BCPFIRSTEX es 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-145">The maximum value that can be passed to BCPFIRSTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="c1bd8-146">BCPFMTXML</span><span class="sxs-lookup"><span data-stu-id="c1bd8-146">BCPFMTXML</span></span>  
 <span data-ttu-id="c1bd8-147">Especifica que el archivo de formato generado debe estar en formato XML.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-147">Specifies that the format file generated should be in XML format.</span></span> <span data-ttu-id="c1bd8-148">Está desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-148">It is off by default.</span></span>  
  
 <span data-ttu-id="c1bd8-149">Los archivos con formato XML proporcionan mayor flexibilidad, pero con algunas restricciones más.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-149">XML format files provide greater flexibility but with some added constraints.</span></span> <span data-ttu-id="c1bd8-150">Por ejemplo, no es posible especificar el prefijo ni el terminador de un campo de forma simultánea, lo que era posible en archivos de formatos anteriores.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-150">For example, you can not specify the prefix and terminator for a field simultaneously, which was possible in older format files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1bd8-151">Los archivos con formato XML solamente se admiten cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se instala junto con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-151">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed along with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="c1bd8-152">BCPHINTS</span><span class="sxs-lookup"><span data-stu-id="c1bd8-152">BCPHINTS</span></span>  
 <span data-ttu-id="c1bd8-153">*iValue* contiene un puntero de cadena de caracteres SQLTCHAR.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-153">*iValue* contains an SQLTCHAR character string pointer.</span></span> <span data-ttu-id="c1bd8-154">La cadena direccionada especifica sugerencias de procesamiento de copia masiva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o una instrucción Transact-SQL que devuelve un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-154">The string addressed specifies either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bulk-copy processing hints or a Transact-SQL statement that returns a result set.</span></span> <span data-ttu-id="c1bd8-155">Si se especifica una instrucción Transact-SQL que devuelve más de un conjunto de resultados, se omiten todos los conjuntos de resultados posteriores al primero.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-155">If a Transact-SQL statement is specified that returns more than one result set, all result sets after the first are ignored.</span></span> <span data-ttu-id="c1bd8-156">Para obtener más información acerca de las sugerencias de procesamiento de copia masiva, vea [BCP (utilidad](../../tools/bcp-utility.md)).</span><span class="sxs-lookup"><span data-stu-id="c1bd8-156">For more information about bulk-copy processing hints, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
 <span data-ttu-id="c1bd8-157">BCPKEEPIDENTITY</span><span class="sxs-lookup"><span data-stu-id="c1bd8-157">BCPKEEPIDENTITY</span></span>  
 <span data-ttu-id="c1bd8-158">Cuando *iValue* es true, especifica que las funciones de copia masiva insertan valores de datos proporcionados para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] las columnas definidas con una restricción de identidad.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-158">When *iValue* is TRUE, specifies that bulk copy functions insert data values supplied for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns defined with an identity constraint.</span></span> <span data-ttu-id="c1bd8-159">El archivo de entrada debe proporcionar valores para las columnas de identidad.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-159">The input file must supply values for the identity columns.</span></span> <span data-ttu-id="c1bd8-160">Si no se establece, se generan nuevos valores de identidad para las filas insertadas.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-160">If this is not set, new identity values are generated for the inserted rows.</span></span> <span data-ttu-id="c1bd8-161">No se tiene en cuenta ningún dato presente en el archivo para las columnas de identidad.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-161">Any data present in the file for the identity columns is ignored.</span></span>  
  
 <span data-ttu-id="c1bd8-162">BCPKEEPNULLS</span><span class="sxs-lookup"><span data-stu-id="c1bd8-162">BCPKEEPNULLS</span></span>  
 <span data-ttu-id="c1bd8-163">Especifica si los valores de datos vacíos del archivo se convertirán en valores NULL en la tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1bd8-163">Specifies whether empty data values in the file will be converted to NULL values in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="c1bd8-164">Cuando *iValue* es true, los valores vacíos se convertirán en null en la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-164">When *iValue* is TRUE, empty values will be converted to NULL in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="c1bd8-165">Con el valor predeterminado, los valores vacíos se convierten en un valor predeterminado para la columna en la tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si existe un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-165">The default is for empty values to be converted to a default value for the column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table if a default exists.</span></span>  
  
 <span data-ttu-id="c1bd8-166">BCPLAST</span><span class="sxs-lookup"><span data-stu-id="c1bd8-166">BCPLAST</span></span>  
 <span data-ttu-id="c1bd8-167">Es la última fila que va a copiarse.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-167">Is the last row to copy.</span></span> <span data-ttu-id="c1bd8-168">Con el valor predeterminado se copian todas las filas; un valor inferior a 1 restablece esta opción a su valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-168">The default is to copy all rows; a value less than 1 resets this option to its default.</span></span>  
  
 <span data-ttu-id="c1bd8-169">BCPLASTEX</span><span class="sxs-lookup"><span data-stu-id="c1bd8-169">BCPLASTEX</span></span>  
 <span data-ttu-id="c1bd8-170">En operaciones de salida de BCP, especifica la última fila de la tabla de base de datos que se copia en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-170">For BCP out operations, specifies the last row of the database table to copy into the data file.</span></span>  
  
 <span data-ttu-id="c1bd8-171">En operaciones de entrada de BCP, especifica la última fila del archivo de datos que se copia en la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-171">For BCP in operations, specifies the last row of the data file to copy into the database table.</span></span>  
  
 <span data-ttu-id="c1bd8-172">Se espera que el parámetro *iValue* sea la dirección de un entero de 64 bits con signo que contiene el valor.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-172">The *iValue* parameter is expected to be the address of a signed 64-bit integer containing the value.</span></span> <span data-ttu-id="c1bd8-173">El valor máximo que se puede pasar a BCPLASTEX es 2^63-1.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-173">The maximum value that can be passed to BCPLASTEX is 2^63-1.</span></span>  
  
 <span data-ttu-id="c1bd8-174">BCPMAXERRS</span><span class="sxs-lookup"><span data-stu-id="c1bd8-174">BCPMAXERRS</span></span>  
 <span data-ttu-id="c1bd8-175">Es el número de errores permitido antes de que la operación de copia masiva genere un error.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-175">Is the number of errors allowed before the bulk copy operation fails.</span></span> <span data-ttu-id="c1bd8-176">El valor predeterminado es 10; un valor menor que 1 restablece esta opción a su valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-176">The default is 10; a value less than 1 resets this option to its default.</span></span> <span data-ttu-id="c1bd8-177">La copia masiva impone un máximo de 65.535 errores.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-177">Bulk copy imposes a maximum of 65,535 errors.</span></span> <span data-ttu-id="c1bd8-178">Si se intenta establecer esta opción en un valor mayor que 65.535, la opción se establece en 65.535.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-178">An attempt to set this option to a value larger than 65,535 results in the option being set to 65,535.</span></span>  
  
 <span data-ttu-id="c1bd8-179">BCPODBC</span><span class="sxs-lookup"><span data-stu-id="c1bd8-179">BCPODBC</span></span>  
 <span data-ttu-id="c1bd8-180">Si es TRUE, especifica que los valores **DateTime** y **smalldatetime** guardados en formato de caracteres usarán el prefijo y el sufijo de la secuencia de escape de la marca de tiempo de ODBC.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-180">When TRUE, specifies that **datetime** and **smalldatetime** values saved in character format will use the ODBC timestamp escape sequence prefix and suffix.</span></span> <span data-ttu-id="c1bd8-181">La opción BCPODBC solo se aplica a BCP_OUT.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-181">The BCPODBC option only applies to BCP_OUT.</span></span>  
  
 <span data-ttu-id="c1bd8-182">Cuando es FALSE, un valor **DateTime** que representa el 1 de enero de 1997 se convierte en la cadena de caracteres: 1997-01-01 00:00:00.000.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-182">When FALSE, a **datetime** value representing January 1, 1997 is converted to the character string: 1997-01-01 00:00:00.000.</span></span> <span data-ttu-id="c1bd8-183">Si es TRUE, el mismo valor **DateTime** se representa como: {ts ' 1997-01-01 00:00:00.000 '}.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-183">When TRUE, the same **datetime** value is represented as: {ts '1997-01-01 00:00:00.000'}.</span></span>  
  
 <span data-ttu-id="c1bd8-184">BCPROWCOUNT</span><span class="sxs-lookup"><span data-stu-id="c1bd8-184">BCPROWCOUNT</span></span>  
 <span data-ttu-id="c1bd8-185">Devuelve el número de filas afectado por la operación actual (o última) de BCP.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-185">Returns the number of rows affected by the current (or last) BCP operation.</span></span>  
  
 <span data-ttu-id="c1bd8-186">BCPTEXTFILE</span><span class="sxs-lookup"><span data-stu-id="c1bd8-186">BCPTEXTFILE</span></span>  
 <span data-ttu-id="c1bd8-187">Cuando es TRUE, especifica que el archivo de datos es un archivo de texto, en lugar de un archivo binario.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-187">When TRUE, specifies that the data file is a text file, rather than a binary file.</span></span> <span data-ttu-id="c1bd8-188">Si el archivo es un archivo de texto, BCP determina si es Unicode o no comprobando el marcador de bytes Unicode de los dos primeros bytes del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-188">If the file is a text file, BCP determines whether or not it is Unicode by checking the Unicode byte marker in the first two bytes of the data file.</span></span>  
  
 <span data-ttu-id="c1bd8-189">BCPUNICODEFILE</span><span class="sxs-lookup"><span data-stu-id="c1bd8-189">BCPUNICODEFILE</span></span>  
 <span data-ttu-id="c1bd8-190">Cuando es TRUE, especifica que el archivo de entrada es un archivo Unicode.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-190">When TRUE, specifies the input file is a Unicode file.</span></span>  
  
 <span data-ttu-id="c1bd8-191">*iValue*</span><span class="sxs-lookup"><span data-stu-id="c1bd8-191">*iValue*</span></span>  
 <span data-ttu-id="c1bd8-192">Es el valor de la *eOption*especificada.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-192">Is the value for the specified *eOption*.</span></span> <span data-ttu-id="c1bd8-193">*iValue* es un valor entero (LONGLONG) convertido en un puntero void para permitir la ampliación futura a valores de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-193">*iValue* is an integer (LONGLONG) value cast to a void pointer to allow for future expansion to 64 bit values.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c1bd8-194">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="c1bd8-194">Returns</span></span>  
 <span data-ttu-id="c1bd8-195">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-195">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1bd8-196">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c1bd8-196">Remarks</span></span>  
 <span data-ttu-id="c1bd8-197">Esta función establece varios parámetros de control para operaciones de copia masiva, incluido el número de errores permitidos antes de cancelar una copia masiva, los números de la primera y la última fila que van a copiarse de un archivo de datos y el tamaño del lote.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-197">This function sets various control parameters for bulk-copy operations, including the number of errors allowed before canceling a bulk copy, the numbers of the first and last rows to copy from a data file, and the batch size.</span></span>  
  
 <span data-ttu-id="c1bd8-198">Esta función también se utiliza para especificar la instrucción SELECT cuando la copia masiva del conjunto de resultados de una instrucción SELECT no se realiza desde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1bd8-198">This function is also used to specify the SELECT statement when bulk copying out from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] the result set of a SELECT.</span></span> <span data-ttu-id="c1bd8-199">Establezca *eOption* en BCPHINTS y *iValue* para que tenga un puntero a una cadena SQLTCHAR que contenga la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="c1bd8-199">Set *eOption* to BCPHINTS and set *iValue* to have a pointer to an SQLTCHAR string containing the SELECT statement.</span></span>  
  
 <span data-ttu-id="c1bd8-200">Estos parámetros de control solo son significativos cuando la copia se realiza entre un archivo de usuario y una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1bd8-200">These control parameters are only meaningful when copying between a user file and an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="c1bd8-201">La configuración de los parámetros de control no tiene ningún efecto en las filas copiadas en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="c1bd8-201">Control parameter settings have no effect on rows copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1bd8-202">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1bd8-202">Example</span></span>  
  
```  
// Variables like henv not specified.  
SQLHDBC      hdbc;  
DBINT      nRowsProcessed;  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source, return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bulk copy.   
if (bcp_init(hdbc, _T("address"), _T("address.add"), _T("addr.err"),  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the number of rows per batch.   
if (bcp_control(hdbc, BCPBATCH, (void*) 1000) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set file column count.   
if (bcp_columns(hdbc, 1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Set the file format.   
if (bcp_colfmt(hdbc, 1, 0, 0, SQL_VARLEN_DATA, '\n', 1, 1)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
printf_s("%ld rows processed by bulk copy.", nRowsProcessed);  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1bd8-203">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1bd8-203">See Also</span></span>  
 [<span data-ttu-id="c1bd8-204">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="c1bd8-204">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
