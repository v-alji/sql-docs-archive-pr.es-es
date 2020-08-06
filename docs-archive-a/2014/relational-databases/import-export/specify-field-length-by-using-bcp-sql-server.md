---
title: Especificar la longitud de campo mediante bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- default field lengths
- field length [SQL Server]
- data formats [SQL Server], field length
- bcp utility [SQL Server], field length
ms.assetid: 240f33ca-ef4a-413a-a4de-831885cb505b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 13343b4f3778df1bbe7ef1c99b3d06338f18631c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744699"
---
# <a name="specify-field-length-by-using-bcp-sql-server"></a><span data-ttu-id="7a7b2-102">Especificar la longitud de campo mediante bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7a7b2-102">Specify Field Length by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="7a7b2-103">La longitud de campo indica el número máximo de caracteres necesarios para representar los datos en formato de carácter.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-103">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="7a7b2-104">La longitud de campo se conoce si los datos están almacenados en formato nativo; por ejemplo, el tipo de datos `int` ocupa 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-104">The field length is already known if the data is stored in the native format; for example, the `int` data type takes 4 bytes.</span></span> <span data-ttu-id="7a7b2-105">Si ha indicado 0 para la longitud del prefijo, el comando **BCP** le solicitará la longitud del campo, las longitudes de campo predeterminadas y el impacto de la longitud de campo en el almacenamiento de datos en los archivos de datos que contienen `char` datos.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-105">If you have indicated 0 for the prefix length, the **bcp** command prompts you for field length, the default field lengths, and the impact of field-length on data storage in data files that contain `char` data.</span></span>  
  
## <a name="the-bcp-prompt-for-field-length"></a><span data-ttu-id="7a7b2-106">Solicitud bcp para la longitud de campo</span><span class="sxs-lookup"><span data-stu-id="7a7b2-106">The bcp Prompt for Field Length</span></span>  
 <span data-ttu-id="7a7b2-107">Si un comando **bcp** interactivo contiene la opción **in** o **out** sin el modificador de archivo de formato ( **-f**) o un modificador de formato de datos ( **-n**, **-c**, **-w** o **-N**), el comando solicita la longitud de campo de cada campo, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a7b2-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the field length of each data field, as follows:</span></span>  
  
 `Enter length of field <field_name> [<default>]:`  
  
 <span data-ttu-id="7a7b2-108">Para obtener un ejemplo que muestra esta solicitud en contexto, vea [Especificar formatos de datos por razones de compatibilidad mediante bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a7b2-108">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a7b2-109">Después de que se especifiquen de forma interactiva todos los campos de un comando **bcp**, el comando solicita que guarde sus respuestas para cada campo en un archivo que no tenga el formato XML.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-109">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="7a7b2-110">Para obtener más información sobre los archivos con formato distinto de XML, vea [Archivos de formato no XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7a7b2-110">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 <span data-ttu-id="7a7b2-111">Que un comando **bcp** solicite la longitud de campo depende de varios factores, entre ellos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7a7b2-111">Whether a **bcp** command prompts for field length depends on several factors, as follows:</span></span>  
  
-   <span data-ttu-id="7a7b2-112">Cuando se copian tipos de datos que no son de longitud fija y se especifica una longitud de prefijo 0, **bcp** solicita una longitud de campo.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-112">When you copy data types that are not of fixed length and you specify a prefix length of 0, **bcp** prompts for a field length.</span></span>  
  
-   <span data-ttu-id="7a7b2-113">Cuando se convierten datos que no son de caracteres al formato de datos de caracteres, **bcp** recomienda una longitud de campo predeterminada lo suficientemente grande como para almacenar los datos.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-113">When converting noncharacter data to character data, **bcp** suggests a default field length large enough to store the data.</span></span>  
  
-   <span data-ttu-id="7a7b2-114">Si se almacenan tipos de archivos que no son de caracteres, el comando **bcp** no solicita una longitud de campo.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-114">If the file storage type is noncharacter, the **bcp** command does not prompt for a field length.</span></span> <span data-ttu-id="7a7b2-115">Los datos se almacenan en la representación de datos nativa de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (formato nativo).</span><span class="sxs-lookup"><span data-stu-id="7a7b2-115">The data is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data representation (native format).</span></span>  
  
## <a name="using-default-field-lengths"></a><span data-ttu-id="7a7b2-116">Usar longitudes de campo predeterminadas</span><span class="sxs-lookup"><span data-stu-id="7a7b2-116">Using Default Field Lengths</span></span>  
 <span data-ttu-id="7a7b2-117">Por lo general, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recomienda aceptar los valores predeterminados que sugiere **bcp**para la longitud de campo.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-117">Generally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you accept the **bcp**-suggested default values for the field length.</span></span> <span data-ttu-id="7a7b2-118">Cuando se crea un archivo de datos en modo de carácter, si especifica la longitud de campo predeterminada, los datos no se truncan ni se producirán errores de desbordamiento numérico.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-118">When a character mode data file is created, using the default field length ensures that data is not truncated and that numeric overflow errors do not occur.</span></span>  
  
 <span data-ttu-id="7a7b2-119">Si especifica una longitud de campo incorrecta, pueden producirse problemas.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-119">If you specify a field length that is incorrect, problems can occur.</span></span> <span data-ttu-id="7a7b2-120">Por ejemplo, si copia datos numéricos y especifica una longitud de campo demasiado corta para los datos, la utilidad **bcp** imprime un mensaje de desbordamiento y no copia los datos.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-120">For instance, if you copy numeric data and you specify a field length that is too short for the data, the **bcp** utility prints an overflow message and does not copy the data.</span></span> <span data-ttu-id="7a7b2-121">Además, si exporta `datetime` datos y especifica una longitud de campo inferior a 26 bytes para la cadena de caracteres, la utilidad **BCP** trunca los datos sin un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-121">Also, if you export `datetime` data and specify a field length of less than 26 bytes for the character string, the **bcp** utility truncates the data without an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7a7b2-122">Cuando se utiliza la opción de tamaño predeterminado, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] espera leer una cadena entera.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-122">When the default size option is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expects to read an entire string.</span></span> <span data-ttu-id="7a7b2-123">En algunos casos, el uso de la longitud de campo predeterminada puede provocar un error del tipo "fin de archivo inesperado".</span><span class="sxs-lookup"><span data-stu-id="7a7b2-123">In some situations, use of a default field length can lead to an "unexpected end of file" error.</span></span> <span data-ttu-id="7a7b2-124">Normalmente, este error se produce con `money` los `datetime` tipos de datos y cuando solo parte del campo esperado tiene lugar en el archivo de datos; por ejemplo, cuando `datetime` se especifica un valor de *mm* / *DD* / *AA* sin el componente de hora y, por tanto, es menor que la longitud de 24 caracteres esperada de un `datetime` valor en `char` formato.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-124">Typically, this error occurs with the `money` and `datetime` data types when only part of the expected field occurs in the data file; for example, when a `datetime` value of *mm*/*dd*/*yy* is specified without the time component and is, therefore, shorter than the expected 24 character length of a `datetime` value in `char` format.</span></span> <span data-ttu-id="7a7b2-125">Para evitar este tipo de error, puede utilizar terminadores de campo o campos de datos de longitud fija o cambiar la longitud de campo predeterminada especificando otro valor.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-125">To avoid this type of error, use field terminators or fixed-length data fields, or change the default field length by specifying another value.</span></span>  
  
### <a name="default-field-lengths-for-character-file-storage"></a><span data-ttu-id="7a7b2-126">Longitudes de campo predeterminadas para el almacenamiento de archivos de caracteres</span><span class="sxs-lookup"><span data-stu-id="7a7b2-126">Default Field Lengths for Character File Storage</span></span>  
 <span data-ttu-id="7a7b2-127">En la siguiente tabla se enumeran las longitudes de campo predeterminadas de los datos que se almacenan como tipo de almacenamiento de archivo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-127">The following table lists the default field lengths for data to be stored as a character-file storage type.</span></span> <span data-ttu-id="7a7b2-128">Los datos que aceptan valores NULL tienen la misma longitud que los datos que no aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-128">Nullable data is the same length as nonnull data.</span></span>  
  
|<span data-ttu-id="7a7b2-129">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7a7b2-129">Data type</span></span>|<span data-ttu-id="7a7b2-130">Longitud predeterminada (caracteres)</span><span class="sxs-lookup"><span data-stu-id="7a7b2-130">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`char`|<span data-ttu-id="7a7b2-131">Longitud definida para la columna</span><span class="sxs-lookup"><span data-stu-id="7a7b2-131">Length defined for the column</span></span>|  
|`varchar`|<span data-ttu-id="7a7b2-132">Longitud definida para la columna</span><span class="sxs-lookup"><span data-stu-id="7a7b2-132">Length defined for the column</span></span>|  
|`nchar`|<span data-ttu-id="7a7b2-133">Dos veces la longitud definida para la columna</span><span class="sxs-lookup"><span data-stu-id="7a7b2-133">Twice the length defined for the column</span></span>|  
|`nvarchar`|<span data-ttu-id="7a7b2-134">Dos veces la longitud definida para la columna</span><span class="sxs-lookup"><span data-stu-id="7a7b2-134">Twice the length defined for the column</span></span>|  
|`Text`|<span data-ttu-id="7a7b2-135">0</span><span class="sxs-lookup"><span data-stu-id="7a7b2-135">0</span></span>|  
|`ntext`|<span data-ttu-id="7a7b2-136">0</span><span class="sxs-lookup"><span data-stu-id="7a7b2-136">0</span></span>|  
|`bit`|<span data-ttu-id="7a7b2-137">1</span><span class="sxs-lookup"><span data-stu-id="7a7b2-137">1</span></span>|  
|`binary`|<span data-ttu-id="7a7b2-138">Dos veces la longitud definida para la columna + 1</span><span class="sxs-lookup"><span data-stu-id="7a7b2-138">Twice the length defined for the column + 1</span></span>|  
|`varbinary`|<span data-ttu-id="7a7b2-139">Dos veces la longitud definida para la columna + 1</span><span class="sxs-lookup"><span data-stu-id="7a7b2-139">Twice the length defined for the column + 1</span></span>|  
|`image`|<span data-ttu-id="7a7b2-140">0</span><span class="sxs-lookup"><span data-stu-id="7a7b2-140">0</span></span>|  
|`datetime`|<span data-ttu-id="7a7b2-141">24</span><span class="sxs-lookup"><span data-stu-id="7a7b2-141">24</span></span>|  
|`smalldatetime`|<span data-ttu-id="7a7b2-142">24</span><span class="sxs-lookup"><span data-stu-id="7a7b2-142">24</span></span>|  
|`float`|<span data-ttu-id="7a7b2-143">30</span><span class="sxs-lookup"><span data-stu-id="7a7b2-143">30</span></span>|  
|`real`|<span data-ttu-id="7a7b2-144">30</span><span class="sxs-lookup"><span data-stu-id="7a7b2-144">30</span></span>|  
|`int`|<span data-ttu-id="7a7b2-145">12</span><span class="sxs-lookup"><span data-stu-id="7a7b2-145">12</span></span>|  
|`bigint`|<span data-ttu-id="7a7b2-146">19</span><span class="sxs-lookup"><span data-stu-id="7a7b2-146">19</span></span>|  
|`smallint`|<span data-ttu-id="7a7b2-147">7</span><span class="sxs-lookup"><span data-stu-id="7a7b2-147">7</span></span>|  
|`tinyint`|<span data-ttu-id="7a7b2-148">5</span><span class="sxs-lookup"><span data-stu-id="7a7b2-148">5</span></span>|  
|`money`|<span data-ttu-id="7a7b2-149">30</span><span class="sxs-lookup"><span data-stu-id="7a7b2-149">30</span></span>|  
|`smallmoney`|<span data-ttu-id="7a7b2-150">30</span><span class="sxs-lookup"><span data-stu-id="7a7b2-150">30</span></span>|  
|`decimal`|<span data-ttu-id="7a7b2-151">41\*</span><span class="sxs-lookup"><span data-stu-id="7a7b2-151">41\*</span></span>|  
|`numeric`|<span data-ttu-id="7a7b2-152">41\*</span><span class="sxs-lookup"><span data-stu-id="7a7b2-152">41\*</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="7a7b2-153">37</span><span class="sxs-lookup"><span data-stu-id="7a7b2-153">37</span></span>|  
|`timestamp`|<span data-ttu-id="7a7b2-154">17</span><span class="sxs-lookup"><span data-stu-id="7a7b2-154">17</span></span>|  
|`varchar(max)`|<span data-ttu-id="7a7b2-155">0</span><span class="sxs-lookup"><span data-stu-id="7a7b2-155">0</span></span>|  
|`varbinary(max)`|<span data-ttu-id="7a7b2-156">0</span><span class="sxs-lookup"><span data-stu-id="7a7b2-156">0</span></span>|  
|`nvarchar(max)`|<span data-ttu-id="7a7b2-157">0</span><span class="sxs-lookup"><span data-stu-id="7a7b2-157">0</span></span>|  
|<span data-ttu-id="7a7b2-158">UDT</span><span class="sxs-lookup"><span data-stu-id="7a7b2-158">UDT</span></span>|<span data-ttu-id="7a7b2-159">Longitud de la columna del término definido por el usuario (UDT)</span><span class="sxs-lookup"><span data-stu-id="7a7b2-159">Length of the user-defined term (UDT) column</span></span>|  
|<span data-ttu-id="7a7b2-160">XML</span><span class="sxs-lookup"><span data-stu-id="7a7b2-160">XML</span></span>|<span data-ttu-id="7a7b2-161">0</span><span class="sxs-lookup"><span data-stu-id="7a7b2-161">0</span></span>|  
  
 <span data-ttu-id="7a7b2-162">\*Para obtener más información sobre `decimal` los `numeric` tipos de datos y, vea [decimal y Numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a7b2-162">\*For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a7b2-163">Una columna de tipo `tinyint` puede contener valores entre 0 y 255; el número máximo de caracteres necesarios para representar cualquier número de este intervalo es tres (que representa valores entre 100 y 255).</span><span class="sxs-lookup"><span data-stu-id="7a7b2-163">A column of type `tinyint` can have values from 0 through 255; the maximum number of characters that are needed to represent any number in that range is three (representing values 100 through 255).</span></span>  
  
### <a name="default-field-lengths-for-native-file-storage"></a><span data-ttu-id="7a7b2-164">Longitudes de campo predeterminadas para el almacenamiento de archivos nativos</span><span class="sxs-lookup"><span data-stu-id="7a7b2-164">Default Field Lengths for Native File Storage</span></span>  
 <span data-ttu-id="7a7b2-165">En la siguiente tabla se enumeran las longitudes de campo predeterminadas de los datos que se almacenan como tipo de almacenamiento de archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-165">The following table lists the default field lengths for data to be stored as native file storage type.</span></span> <span data-ttu-id="7a7b2-166">Los datos que aceptan valores NULL tienen la misma longitud que los datos que no aceptan valores NULL, y los datos de caracteres siempre se almacenan en formato de caracteres.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-166">Nullable data is the same length as nonnull data, and character data is always stored in character format.</span></span>  
  
|<span data-ttu-id="7a7b2-167">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7a7b2-167">Data type</span></span>|<span data-ttu-id="7a7b2-168">Longitud predeterminada (caracteres)</span><span class="sxs-lookup"><span data-stu-id="7a7b2-168">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`bit`|<span data-ttu-id="7a7b2-169">1</span><span class="sxs-lookup"><span data-stu-id="7a7b2-169">1</span></span>|  
|`binary`|<span data-ttu-id="7a7b2-170">Longitud definida para la columna</span><span class="sxs-lookup"><span data-stu-id="7a7b2-170">Length defined for the column</span></span>|  
|`varbinary`|<span data-ttu-id="7a7b2-171">Longitud definida para la columna</span><span class="sxs-lookup"><span data-stu-id="7a7b2-171">Length defined for the column</span></span>|  
|`image`|<span data-ttu-id="7a7b2-172">0</span><span class="sxs-lookup"><span data-stu-id="7a7b2-172">0</span></span>|  
|`datetime`|<span data-ttu-id="7a7b2-173">8</span><span class="sxs-lookup"><span data-stu-id="7a7b2-173">8</span></span>|  
|`smalldatetime`|<span data-ttu-id="7a7b2-174">4</span><span class="sxs-lookup"><span data-stu-id="7a7b2-174">4</span></span>|  
|`float`|<span data-ttu-id="7a7b2-175">8</span><span class="sxs-lookup"><span data-stu-id="7a7b2-175">8</span></span>|  
|`real`|<span data-ttu-id="7a7b2-176">4</span><span class="sxs-lookup"><span data-stu-id="7a7b2-176">4</span></span>|  
|`int`|<span data-ttu-id="7a7b2-177">4</span><span class="sxs-lookup"><span data-stu-id="7a7b2-177">4</span></span>|  
|`bigint`|<span data-ttu-id="7a7b2-178">8</span><span class="sxs-lookup"><span data-stu-id="7a7b2-178">8</span></span>|  
|`smallint`|<span data-ttu-id="7a7b2-179">2</span><span class="sxs-lookup"><span data-stu-id="7a7b2-179">2</span></span>|  
|`tinyint`|<span data-ttu-id="7a7b2-180">1</span><span class="sxs-lookup"><span data-stu-id="7a7b2-180">1</span></span>|  
|`money`|<span data-ttu-id="7a7b2-181">8</span><span class="sxs-lookup"><span data-stu-id="7a7b2-181">8</span></span>|  
|`smallmoney`|<span data-ttu-id="7a7b2-182">4</span><span class="sxs-lookup"><span data-stu-id="7a7b2-182">4</span></span>|  
|<span data-ttu-id="7a7b2-183">`decimal`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a7b2-183">`decimal` <sup>1</sup></span></span>|<sup>*</sup>|  
|<span data-ttu-id="7a7b2-184">`numeric`<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a7b2-184">`numeric` <sup>1</sup></span></span>|<sup>*</sup>|  
|`uniqueidentifier`|<span data-ttu-id="7a7b2-185">16</span><span class="sxs-lookup"><span data-stu-id="7a7b2-185">16</span></span>|  
|`timestamp`|<span data-ttu-id="7a7b2-186">8</span><span class="sxs-lookup"><span data-stu-id="7a7b2-186">8</span></span>|  
  
 <span data-ttu-id="7a7b2-187"><sup>1</sup> para obtener más información sobre `decimal` los `numeric` tipos de datos y, vea [decimal y numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7a7b2-187"><sup>1</sup> For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
 <span data-ttu-id="7a7b2-188">En todos los casos anteriores, si desea crear un archivo de datos para recargarlo posteriormente en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y mantener el espacio de almacenamiento mínimo, use un prefijo de longitud con el tipo de almacenamiento en archivo y la longitud de campo predeterminados.</span><span class="sxs-lookup"><span data-stu-id="7a7b2-188">In all of the preceding cases, to create a data file for later reloading into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that keeps the storage space to a minimum, use a length prefix with the default file storage type and the default field length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7b2-189">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a7b2-189">See Also</span></span>  
 <span data-ttu-id="7a7b2-190">[bcp (utilidad)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="7a7b2-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="7a7b2-191">[Tipos de datos &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a7b2-191">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="7a7b2-192">[Especificar terminadores de campo y de fila &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a7b2-192">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 <span data-ttu-id="7a7b2-193">[Especificar la longitud de prefijo en los archivos de datos mediante bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a7b2-193">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="7a7b2-194">[Especificar el tipo de almacenamiento en archivo mediante bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a7b2-194">[Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="7a7b2-195">Mantener valores NULL o usar valores predeterminados durante la importación en bloque &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7a7b2-195">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
  
