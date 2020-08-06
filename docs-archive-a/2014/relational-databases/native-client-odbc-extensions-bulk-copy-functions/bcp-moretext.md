---
title: bcp_moretext | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_moretext
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_moretext function
ms.assetid: 23e98015-a8e4-4434-9b3f-9c7350cf965f
author: rothja
ms.author: jroth
ms.openlocfilehash: 00c0eb1c8739e94380b12034cebc70d8e22b79c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671052"
---
# <a name="bcp_moretext"></a><span data-ttu-id="40178-102">bcp_moretext</span><span class="sxs-lookup"><span data-stu-id="40178-102">bcp_moretext</span></span>
  <span data-ttu-id="40178-103">Envía parte de un valor de tipo de datos largo, de longitud variable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40178-103">Sends part of a long, variable-length data type value to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40178-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40178-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_moretext (  
HDBC   
hdbc  
,  
DBINT   
cbData  
,  
LPCBYTE   
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="40178-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="40178-105">Arguments</span></span>  
 <span data-ttu-id="40178-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="40178-106">*hdbc*</span></span>  
 <span data-ttu-id="40178-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="40178-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="40178-108">*cbData*</span><span class="sxs-lookup"><span data-stu-id="40178-108">*cbData*</span></span>  
 <span data-ttu-id="40178-109">Es el número de bytes de datos que se copian en SQL Server a partir de los datos a los que se hace referencia en *pdata*.</span><span class="sxs-lookup"><span data-stu-id="40178-109">Is the number of bytes of data being copied to SQL Server from the data referenced by *pData*.</span></span> <span data-ttu-id="40178-110">Un valor de SQL_NULL_DATA indica NULL.</span><span class="sxs-lookup"><span data-stu-id="40178-110">A value of SQL_NULL_DATA indicates NULL.</span></span>  
  
 <span data-ttu-id="40178-111">*pData*</span><span class="sxs-lookup"><span data-stu-id="40178-111">*pData*</span></span>  
 <span data-ttu-id="40178-112">Es un puntero al fragmento de datos compatible, largo y de longitud variable que se va a enviar a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40178-112">Is a pointer to the supported, long, variable-length data chunk to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="returns"></a><span data-ttu-id="40178-113">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="40178-113">Returns</span></span>  
 <span data-ttu-id="40178-114">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="40178-114">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40178-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="40178-115">Remarks</span></span>  
 <span data-ttu-id="40178-116">Esta función se puede usar junto con [bcp_bind](bcp-bind.md) y [bcp_sendrow](bcp-sendrow.md) para copiar valores de datos largos y de longitud variable en SQL Server en varios fragmentos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="40178-116">This function can be used in conjunction with [bcp_bind](bcp-bind.md) and [bcp_sendrow](bcp-sendrow.md) to copy long, variable-length data values to SQL Server in a number of smaller chunks.</span></span> <span data-ttu-id="40178-117">**bcp_moretext** se puede utilizar con columnas que tienen los siguientes tipos de datos SQL Server: `text` , `ntext` , `image` , `varchar(max)` , `nvarchar(max)` , `varbinary(max)` , tipo definido por el usuario (UDT) y XML.</span><span class="sxs-lookup"><span data-stu-id="40178-117">**bcp_moretext** can be used with columns that have the following SQL Server data types: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, user-defined type (UDT), and XML.</span></span> <span data-ttu-id="40178-118">**bcp_moretext** no admite conversiones de datos, los datos proporcionados deben coincidir con el tipo de datos de la columna de destino.</span><span class="sxs-lookup"><span data-stu-id="40178-118">**bcp_moretext** does not support data conversions, the data supplied must match the data type of the target column.</span></span>  
  
 <span data-ttu-id="40178-119">Si se llama a **bcp_bind** con un parámetro *pdata* no NULL para los tipos de datos admitidos por **bcp_moretext**, `bcp_sendrow` envía todo el valor de datos, independientemente de su longitud.</span><span class="sxs-lookup"><span data-stu-id="40178-119">If **bcp_bind** is called with a nonNULL *pData* parameter for data types that are supported by **bcp_moretext**, `bcp_sendrow` sends the entire data value, regardless of length.</span></span> <span data-ttu-id="40178-120">Sin embargo, si **bcp_bind** tiene un parámetro *pdata* null para los tipos de datos admitidos, **bcp_moretext** se puede usar para copiar los datos inmediatamente después de que se devuelva correctamente, `bcp_sendrow` lo que indica que se han procesado todas las columnas enlazadas con datos presentes.</span><span class="sxs-lookup"><span data-stu-id="40178-120">If, however, **bcp_bind** has a NULL *pData* parameter for supported data types, **bcp_moretext** can be used to copy data immediately after a successful return from `bcp_sendrow` indicating that any bound columns with data present have been processed.</span></span>  
  
 <span data-ttu-id="40178-121">Si usa **bcp_moretext** para enviar una columna de tipo de datos compatible en una fila, también debe utilizarla para enviar todas las demás columnas de tipos de datos compatibles de la fila.</span><span class="sxs-lookup"><span data-stu-id="40178-121">If you use **bcp_moretext** to send one supported data type column in a row, you must also use it to send all other supported data type columns in the row.</span></span> <span data-ttu-id="40178-122">No se puede omitir ninguna columna.</span><span class="sxs-lookup"><span data-stu-id="40178-122">No columns may be skipped.</span></span> <span data-ttu-id="40178-123">Los tipos de datos admitidos son SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT y SQLXML.</span><span class="sxs-lookup"><span data-stu-id="40178-123">Supported data types are SQLTEXT, SQLNTEXT, SQLIMAGE, SQLUDT and SQLXML.</span></span> <span data-ttu-id="40178-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY y SQLVARBINARY también pertenecen a esta categoría si la columna es de tipo varchar (max), nvarchar (max) o varbinary (max), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="40178-124">SQLCHARACTER, SQLVARCHAR, SQNCHAR, SQLBINARY and SQLVARBINARY also fall into this category if the column is a varchar(max), nvarchar(max) or varbinary(max), respectively.</span></span>  
  
 <span data-ttu-id="40178-125">Al llamar a **bcp_bind** o [bcp_collen](bcp-collen.md) se establece la longitud total de todas las partes de datos que se van a copiar en la columna SQL Server.</span><span class="sxs-lookup"><span data-stu-id="40178-125">Calling either **bcp_bind** or [bcp_collen](bcp-collen.md) sets the total length of all data parts to be copied to the SQL Server column.</span></span> <span data-ttu-id="40178-126">Un intento de enviar SQL Server más bytes de los especificados en la llamada a **bcp_bind** o `bcp_collen` genera un error.</span><span class="sxs-lookup"><span data-stu-id="40178-126">An attempt to send SQL Server more bytes than specified in the call to **bcp_bind** or `bcp_collen` generates an error.</span></span> <span data-ttu-id="40178-127">Este error surgiría, por ejemplo, en una aplicación que usaba `bcp_collen` para establecer la longitud de los datos disponibles para una SQL Server `text` columna en 4500 y, a continuación, se llamó **bcp_moretext** cinco veces mientras se indicaba en cada llamada que la longitud del búfer de datos era de 1000 bytes.</span><span class="sxs-lookup"><span data-stu-id="40178-127">This error would arise, for example, in an application which used `bcp_collen` to set the length of available data for an SQL Server `text` column to 4500, then called **bcp_moretext** five times while indicating on each call that the data buffer length was 1000 bytes long.</span></span>  
  
 <span data-ttu-id="40178-128">Si una fila copiada contiene más de una columna de longitud variable larga, **bcp_moretext** primero envía sus datos a la columna con el número ordinal más bajo, seguida de la siguiente columna con el número ordinal más bajo, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="40178-128">If a copied row contains more than one long, variable-length column, **bcp_moretext** first sends its data to the lowest ordinally numbered column, followed by the next lowest ordinally numbered column, and so on.</span></span> <span data-ttu-id="40178-129">Es importante una configuración correcta de la longitud total de datos esperados.</span><span class="sxs-lookup"><span data-stu-id="40178-129">Correct setting of the total length of expected data is important.</span></span> <span data-ttu-id="40178-130">No hay ninguna manera de indicar, fuera de la configuración de longitud, que la copia masiva ha recibido todos los datos de una columna.</span><span class="sxs-lookup"><span data-stu-id="40178-130">There is no way to signal, outside of the length setting, that all data for a column has been received by bulk copy.</span></span>  
  
 <span data-ttu-id="40178-131">Cuando `var(max)` los valores se envían al servidor mediante bcp_sendrow y bcp_moretext, no es necesario llamar a bcp_collen para establecer la longitud de la columna.</span><span class="sxs-lookup"><span data-stu-id="40178-131">When `var(max)` values are sent to the server using bcp_sendrow and bcp_moretext, it is not necessary to call bcp_collen to set the column length.</span></span> <span data-ttu-id="40178-132">En su lugar, solo para estos tipos, el valor se termina llamando a bcp_sendrow con una longitud de cero.</span><span class="sxs-lookup"><span data-stu-id="40178-132">Instead, for these types only, the value is terminated by calling bcp_sendrow with a length of zero.</span></span>  
  
 <span data-ttu-id="40178-133">Normalmente, una aplicación llama a `bcp_sendrow` y **bcp_moretext** dentro de los bucles para enviar varias filas de datos.</span><span class="sxs-lookup"><span data-stu-id="40178-133">An application normally calls `bcp_sendrow` and **bcp_moretext** within loops to send a number of rows of data.</span></span> <span data-ttu-id="40178-134">A continuación se muestra un esquema de cómo hacerlo en una tabla que contiene dos `text` columnas:</span><span class="sxs-lookup"><span data-stu-id="40178-134">Here's an outline of how to do this for a table containing two `text` columns:</span></span>  
  
```  
while (there are still rows to send)  
{  
bcp_sendrow(...);  
  
for (all the data in the first varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
for (all the data in the second varbinary(max) column)  
bcp_moretext(...);  
bcp_moretext(hdbc, 0, NULL);  
  
}  
  
```  
  
## <a name="example"></a><span data-ttu-id="40178-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="40178-135">Example</span></span>  
 <span data-ttu-id="40178-136">En este ejemplo se muestra cómo usar **bcp_moretext** con **bcp_bind** y `bcp_sendrow` :</span><span class="sxs-lookup"><span data-stu-id="40178-136">This example shows how to use **bcp_moretext** with **bcp_bind** and `bcp_sendrow`:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
DBINT      idRow = 5;  
char*      pPart1 = "This text value isn't very long,";  
char*      pPart2 = " but it's broken into three parts";  
char*      pPart3 = " anyhow.";  
DBINT      cbAllParts;  
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
if (bcp_init(hdbc, "comdb..articles", NULL, NULL, DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Bind program variables to table columns.   
if (bcp_bind(hdbc, (LPCBYTE) &idRow, 0, SQL_VARLEN_DATA, NULL, 0,  
   SQLINT4, 1)    == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
cbAllParts = (DBINT) (strnlen(pPart1, sizeof(pPart1) + 1) + strnlen(pPart2, sizeof(pPart2) + 1) + strnlen(pPart3, sizeof(pPart3) + 1));  
if (bcp_bind(hdbc, NULL, 0, cbAllParts, NULL, 0, SQLTEXT, 2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Send this row, with the text value broken into three chunks.   
if (bcp_sendrow(hdbc) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart1, sizeof(pPart1) + 1), pPart1) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart2, sizeof(pPart2) + 1), pPart2) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
if (bcp_moretext(hdbc, (DBINT) strnlen(pPart3, sizeof(pPart3) + 1), pPart3) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// All done. Get the number of rows processed (should be one).  
nRowsProcessed = bcp_done(hdbc);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="40178-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="40178-137">See Also</span></span>  
 [<span data-ttu-id="40178-138">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="40178-138">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
