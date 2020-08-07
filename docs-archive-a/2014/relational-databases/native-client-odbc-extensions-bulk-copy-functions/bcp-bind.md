---
title: bcp_bind | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_bind
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_bind function
ms.assetid: 6e335a5c-64b2-4bcf-a88f-35dc9393f329
author: rothja
ms.author: jroth
ms.openlocfilehash: db0a58398bf47bd0bb96bd1ef587d41890ed8461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745284"
---
# <a name="bcp_bind"></a><span data-ttu-id="2f39f-102">bcp_bind</span><span class="sxs-lookup"><span data-stu-id="2f39f-102">bcp_bind</span></span>
  <span data-ttu-id="2f39f-103">Enlaza los datos de una variable de programa a una columna de tabla para la copia masiva en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f39f-103">Binds data from a program variable to a table column for bulk copy into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f39f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f39f-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_bind (  
HDBC   
hdbc  
,   
LPCBYTE   
pData  
,  
INT   
cbIndicator  
,  
DBINT   
cbData  
,  
LPCBYTE   
pTerm  
,  
INT   
cbTerm  
,  
INT   
eDataType  
,  
INT   
idxServerCol  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="2f39f-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2f39f-105">Arguments</span></span>  
 <span data-ttu-id="2f39f-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="2f39f-106">*hdbc*</span></span>  
 <span data-ttu-id="2f39f-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="2f39f-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="2f39f-108">*pData*</span><span class="sxs-lookup"><span data-stu-id="2f39f-108">*pData*</span></span>  
 <span data-ttu-id="2f39f-109">Es un puntero a los datos copiados.</span><span class="sxs-lookup"><span data-stu-id="2f39f-109">Is a pointer to the data copied.</span></span> <span data-ttu-id="2f39f-110">Si *eDataType* es SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR o SQLIMAGE, *PDATA* puede ser null.</span><span class="sxs-lookup"><span data-stu-id="2f39f-110">If *eDataType* is SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR or SQLIMAGE, *pData* can be NULL.</span></span> <span data-ttu-id="2f39f-111">Un *PDATA* null indica que los valores de datos largos se enviarán a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en fragmentos mediante [bcp_moretext](bcp-moretext.md).</span><span class="sxs-lookup"><span data-stu-id="2f39f-111">A NULL *pData* indicates that long data values will be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in chunks using [bcp_moretext](bcp-moretext.md).</span></span> <span data-ttu-id="2f39f-112">El usuario solo debe establecer *pdata* en NULL si la columna correspondiente al campo enlazado al usuario es una columna BLOB; de lo contrario **bcp_bind** producirá un error.</span><span class="sxs-lookup"><span data-stu-id="2f39f-112">The user should only set *pData* to NULL if the column corresponding to the user bound field is a BLOB column otherwise **bcp_bind** will fail.</span></span>  
  
 <span data-ttu-id="2f39f-113">Si en los datos hay indicadores, estos aparecen en la memoria directamente antes de los datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-113">If indicators are present in the data, they appear in memory directly before the data.</span></span> <span data-ttu-id="2f39f-114">El parámetro *pdata* apunta a la variable de indicador en este caso y el ancho del indicador, el parámetro *cbIndicator* , se usa en la copia masiva para direccionar los datos del usuario correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f39f-114">The *pData* parameter points to the indicator variable in this case, and the width of the indicator, the *cbIndicator* parameter, is used by bulk copy to address user data correctly.</span></span>  
  
 <span data-ttu-id="2f39f-115">*cbIndicator*</span><span class="sxs-lookup"><span data-stu-id="2f39f-115">*cbIndicator*</span></span>  
 <span data-ttu-id="2f39f-116">Es la longitud, en bytes, de un indicador de longitud o nulo para los datos de la columna.</span><span class="sxs-lookup"><span data-stu-id="2f39f-116">Is the length, in bytes, of a length or null indicator for the column's data.</span></span> <span data-ttu-id="2f39f-117">Los valores de longitud de indicador válidos son 0 (cuando no se utiliza ningún indicador), 1, 2, 4 u 8.</span><span class="sxs-lookup"><span data-stu-id="2f39f-117">Valid indicator length values are 0 (when using no indicator), 1, 2, 4, or 8.</span></span> <span data-ttu-id="2f39f-118">Los indicadores aparecen en la memoria directamente antes de ningún dato.</span><span class="sxs-lookup"><span data-stu-id="2f39f-118">Indicators appear in memory directly before any data.</span></span> <span data-ttu-id="2f39f-119">Por ejemplo, la siguiente definición de tipo de estructura se puede utilizar para insertar valores enteros en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizando la copia masiva:</span><span class="sxs-lookup"><span data-stu-id="2f39f-119">For example, the following structure type definition could be used to insert integer values into an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table using bulk copy:</span></span>  
  
```  
typedef struct tagBCPBOUNDINT  
    {  
    int iIndicator;  
    int Value;  
    } BCPBOUNDINT;  
```  
  
 <span data-ttu-id="2f39f-120">En el caso de ejemplo, el parámetro *pdata* se establecería en la dirección de una instancia declarada de la estructura, la dirección del miembro de la estructura BCPBOUNDINT *iIndicator* .</span><span class="sxs-lookup"><span data-stu-id="2f39f-120">In the example case, the *pData* parameter would be set to the address of a declared instance of the structure, the address of the BCPBOUNDINT *iIndicator* structure member.</span></span> <span data-ttu-id="2f39f-121">El parámetro *cbIndicator* se establecería en el tamaño de un entero (sizeof (int)) y el parámetro *cbData* se establecería de nuevo en el tamaño de un entero (sizeof (int)).</span><span class="sxs-lookup"><span data-stu-id="2f39f-121">The *cbIndicator* parameter would be set to the size of an integer (sizeof(int)), and the *cbData* parameter would again be set to the size of an integer (sizeof(int)).</span></span> <span data-ttu-id="2f39f-122">Para copiar de forma masiva una fila en el servidor que contiene un valor NULL para la columna enlazada, el valor del miembro *iIndicator* de la instancia debe establecerse en SQL_NULL_DATA.</span><span class="sxs-lookup"><span data-stu-id="2f39f-122">To bulk copy a row to the server containing a NULL value for the bound column, the value of the instance's *iIndicator* member should be set to SQL_NULL_DATA.</span></span>  
  
 <span data-ttu-id="2f39f-123">*cbData*</span><span class="sxs-lookup"><span data-stu-id="2f39f-123">*cbData*</span></span>  
 <span data-ttu-id="2f39f-124">Es el número de bytes de datos de la variable de programa, sin incluir la longitud de ningún terminador o indicador de longitud o nulo.</span><span class="sxs-lookup"><span data-stu-id="2f39f-124">Is the count of bytes of data in the program variable, not including the length of any length or null indicator or terminator.</span></span>  
  
 <span data-ttu-id="2f39f-125">Establecer *cbData* en SQL_NULL_DATA significa que todas las filas copiadas en el servidor contienen un valor null para la columna.</span><span class="sxs-lookup"><span data-stu-id="2f39f-125">Setting *cbData* to SQL_NULL_DATA signifies that all rows copied to the server contain a NULL value for the column.</span></span>  
  
 <span data-ttu-id="2f39f-126">Al establecer *cbData* en SQL_VARLEN_DATA, se indica que el sistema usará un terminador de cadena u otro método para determinar la longitud de los datos copiados.</span><span class="sxs-lookup"><span data-stu-id="2f39f-126">Setting *cbData* to SQL_VARLEN_DATA indicates that the system will use a string terminator, or other method, to determine the length of data copied.</span></span>  
  
 <span data-ttu-id="2f39f-127">En el caso de los tipos de datos de longitud fija, como los enteros, el tipo de datos indica la longitud de los datos al sistema.</span><span class="sxs-lookup"><span data-stu-id="2f39f-127">For fixed-length data types, such as integers, the data type indicates the length of the data to the system.</span></span> <span data-ttu-id="2f39f-128">Por lo tanto, en el caso de los tipos de datos de longitud fija, *cbData* se puede SQL_VARLEN_DATA o la longitud de los datos de forma segura.</span><span class="sxs-lookup"><span data-stu-id="2f39f-128">Therefore, for fixed-length data types, *cbData* can safely be SQL_VARLEN_DATA or the length of the data.</span></span>  
  
 <span data-ttu-id="2f39f-129">En el caso de los [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de datos de caracteres y binarios, *cbData* puede ser SQL_VARLEN_DATA, SQL_NULL_DATA, algún valor positivo o 0.</span><span class="sxs-lookup"><span data-stu-id="2f39f-129">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character and binary data types, *cbData* can be SQL_VARLEN_DATA, SQL_NULL_DATA, some positive value, or 0.</span></span> <span data-ttu-id="2f39f-130">Si *cbData* es SQL_VARLEN_DATA, el sistema utiliza un indicador de longitud o null (si existe) o una secuencia de terminador para determinar la longitud de los datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-130">If *cbData* is SQL_VARLEN_DATA, the system uses either a length/null indicator (if present) or a terminator sequence to determine the length of the data.</span></span> <span data-ttu-id="2f39f-131">Si se proporciona ambos, el sistema utiliza el que hace que se copie una menor cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-131">If both are supplied, the system uses the one that results in the least amount of data being copied.</span></span> <span data-ttu-id="2f39f-132">Si *cbData* es SQL_VARLEN_DATA, el tipo de datos de la columna es un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo de carácter o binario y no se especifica un indicador de longitud ni una secuencia de terminador, el sistema devuelve un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="2f39f-132">If *cbData* is SQL_VARLEN_DATA, the data type of the column is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] character or binary type, and neither a length indicator nor a terminator sequence is specified, the system returns an error message.</span></span>  
  
 <span data-ttu-id="2f39f-133">Si *cbData* es 0 o un valor positivo, el sistema utiliza *cbData* como la longitud de los datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-133">If *cbData* is 0 or a positive value, the system uses *cbData* as the data length.</span></span> <span data-ttu-id="2f39f-134">Sin embargo, si, además de un valor de *cbData* positivo, se proporciona un indicador de longitud o una secuencia de terminador, el sistema determina la longitud de los datos mediante el método que hace que se copie la menor cantidad de datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-134">However, if, in addition to a positive *cbData* value, a length indicator or terminator sequence is provided, the system determines the data length by using the method that results in the least amount of data being copied.</span></span>  
  
 <span data-ttu-id="2f39f-135">El valor del parámetro *cbData* representa el recuento de bytes de datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-135">The *cbData* parameter value represents the count of bytes of data.</span></span> <span data-ttu-id="2f39f-136">Si los datos de caracteres se representan mediante caracteres anchos de Unicode, un valor de parámetro *cbData* positivo representa el número de caracteres multiplicado por el tamaño en bytes de cada carácter.</span><span class="sxs-lookup"><span data-stu-id="2f39f-136">If character data is represented by Unicode wide characters, then a positive *cbData* parameter value represents the number of characters multiplied by the size in bytes of each character.</span></span>  
  
 <span data-ttu-id="2f39f-137">*pTerm*</span><span class="sxs-lookup"><span data-stu-id="2f39f-137">*pTerm*</span></span>  
 <span data-ttu-id="2f39f-138">Es un puntero al modelo de bytes que marca el fin de esta variable de programa, en caso de haberlo.</span><span class="sxs-lookup"><span data-stu-id="2f39f-138">Is a pointer to the byte pattern, if any, that marks the end of this program variable.</span></span> <span data-ttu-id="2f39f-139">Por ejemplo, las cadenas ANSI y MBCS de C suelen tener un terminador de 1 byte (\0).</span><span class="sxs-lookup"><span data-stu-id="2f39f-139">For example, ANSI and MBCS C strings usually have a 1-byte terminator (\0).</span></span>  
  
 <span data-ttu-id="2f39f-140">Si no hay ningún terminador para la variable, establezca *pTerm* en NULL.</span><span class="sxs-lookup"><span data-stu-id="2f39f-140">If there is no terminator for the variable, set *pTerm* to NULL.</span></span>  
  
 <span data-ttu-id="2f39f-141">Puede utilizar una cadena vacía ("") para designar el terminador nulo de C como el terminador de la variable de programa.</span><span class="sxs-lookup"><span data-stu-id="2f39f-141">You can use an empty string ("") to designate the C null terminator as the program-variable terminator.</span></span> <span data-ttu-id="2f39f-142">Dado que la cadena vacía terminada en NULL constituye un solo byte (el propio byte de terminador), establezca *cbTerm* en 1.</span><span class="sxs-lookup"><span data-stu-id="2f39f-142">Because the null-terminated empty string constitutes a single byte (the terminator byte itself), set *cbTerm* to 1.</span></span> <span data-ttu-id="2f39f-143">Por ejemplo, para indicar que la cadena en *szName* está terminada en NULL y que se debe usar el terminador para indicar la longitud:</span><span class="sxs-lookup"><span data-stu-id="2f39f-143">For example, to indicate that the string in *szName* is null-terminated and that the terminator should be used to indicate the length:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,  
   SQL_VARLEN_DATA, "", 1,  
   SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="2f39f-144">Un formulario no terminado de este ejemplo podría indicar que se copian 15 caracteres de la variable *szName* a la segunda columna de la tabla enlazada:</span><span class="sxs-lookup"><span data-stu-id="2f39f-144">A nonterminated form of this example could indicate that 15 characters be copied from the *szName* variable to the second column of the bound table:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0, 15,   
   NULL, 0, SQLCHARACTER, 2)  
```  
  
 <span data-ttu-id="2f39f-145">La API de copia masiva realiza la conversión de caracteres Unicode a MBCS según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2f39f-145">The bulk copy API performs Unicode-to-MBCS character conversion as required.</span></span> <span data-ttu-id="2f39f-146">Asegúrese de que tanto la cadena de bytes de terminador como la longitud de la cadena de bytes están correctamente establecidas.</span><span class="sxs-lookup"><span data-stu-id="2f39f-146">Make sure that both the terminator byte string and the length of the byte string are set correctly.</span></span> <span data-ttu-id="2f39f-147">Por ejemplo, para indicar que la cadena en *szName* es una cadena de caracteres anchos de Unicode, terminada por el valor de terminador null de Unicode:</span><span class="sxs-lookup"><span data-stu-id="2f39f-147">For example, to indicate that the string in *szName* is a Unicode wide character string, terminated by the Unicode null terminator value:</span></span>  
  
```  
bcp_bind(hdbc, szName, 0,   
   SQL_VARLEN_DATA, L"",  
   sizeof(WCHAR), SQLNCHAR, 2)  
```  
  
 <span data-ttu-id="2f39f-148">Si la columna enlazada [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es un carácter ancho, no se realiza ninguna conversión en [bcp_sendrow](bcp-sendrow.md).</span><span class="sxs-lookup"><span data-stu-id="2f39f-148">If the bound [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is wide character, no conversion is performed on [bcp_sendrow](bcp-sendrow.md).</span></span> <span data-ttu-id="2f39f-149">Si el tipo de caracteres de la columna de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es MBCS, la conversión de caracteres anchos a caracteres multibyte se realiza cuando los datos se envían a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f39f-149">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column is an MBCS character type, wide character to multibyte character conversion is performed as the data is sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2f39f-150">*cbTerm*</span><span class="sxs-lookup"><span data-stu-id="2f39f-150">*cbTerm*</span></span>  
 <span data-ttu-id="2f39f-151">Es el número de bytes que hay en el terminador para la variable de programa, si existe.</span><span class="sxs-lookup"><span data-stu-id="2f39f-151">Is the count of bytes present in the terminator for the program variable, if any.</span></span> <span data-ttu-id="2f39f-152">Si no hay ningún terminador para la variable, establezca *cbTerm* en 0.</span><span class="sxs-lookup"><span data-stu-id="2f39f-152">If there is no terminator for the variable, set *cbTerm* to 0.</span></span>  
  
 <span data-ttu-id="2f39f-153">*eDataType*</span><span class="sxs-lookup"><span data-stu-id="2f39f-153">*eDataType*</span></span>  
 <span data-ttu-id="2f39f-154">Es el tipo de datos de C de la variable de programa.</span><span class="sxs-lookup"><span data-stu-id="2f39f-154">Is the C data type of the program variable.</span></span> <span data-ttu-id="2f39f-155">Los datos de la variable de programa se convierten al tipo de la columna de base de datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-155">The data in the program variable is converted to the type of the database column.</span></span> <span data-ttu-id="2f39f-156">Si este parámetro es 0, no se realiza ninguna conversión.</span><span class="sxs-lookup"><span data-stu-id="2f39f-156">If this parameter is 0, no conversion is performed.</span></span>  
  
 <span data-ttu-id="2f39f-157">Los *eDataType* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tokens de tipo de datos enumeran el parámetro eDataType en SQLNCLI. h, no los enumeradores de tipos de datos C de ODBC.</span><span class="sxs-lookup"><span data-stu-id="2f39f-157">The *eDataType* parameter is enumerated by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type tokens in sqlncli.h, not the ODBC C data type enumerators.</span></span> <span data-ttu-id="2f39f-158">Por ejemplo, puede especificar un entero de dos bytes, el tipo ODBC SQL_C_SHORT, utilizando el tipo SQLINT2 específico de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f39f-158">For example, you can specify a two-byte integer, ODBC type SQL_C_SHORT, using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific type SQLINT2.</span></span>  
  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]<span data-ttu-id="2f39f-159">incorporó la compatibilidad con los tokens de tipo de datos SQLXML y SQLUDT del *`eDataType`* .</span><span class="sxs-lookup"><span data-stu-id="2f39f-159">introduced support for SQLXML and SQLUDT data type tokens in the *`eDataType`* paramenter.</span></span>  
  
 <span data-ttu-id="2f39f-160">*idxServerCol*</span><span class="sxs-lookup"><span data-stu-id="2f39f-160">*idxServerCol*</span></span>  
 <span data-ttu-id="2f39f-161">Es la posición ordinal de la columna en la tabla de base de datos en la que se copian los datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-161">Is the ordinal position of the column in the database table to which the data is copied.</span></span> <span data-ttu-id="2f39f-162">La primera columna de una tabla es la columna 1.</span><span class="sxs-lookup"><span data-stu-id="2f39f-162">The first column in a table is column 1.</span></span> <span data-ttu-id="2f39f-163">La posición ordinal de una columna se notifica mediante [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="2f39f-163">The ordinal position of a column is reported by [SQLColumns](../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="returns"></a><span data-ttu-id="2f39f-164">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="2f39f-164">Returns</span></span>  
 <span data-ttu-id="2f39f-165">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="2f39f-165">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f39f-166">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2f39f-166">Remarks</span></span>  
 <span data-ttu-id="2f39f-167">Utilice **bcp_bind** para una manera rápida y eficaz de copiar datos de una variable de programa en una tabla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f39f-167">Use **bcp_bind** for a fast, efficient way to copy data from a program variable into a table in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="2f39f-168">Llame a [bcp_init](bcp-init.md) antes de llamar a esta o a cualquier otra función de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="2f39f-168">Call [bcp_init](bcp-init.md) before calling this or any other bulk-copy function.</span></span> <span data-ttu-id="2f39f-169">Al llamar a **bcp_init** se establece la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla de destino para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="2f39f-169">Calling **bcp_init** sets the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] target table for bulk copy.</span></span> <span data-ttu-id="2f39f-170">Cuando se llama a **bcp_init** para su uso con **bcp_bind** y [bcp_sendrow](bcp-sendrow.md), el parámetro **bcp_init** _szDataFile_ , que indica el archivo de datos, se establece en null; el parámetro **bcp_init**_eDirection_ se establece en DB_IN.</span><span class="sxs-lookup"><span data-stu-id="2f39f-170">When calling **bcp_init** for use with **bcp_bind** and [bcp_sendrow](bcp-sendrow.md), the **bcp_init** _szDataFile_ parameter, indicating the data file, is set to NULL; the **bcp_init**_eDirection_ parameter is set to DB_IN.</span></span>  
  
 <span data-ttu-id="2f39f-171">Realice una llamada de **bcp_bind** independiente para cada columna de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabla en la que desea copiar.</span><span class="sxs-lookup"><span data-stu-id="2f39f-171">Make a separate **bcp_bind** call for every column in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into which you want to copy.</span></span> <span data-ttu-id="2f39f-172">Una vez realizadas las llamadas de **bcp_bind** necesarias, llame a **bcp_sendrow** para enviar una fila de datos de las variables de programa a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f39f-172">After the necessary **bcp_bind** calls have been made, then call **bcp_sendrow** to send a row of data from your program variables to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2f39f-173">No se permite volver a enlazar una columna.</span><span class="sxs-lookup"><span data-stu-id="2f39f-173">Rebinding a column is not supported.</span></span>  
  
 <span data-ttu-id="2f39f-174">Siempre que desee [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] confirmar las filas ya recibidas, llame a [bcp_batch](bcp-batch.md).</span><span class="sxs-lookup"><span data-stu-id="2f39f-174">Whenever you want [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to commit the rows already received, call [bcp_batch](bcp-batch.md).</span></span> <span data-ttu-id="2f39f-175">Por ejemplo, llame a **bcp_batch** una vez por cada 1000 filas insertadas o en cualquier otro intervalo.</span><span class="sxs-lookup"><span data-stu-id="2f39f-175">For example, call **bcp_batch** once for every 1000 rows inserted or at any other interval.</span></span>  
  
 <span data-ttu-id="2f39f-176">Cuando no haya más filas para insertar, llame a [bcp_done](bcp-done.md).</span><span class="sxs-lookup"><span data-stu-id="2f39f-176">When there are no more rows to be inserted, call [bcp_done](bcp-done.md).</span></span> <span data-ttu-id="2f39f-177">Si no lo hace, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="2f39f-177">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="2f39f-178">La configuración de los parámetros de control, especificada con [bcp_control](bcp-control.md), no tiene ningún efecto en **bcp_bind** transferencias de filas.</span><span class="sxs-lookup"><span data-stu-id="2f39f-178">Control parameter settings, specified with [bcp_control](bcp-control.md), have no effect on **bcp_bind** row transfers.</span></span>  
  
 <span data-ttu-id="2f39f-179">Si *pdata* para una columna se establece en NULL porque su valor se proporcionará mediante llamadas a [bcp_moretext](bcp-moretext.md), las columnas subsiguientes con *EDATATYPE* establecido en SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR o SQLIMAGE también se deben enlazar con *pdata* establecido en null, y sus valores también se deben proporcionar mediante llamadas a `bcp_moretext` .</span><span class="sxs-lookup"><span data-stu-id="2f39f-179">If *pData* for a column is set to NULL because its value will be supplied by calls to [bcp_moretext](bcp-moretext.md), any subsequent columns with *eDataType* set to SQLTEXT, SQLNTEXT, SQLXML, SQLUDT, SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, SQLNCHAR, or SQLIMAGE must also be bound with *pData* set to NULL, and their values must also be supplied by calls to `bcp_moretext`.</span></span>  
  
 <span data-ttu-id="2f39f-180">En el caso de los nuevos tipos de valores grandes, como `varchar(max)` , `varbinary(max)` o `nvarchar(max)` , puede usar SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY y SQLNCHAR como indicadores de tipo en el parámetro *eDataType* .</span><span class="sxs-lookup"><span data-stu-id="2f39f-180">For new large value types, such as `varchar(max)`, `varbinary(max)`, or `nvarchar(max)`, you can use SQLCHARACTER, SQLVARCHAR, SQLVARBINARY, SQLBINARY, and SQLNCHAR as type indicators in the *eDataType* parameter.</span></span>  
  
 <span data-ttu-id="2f39f-181">Si *cbTerm* no es 0, los valores (1, 2, 4 u 8) son válidos para el prefijo (*cbIndicator*).</span><span class="sxs-lookup"><span data-stu-id="2f39f-181">If *cbTerm* is not 0, any value (1, 2, 4, or 8) is valid for the prefix (*cbIndicator*).</span></span> <span data-ttu-id="2f39f-182">En esta situación, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client buscará el terminador, calculará la longitud de los datos con respecto al terminador (*i*) y establecerá el valor de *cbData* en el valor más pequeño de i y el valor de prefijo.</span><span class="sxs-lookup"><span data-stu-id="2f39f-182">In this situation, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client will search for the terminator, calculate data length with respect to the terminator (*i*), and set the *cbData* to the smaller value of i and the value of prefix.</span></span>  
  
 <span data-ttu-id="2f39f-183">Si *cbTerm* es 0 y *cbIndicator* (el prefijo) no es 0, *cbIndicator* debe ser 8.</span><span class="sxs-lookup"><span data-stu-id="2f39f-183">If *cbTerm* is 0 and *cbIndicator* (the prefix) is not 0, *cbIndicator* must be 8.</span></span> <span data-ttu-id="2f39f-184">El prefijo de 8 bytes puede tomar los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2f39f-184">The 8 byte prefix can take the following values:</span></span>  
  
-   <span data-ttu-id="2f39f-185">0xFFFFFFFFFFFFFFFF significa un valor nulo para el campo.</span><span class="sxs-lookup"><span data-stu-id="2f39f-185">0xFFFFFFFFFFFFFFFF means a null value for the field</span></span>  
  
-   <span data-ttu-id="2f39f-186">0xFFFFFFFFFFFFFFFE se trata como un valor de prefijo especial que se utiliza para enviar los datos en fragmentos al servidor de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="2f39f-186">0xFFFFFFFFFFFFFFFE is treated as a special prefix value which is used for efficiently sending data in chunks to the server.</span></span> <span data-ttu-id="2f39f-187">El formato de los datos con este prefijo especial es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f39f-187">The format of data with this special prefix is:</span></span>  
  
-   <span data-ttu-id="2f39f-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> donde:</span><span class="sxs-lookup"><span data-stu-id="2f39f-188"><SPECIAL_PREFIX> \<0 or more  DATA CHUNKS> <ZERO_CHUNK> where:</span></span>  
  
-   <span data-ttu-id="2f39f-189">PREFIJO_ESPECIAL es 0xFFFFFFFFFFFFFFFE</span><span class="sxs-lookup"><span data-stu-id="2f39f-189">SPECIAL_PREFIX is 0xFFFFFFFFFFFFFFFE</span></span>  
  
-   <span data-ttu-id="2f39f-190">FRAGMENTO_DATOS es un prefijo de 4 bytes que contiene la longitud del fragmento, seguido por los datos reales cuya longitud se especifica en el prefijo de 4 bytes.</span><span class="sxs-lookup"><span data-stu-id="2f39f-190">DATA_CHUNK is a 4 byte prefix containing length of the chunk,followed by the actual data whose length is specified in the 4 byte prefix.</span></span>  
  
-   <span data-ttu-id="2f39f-191">FRAGMENTO_CERO es un valor de 4 bytes que contiene todos los ceros (00000000) que indican el fin de los datos.</span><span class="sxs-lookup"><span data-stu-id="2f39f-191">ZERO_CHUNK is a 4 byte value containing all zeros (00000000) indicating the end of data.</span></span>  
  
-   <span data-ttu-id="2f39f-192">Cualquier otra longitud válida de 8 bytes se tratará como una longitud de datos normal.</span><span class="sxs-lookup"><span data-stu-id="2f39f-192">Any other valid 8 byte length is treated as a regular data length.</span></span>  
  
 <span data-ttu-id="2f39f-193">La llamada a [bcp_columns](bcp-columns.md) cuando se usa **bcp_bind** produce un error.</span><span class="sxs-lookup"><span data-stu-id="2f39f-193">Calling [bcp_columns](bcp-columns.md) when using **bcp_bind** results in an error.</span></span>  
  
## <a name="bcp_bind-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="2f39f-194">Compatibilidad de bcp_bind con las características mejoradas de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="2f39f-194">bcp_bind Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="2f39f-195">Para obtener información sobre los tipos utilizados con el parámetro *eDataType* para los tipos de fecha y hora, vea [cambios de copia masiva para tipos de fecha y hora mejorados &#40;OLE DB y ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2f39f-195">For information about the types used with the *eDataType* parameter for date/time types, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="2f39f-196">Para obtener más información, vea [mejoras de fecha y hora &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="2f39f-196">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f39f-197">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f39f-197">Example</span></span>  
  
```  
#include sql.h  
#include sqlext.h  
#include odbcss.h  
// Variables like henv not specified.  
HDBC      hdbc;  
char         szCompanyName[MAXNAME];  
DBINT      idCompany;  
DBINT      nRowsProcessed;  
DBBOOL      bMoreData;  
char*      pTerm = "\t\t";  
  
// Application initiation, get an ODBC environment handle, allocate the  
// hdbc, and so on.  
...   
  
// Enable bulk copy prior to connecting on allocated hdbc.  
SQLSetConnectAttr(hdbc, SQL_COPT_SS_BCP, (SQLPOINTER) SQL_BCP_ON,  
   SQL_IS_INTEGER);  
  
// Connect to the data source; return on error.  
if (!SQL_SUCCEEDED(SQLConnect(hdbc, _T("myDSN"), SQL_NTS,  
   _T("myUser"), SQL_NTS, _T("myPwd"), SQL_NTS)))  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Initialize bcp.   
if (bcp_init(hdbc, "comdb..accounts_info", NULL, NULL  
   DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idCompany, 0, sizeof(DBINT), NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_bind(hdbc, (LPCBYTE) szCompanyName, 0, SQL_VARLEN_DATA,  
   (LPCBYTE) pTerm, strnlen(pTerm, sizeof(pTerm)), SQLCHARACTER, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
while (TRUE)  
   {  
   // Retrieve and process program data.   
   if ((bMoreData = getdata(&idCompany, szCompanyName)) == TRUE)  
      {  
      // Send the data.   
      if (bcp_sendrow(hdbc) == FAIL)  
         {  
         // Raise error and return.  
         return;  
         }  
      }  
   else  
      {  
      // Break out of loop.  
      break;  
      }  
   }  
  
// Terminate the bulk copy operation.  
if ((nRowsProcessed = bcp_done(hdbc)) == -1)  
   {  
   printf_s("Bulk-copy unsuccessful.\n");  
   return;  
   }  
  
printf_s("%ld rows copied.\n", nRowsProcessed);  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f39f-198">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f39f-198">See Also</span></span>  
 [<span data-ttu-id="2f39f-199">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="2f39f-199">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
