---
title: bcp_colfmt | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_colfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_colfmt function
ms.assetid: 5c3b6299-80c7-4e84-8e69-4ff33009548e
author: rothja
ms.author: jroth
ms.openlocfilehash: f646f3aaf9a8f640d829020bd6762c07c406b61f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750914"
---
# <a name="bcp_colfmt"></a><span data-ttu-id="a85ac-102">bcp_colfmt</span><span class="sxs-lookup"><span data-stu-id="a85ac-102">bcp_colfmt</span></span>
  <span data-ttu-id="a85ac-103">Especifica el formato de origen o destino de los datos de un archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="a85ac-103">Specifies the source or target format of the data in a user file.</span></span> <span data-ttu-id="a85ac-104">Cuando se utiliza como formato de origen, **bcp_colfmt** especifica el formato de un archivo de datos existente utilizado como origen de datos de una copia masiva en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a85ac-104">When used as a source format, **bcp_colfmt** specifies the format of an existing data file used as the source of data in a bulk copy to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="a85ac-105">Cuando se utiliza como formato de destino, se crea el archivo de datos utilizando los formatos de columna especificados con **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="a85ac-105">When used as a target format, the data file is created using the column formats specified with **bcp_colfmt**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a85ac-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a85ac-106">Syntax</span></span>  
  
```  
  
RETCODE bcp_colfmt (  
HDBC   
hdbc  
,  
INT  
idxUserDataCol  
,  
BYTE   
eUserDataType  
,  
INT   
cbIndicator  
,  
DBINT   
cbUserData  
,  
LPCBYTE   
pUserDataTerm  
,  
INT   
cbUserDataTerm  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="a85ac-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a85ac-107">Arguments</span></span>  
 <span data-ttu-id="a85ac-108">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="a85ac-108">*hdbc*</span></span>  
 <span data-ttu-id="a85ac-109">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="a85ac-109">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="a85ac-110">*idxUserDataCol*</span><span class="sxs-lookup"><span data-stu-id="a85ac-110">*idxUserDataCol*</span></span>  
 <span data-ttu-id="a85ac-111">Es el número de columna ordinal del archivo de datos de usuario para el que se especifica el formato.</span><span class="sxs-lookup"><span data-stu-id="a85ac-111">Is the ordinal column number in the user data file for which the format is being specified.</span></span> <span data-ttu-id="a85ac-112">La primera columna es 1.</span><span class="sxs-lookup"><span data-stu-id="a85ac-112">The first column is 1.</span></span>  
  
 <span data-ttu-id="a85ac-113">*eUserDataType*</span><span class="sxs-lookup"><span data-stu-id="a85ac-113">*eUserDataType*</span></span>  
 <span data-ttu-id="a85ac-114">Es el tipo de datos de esta columna del archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="a85ac-114">Is the data type of this column in the user file.</span></span> <span data-ttu-id="a85ac-115">Si es distinto del tipo de datos de la columna correspondiente en la tabla de base de datos (*idxServerColumn*), la copia masiva convierte los datos si es posible.</span><span class="sxs-lookup"><span data-stu-id="a85ac-115">If different from the data type of the corresponding column in the database table (*idxServerColumn*), bulk copy converts the data if possible.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="a85ac-116">incorporó la compatibilidad con los tokens de tipo de datos SQLXML y SQLUDT en el parámetro *eUserDataType* .</span><span class="sxs-lookup"><span data-stu-id="a85ac-116">introduced support for SQLXML and SQLUDT data type tokens in the *eUserDataType* parameter.</span></span>  
  
 <span data-ttu-id="a85ac-117">Los tokens de tipo de datos de *en sqlncli.h enumeran el parámetro* eUserDataType [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , no los enumeradores de tipos de datos C de ODBC.</span><span class="sxs-lookup"><span data-stu-id="a85ac-117">The *eUserDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="a85ac-118">Por ejemplo, puede especificar una cadena de caracteres, tipo SQL_C_CHAR de ODBC, utilizando el tipo SQLCHARACTER específico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a85ac-118">For example, you can specify a character string, ODBC type SQL_C_CHAR, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLCHARACTER.</span></span>  
  
 <span data-ttu-id="a85ac-119">Para especificar la representación de datos predeterminada para el tipo de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , establezca este parámetro en 0.</span><span class="sxs-lookup"><span data-stu-id="a85ac-119">To specify the default data representation for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, set this parameter to 0.</span></span>  
  
 <span data-ttu-id="a85ac-120">Para generar una salida de copia masiva de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en un archivo, cuando *eUserDataType* es SQLDECIMAL o SQLNUMERIC:</span><span class="sxs-lookup"><span data-stu-id="a85ac-120">For a bulk copy out of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into a file, when *eUserDataType* is SQLDECIMAL or SQLNUMERIC:</span></span>  
  
-   <span data-ttu-id="a85ac-121">Si la columna de origen no es **decimal** o **numérica**, se utilizan la precisión y la escala predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="a85ac-121">If the source column is not **decimal** or **numeric**, the default precision and scale are used.</span></span>  
  
-   <span data-ttu-id="a85ac-122">Si la columna de origen es **decimal** o **numérica**, se utilizan la precisión y la escala de la columna de origen.</span><span class="sxs-lookup"><span data-stu-id="a85ac-122">If the source column is **decimal** or **numeric**, the precision and scale of the source column are used.</span></span>  
  
 <span data-ttu-id="a85ac-123">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="a85ac-123">*cbIndicator*</span></span>  
 <span data-ttu-id="a85ac-124">Es la longitud, en bytes, de un indicador de longitud o nulo en los datos de columna.</span><span class="sxs-lookup"><span data-stu-id="a85ac-124">Is the length, in bytes, of a length/null indicator within the column data.</span></span> <span data-ttu-id="a85ac-125">Los valores de longitud de indicador válidos son 0 (cuando no se utiliza ningún indicador), 1, 2, 4 u 8.</span><span class="sxs-lookup"><span data-stu-id="a85ac-125">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span>  
  
 <span data-ttu-id="a85ac-126">Para especificar el uso del indicador de copia masiva predeterminado, establezca este parámetro en SQL_VARLEN_DATA.</span><span class="sxs-lookup"><span data-stu-id="a85ac-126">To specify default bulk copy indicator usage, set this parameter to SQL_VARLEN_DATA.</span></span>  
  
 <span data-ttu-id="a85ac-127">Los indicadores aparecen directamente en memoria antes de cualquier dato y en el archivo de datos directamente antes de los datos a los que se aplican.</span><span class="sxs-lookup"><span data-stu-id="a85ac-127">Indicators appear in memory directly before any data, and in the data file directly before the data to which they apply.</span></span>  
  
 <span data-ttu-id="a85ac-128">Si se utiliza más de un medio de especificar una longitud de columna del archivo de datos (como un indicador y una longitud máxima de columna o un indicador y una secuencia de terminador) , la copia masiva elige aquél por el que se copia la cantidad mínima de datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-128">If more than one means of specifying a data file column length is used (such as an indicator and a maximum column length, or an indicator and a terminator sequence), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="a85ac-129">Los archivos de datos generados mediante la copia masiva cuando ninguna intervención de usuario ajusta el formato de los datos contienen indicadores acerca de cuándo los datos de columna pueden variar en longitud o cuándo la columna puede aceptar como valores los valores NULL.</span><span class="sxs-lookup"><span data-stu-id="a85ac-129">Data files generated by bulk copy when no user intervention adjusts the format of the data contain indicators when the column data can vary in length or the column can accept NULL as a value.</span></span>  
  
 <span data-ttu-id="a85ac-130">*cbUserData*</span><span class="sxs-lookup"><span data-stu-id="a85ac-130">*cbUserData*</span></span>  
 <span data-ttu-id="a85ac-131">Es la longitud máxima, en bytes, de los datos de esta columna del archivo de usuario, sin incluir la longitud de los indicadores de longitud o de los terminadores.</span><span class="sxs-lookup"><span data-stu-id="a85ac-131">Is the maximum length, in bytes, of this column's data in the user file, not including the length of any length indicator or terminator.</span></span>  
  
 <span data-ttu-id="a85ac-132">Establecer *cbUserData* en SQL_NULL_DATA indica que todos los valores de columna del archivo de datos son NULL o deben establecerse en NULL.</span><span class="sxs-lookup"><span data-stu-id="a85ac-132">Setting *cbUserData* to SQL_NULL_DATA indicates that all values in the data file column are, or should be set to NULL.</span></span>  
  
 <span data-ttu-id="a85ac-133">Establecer *cbUserData* en SQL_VARLEN_DATA indica que el sistema debe determinar la longitud de datos de cada columna.</span><span class="sxs-lookup"><span data-stu-id="a85ac-133">Setting *cbUserData* to SQL_VARLEN_DATA indicates that the system should determine the length of data in each column.</span></span> <span data-ttu-id="a85ac-134">Para algunas columnas, esto podría significar que se genera un indicador de longitud/nulo para preceder los datos en una copia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]o que se espera el indicador en los datos copiados en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a85ac-134">For some columns, this could mean that a length/null indicator is generated to precede data on a copy from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or that the indicator is expected in data copied to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="a85ac-135">Para los tipos de datos de caracteres y binarios de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , *cbUserData* puede ser SQL_VARLEN_DATA, SQL_NULL_DATA, 0 o algún valor positivo.</span><span class="sxs-lookup"><span data-stu-id="a85ac-135">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbUserData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, 0, or some positive value.</span></span> <span data-ttu-id="a85ac-136">Si *cbUserData* es SQL_VARLEN_DATA, el sistema utiliza un indicador de longitud, si lo hay, o una secuencia de terminador para determinar la longitud de los datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-136">If *cbUserData* is SQL_VARLEN_DATA, the system uses either the length indicator, if present, or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="a85ac-137">Si se proporciona un indicador de longitud y una secuencia de terminador, la copia masiva usa aquél por el que se copia la mínima cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-137">If both a length indicator and a terminator sequence are supplied, bulk copy uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="a85ac-138">Si *cbUserData* es SQL_VARLEN_DATA, el tipo de datos es un tipo de carácter o binario de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y no se especifica ni un indicador de longitud ni una secuencia de terminador, el sistema devuelve un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="a85ac-138">If *cbUserData* is SQL_VARLEN_DATA, the data type is an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="a85ac-139">Si *cbUserData* es 0 o un valor positivo, el sistema utiliza *cbUserData* como longitud de datos máxima.</span><span class="sxs-lookup"><span data-stu-id="a85ac-139">If *cbUserData* is 0 or a positive value, the system uses *cbUserData* as the maximum data length.</span></span> <span data-ttu-id="a85ac-140">Sin embargo, si además de un valor de *cbUserData*positivo, se proporciona un indicador de longitud o una secuencia de terminador, el sistema determina la longitud de los datos utilizando el método por el que se copia la cantidad mínima de datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-140">However, if, in addition to a positive *cbUserData*, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="a85ac-141">El valor de *cbUserData* representa el recuento de bytes de datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-141">The *cbUserData* value represents the count of bytes of data.</span></span> <span data-ttu-id="a85ac-142">Si los datos de caracteres se representan mediante caracteres anchos de Unicode, un valor del parámetro *cbUserData* positivo representa el número de caracteres multiplicado por el tamaño, en bytes, de cada carácter.</span><span class="sxs-lookup"><span data-stu-id="a85ac-142">If character data is represented by Unicode wide characters, then a positive *cbUserData* parameter value represents the number of characters multiplied by the size, in bytes, of each character.</span></span>  
  
 <span data-ttu-id="a85ac-143">*pUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="a85ac-143">*pUserDataTerm*</span></span>  
 <span data-ttu-id="a85ac-144">Es la secuencia de terminador que se va a utilizar para esta columna.</span><span class="sxs-lookup"><span data-stu-id="a85ac-144">Is the terminator sequence to be used for this column.</span></span> <span data-ttu-id="a85ac-145">Este parámetro es principalmente útil para los tipos de datos de caracteres porque todos los demás tipos son de longitud fija o, en el caso de los datos binarios, requieren un indicador de longitud que grabe con precisión el número de bytes presentes.</span><span class="sxs-lookup"><span data-stu-id="a85ac-145">This parameter is useful mainly for character data types because all other types are of fixed length or, in the case of binary data, require an indicator of length to accurately record the number of bytes present.</span></span>  
  
 <span data-ttu-id="a85ac-146">Para evitar la terminación de los datos extraídos o indicar que no se terminen los datos de un archivo de usuario, establezca este parámetro en NULL.</span><span class="sxs-lookup"><span data-stu-id="a85ac-146">To avoid terminating extracted data, or to indicate that data in a user file is not terminated, set this parameter to NULL.</span></span>  
  
 <span data-ttu-id="a85ac-147">Si se usa más de un medio para especificar una longitud de columna de usuario (como un terminador y un indicador de longitud, o un terminador y una longitud máxima de columna), la copia masiva elige aquél por el que se copia la cantidad mínima de datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-147">If more than one means of specifying a user-file column length is used (such as a terminator and a length indicator, or a terminator and a maximum column length), bulk copy chooses the one that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="a85ac-148">La API de copia masiva realiza la conversión de caracteres Unicode a MBCS según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a85ac-148">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="a85ac-149">Se deben extremar las precauciones para asegurarse de que se establece correctamente la cadena de bytes del terminador y la longitud de la cadena de bytes.</span><span class="sxs-lookup"><span data-stu-id="a85ac-149">Care must be taken to ensure that both the terminator byte string and the length of the byte string are set correctly.</span></span>  
  
 <span data-ttu-id="a85ac-150">*cbUserDataTerm*</span><span class="sxs-lookup"><span data-stu-id="a85ac-150">*cbUserDataTerm*</span></span>  
 <span data-ttu-id="a85ac-151">Es la longitud, en bytes, de la secuencia de terminador que se va a utilizar para esta columna.</span><span class="sxs-lookup"><span data-stu-id="a85ac-151">Is the length, in bytes, of the terminator sequence to be used for this column.</span></span> <span data-ttu-id="a85ac-152">Si no hay ningún terminador presente o no se desea uno en los datos, establezca este valor en 0.</span><span class="sxs-lookup"><span data-stu-id="a85ac-152">If no terminator is present or desired in the data, set this value to 0.</span></span>  
  
 <span data-ttu-id="a85ac-153">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="a85ac-153">*idxServerCol*</span></span>  
 <span data-ttu-id="a85ac-154">Es la posición ordinal de la columna de la tabla de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-154">Is the ordinal position of the column in the database table.</span></span> <span data-ttu-id="a85ac-155">El primer número de columna es 1.</span><span class="sxs-lookup"><span data-stu-id="a85ac-155">The first column number is 1.</span></span> <span data-ttu-id="a85ac-156">La posición ordinal de una columna se notifica mediante [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="a85ac-156">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
 <span data-ttu-id="a85ac-157">Si este valor es 0, la copia masiva omite la columna en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-157">If this value is 0, bulk copy ignores the column in the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="a85ac-158">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="a85ac-158">Returns</span></span>  
 <span data-ttu-id="a85ac-159">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="a85ac-159">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a85ac-160">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a85ac-160">Remarks</span></span>  
 <span data-ttu-id="a85ac-161">La función **bcp_colfmt** permite especificar el formato de archivo de usuario para las copias masivas.</span><span class="sxs-lookup"><span data-stu-id="a85ac-161">The **bcp_colfmt** function allows you to specify the user-file format for bulk copies.</span></span> <span data-ttu-id="a85ac-162">Para la copia masiva, un formato contiene los componentes siguientes:</span><span class="sxs-lookup"><span data-stu-id="a85ac-162">For bulk copy, a format contains the following parts:</span></span>  
  
-   <span data-ttu-id="a85ac-163">Una asignación de las columnas de archivo de usuario a las columnas de base de datos.</span><span class="sxs-lookup"><span data-stu-id="a85ac-163">A mapping from user-file columns to database columns.</span></span>  
  
-   <span data-ttu-id="a85ac-164">El tipo de datos de cada columna del archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="a85ac-164">The data type of each user-file column.</span></span>  
  
-   <span data-ttu-id="a85ac-165">La longitud del indicador opcional para cada columna.</span><span class="sxs-lookup"><span data-stu-id="a85ac-165">The length of the optional indicator for each column.</span></span>  
  
-   <span data-ttu-id="a85ac-166">La longitud máxima de los datos por columna de archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="a85ac-166">The maximum length of data per user-file column.</span></span>  
  
-   <span data-ttu-id="a85ac-167">Secuencia de bytes de terminación opcional para cada columna.</span><span class="sxs-lookup"><span data-stu-id="a85ac-167">The optional terminating byte sequence for each column.</span></span>  
  
-   <span data-ttu-id="a85ac-168">La longitud de la secuencia de bytes de terminación opcional.</span><span class="sxs-lookup"><span data-stu-id="a85ac-168">The length of the optional terminating byte sequence.</span></span>  
  
 <span data-ttu-id="a85ac-169">Cada llamada a **bcp_colfmt** especifica el formato de una columna de archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="a85ac-169">Each call to **bcp_colfmt** specifies the format for one user-file column.</span></span> <span data-ttu-id="a85ac-170">Por ejemplo, para cambiar la configuración predeterminada de tres columnas de un archivo de datos de usuario de cinco columnas, primero llame a [bcp_columns](bcp-columns.md)**(5)** y, a continuación, llame a **bcp_colfmt** cinco veces, estableciendo con tres de esas llamadas el formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="a85ac-170">For example, to change the default settings for three columns in a five-column user data file, first call [bcp_columns](bcp-columns.md)**(5)**, and then call **bcp_colfmt** five times, with three of those calls setting your custom format.</span></span> <span data-ttu-id="a85ac-171">Para las dos llamadas restantes, establezca *eUserDataType* en 0 y establezca *cbIndicator*, *cbUserData*y *cbUserDataTerm* en 0, SQL_VARLEN_DATA y 0, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a85ac-171">For the remaining two calls, set *eUserDataType* to 0, and set *cbIndicator*, *cbUserData*, and *cbUserDataTerm* to 0, SQL_VARLEN_DATA, and 0 respectively.</span></span> <span data-ttu-id="a85ac-172">Este procedimiento copia las cinco columnas, tres con el formato personalizado y dos con el formato predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a85ac-172">This procedure copies all five columns, three with your customized format and two with the default format.</span></span>  
  
 <span data-ttu-id="a85ac-173">Para *cbIndicator*, un valor de 8 para indicar un tipo de valor grande es válido ahora.</span><span class="sxs-lookup"><span data-stu-id="a85ac-173">For *cbIndicator*, a value of 8 to indicate a large value type is now valid.</span></span> <span data-ttu-id="a85ac-174">Si se especifica el prefijo para un campo cuya columna correspondiente es un nuevo tipo max, solamente se puede establecer en 8.</span><span class="sxs-lookup"><span data-stu-id="a85ac-174">If the prefix is specified for a field whose corresponding column is a new max type, it can only be set to 8.</span></span> <span data-ttu-id="a85ac-175">Para obtener más información, consulte [bcp_bind](bcp-bind.md).</span><span class="sxs-lookup"><span data-stu-id="a85ac-175">For details, see [bcp_bind](bcp-bind.md).</span></span>  
  
 <span data-ttu-id="a85ac-176">Se debe llamar a la función **bcp_columns** antes de realizar cualquier llamada a **bcp_colfmt**.</span><span class="sxs-lookup"><span data-stu-id="a85ac-176">The **bcp_columns** function must be called before any calls to **bcp_colfmt**.</span></span>  
  
 <span data-ttu-id="a85ac-177">Debe llamar a **bcp_colfmt** una vez por cada columna del archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="a85ac-177">You must call **bcp_colfmt** once for each column in the user file.</span></span>  
  
 <span data-ttu-id="a85ac-178">La llamada a **bcp_colfmt** más de una vez para cualquier columna de archivo de usuario produce un error.</span><span class="sxs-lookup"><span data-stu-id="a85ac-178">Calling **bcp_colfmt** more than once for any user-file column causes an error.</span></span>  
  
 <span data-ttu-id="a85ac-179">No tiene que copiar todos los datos de un archivo de usuario en la tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a85ac-179">You do not need to copy all data in a user file to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="a85ac-180">Para omitir una columna, especifique el formato de los datos de la columna; para ello, establezca el parámetro *idxServerCol* en 0.</span><span class="sxs-lookup"><span data-stu-id="a85ac-180">To skip a column, specify the format of the data for the column, setting the *idxServerCol* parameter to 0.</span></span> <span data-ttu-id="a85ac-181">Si desea omitir una columna, debe especificar su tipo.</span><span class="sxs-lookup"><span data-stu-id="a85ac-181">If you want to skip a column, you must specify its type.</span></span>  
  
 <span data-ttu-id="a85ac-182">La función [bcp_writefmt](bcp-writefmt.md) se puede utilizar para conservar la especificación de formato.</span><span class="sxs-lookup"><span data-stu-id="a85ac-182">The [bcp_writefmt](bcp-writefmt.md) function can be used to persist the format specification.</span></span>  
  
## <a name="bcp_colfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="a85ac-183">Compatibilidad de bcp_colfmt con las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="a85ac-183">bcp_colfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="a85ac-184">Para obtener información acerca de los tipos utilizados con el parámetro *eUserDataType* para los tipos de fecha y hora, vea [cambios de copia masiva para tipos de fecha y hora mejorados &#40;OLE DB y&#41;de ODBC ](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a85ac-184">For information aboutt he types used with the *eUserDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="a85ac-185">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a85ac-185">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a85ac-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a85ac-186">See Also</span></span>  
 [<span data-ttu-id="a85ac-187">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="a85ac-187">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
