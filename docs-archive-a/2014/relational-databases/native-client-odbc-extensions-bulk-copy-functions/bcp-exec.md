---
title: bcp_exec | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_exec
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_exec function
ms.assetid: b23ea2cc-8545-4873-b0c1-57e76b0a3a7b
author: rothja
ms.author: jroth
ms.openlocfilehash: f925c6cb1e3a36f79ba4f560a06c5b6d499ece4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661996"
---
# <a name="bcp_exec"></a><span data-ttu-id="e5fdb-102">bcp_exec</span><span class="sxs-lookup"><span data-stu-id="e5fdb-102">bcp_exec</span></span>
  <span data-ttu-id="e5fdb-103">Ejecuta una copia masiva completa de los datos entre una tabla de base de datos y un archivo de usuario.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-103">Executes a complete bulk copy of data between a database table and a user file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5fdb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e5fdb-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_exec (  
HDBC   
hdbc  
,  
LPDBINT   
pnRowsProcessed  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="e5fdb-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e5fdb-105">Arguments</span></span>  
 <span data-ttu-id="e5fdb-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="e5fdb-106">*hdbc*</span></span>  
 <span data-ttu-id="e5fdb-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="e5fdb-108">*pnRowsProcessed*</span><span class="sxs-lookup"><span data-stu-id="e5fdb-108">*pnRowsProcessed*</span></span>  
 <span data-ttu-id="e5fdb-109">Es un puntero a un DBINT.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-109">Is a pointer to a DBINT.</span></span> <span data-ttu-id="e5fdb-110">La función **bcp_exec** llena este DBINT con el número de filas copiadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-110">The **bcp_exec** function fills this DBINT with the number of rows successfully copied.</span></span> <span data-ttu-id="e5fdb-111">Si *pnRowsProcessed* es NULL, **bcp_exec**lo omite.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-111">If *pnRowsProcessed* is NULL, it is ignored by **bcp_exec**.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="e5fdb-112">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="e5fdb-112">Returns</span></span>  
 <span data-ttu-id="e5fdb-113">SUCCEED, SUCCEED_ASYNC o FAIL.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-113">SUCCEED, SUCCEED_ASYNC, or FAIL.</span></span> <span data-ttu-id="e5fdb-114">La función **bcp_exce** devuleve SUCCEED si se se copian todas las filas.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-114">The **bcp_exec** function returns SUCCEED if all rows are copied.</span></span> <span data-ttu-id="e5fdb-115">**bcp_exec** devuelve SUCCEED_ASYNC si la copia masiva asincrónica no se ha completado todavía.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-115">**bcp_exec** returns SUCCEED_ASYNC if an asynchronous bulk copy operation is still outstanding.</span></span> <span data-ttu-id="e5fdb-116">**bcp_exce** devuelve FAIL si se produce un error total o si el número de filas que generan errores alcanza el valor que se ha especificado para BCPMAXERRS con [bcp_control](bcp-control.md).</span><span class="sxs-lookup"><span data-stu-id="e5fdb-116">**bcp_exec** returns FAIL if a complete failure occurs, or if the number of rows generating errors reaches the value specified for BCPMAXERRS using [bcp_control](bcp-control.md).</span></span> <span data-ttu-id="e5fdb-117">BCPMAXERRS toma como valor predeterminado 10.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-117">BCPMAXERRS defaults to 10.</span></span> <span data-ttu-id="e5fdb-118">La opción BCPMAXERRS afecta solo a los errores de sintaxis detectados por el proveedor al leer las filas del archivo de datos (y no las filas enviadas al servidor).</span><span class="sxs-lookup"><span data-stu-id="e5fdb-118">The BCPMAXERRS option affects only the syntax errors detected by the provider while reading the rows from the data file (and not the rows sent to the server).</span></span> <span data-ttu-id="e5fdb-119">El servidor anula el lote cuando detecta un error con una fila.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-119">Server aborts the batch when it detects an error with a row.</span></span> <span data-ttu-id="e5fdb-120">Compruebe en el parámetro *pnRowsProcessed* el número de filas copiadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-120">Check the *pnRowsProcessed* parameter for the number of rows successfully copied.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5fdb-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e5fdb-121">Remarks</span></span>  
 <span data-ttu-id="e5fdb-122">Esta función copia los datos de un archivo de usuario en una tabla de base de datos o viceversa, dependiendo del valor del parámetro *eDirection* de [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="e5fdb-122">This function copies data from a user file to a database table or vice versa, depending on the value of the *eDirection* parameter in [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="e5fdb-123">Antes de llamar a **bcp_exec**, llame a **bcp_init** con un nombre de archivo de usuario válido.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-123">Before calling **bcp_exec**, call **bcp_init** with a valid user file name.</span></span> <span data-ttu-id="e5fdb-124">Si no lo hace, se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-124">Failure to do so results in an error.</span></span>  
  
 <span data-ttu-id="e5fdb-125">**bcp_exec** es la única función de copia masiva que es probable que quede pendiente durante un período de tiempo indeterminado.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-125">**bcp_exec** is the only bulk copy function that is likely to be outstanding for any length of time.</span></span> <span data-ttu-id="e5fdb-126">Por lo tanto, es la única función de copia masiva que admite el modo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-126">It is therefore the only bulk copy function that supports asynchronous mode.</span></span> <span data-ttu-id="e5fdb-127">Para establecer el modo asincrónico, utilice [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) para establecer SQL_ATTR_ASYNC_ENABLE en SQL_ASYNC_ENABLE_ON antes de llamar a **bcp_exec**.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-127">To set asynchronous mode, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set SQL_ATTR_ASYNC_ENABLE to SQL_ASYNC_ENABLE_ON before calling **bcp_exec**.</span></span> <span data-ttu-id="e5fdb-128">Para comprobar si se ha completado, llame a **bcp_exec** con los mismos parámetros.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-128">To test for completion, call **bcp_exec** with the same parameters.</span></span> <span data-ttu-id="e5fdb-129">Si la copia masiva no se ha completado todavía, **bcp_exec** devuelve SUCCEED_ASYNC.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-129">If the bulk copy has not yet completed, **bcp_exec** returns SUCCEED_ASYNC.</span></span> <span data-ttu-id="e5fdb-130">También devuelve en *pnRowsProcessed* un recuento del estado del número de filas enviadas al servidor.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-130">It also returns in *pnRowsProcessed* a status count of the number of rows that have been sent to the server.</span></span> <span data-ttu-id="e5fdb-131">Las filas enviadas al servidor no se confirman hasta que se alcanza el final de un lote.</span><span class="sxs-lookup"><span data-stu-id="e5fdb-131">Rows sent to the server are not committed until the end of a batch has been reached.</span></span>  
  
 <span data-ttu-id="e5fdb-132">Para obtener información sobre un cambio importante en la copia masiva a partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , vea [realizar operaciones de copia masiva &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="e5fdb-132">For information about a breaking change in bulk-copying beginning in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], see [Performing Bulk Copy Operations &#40;ODBC&#41;](../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5fdb-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5fdb-133">Example</span></span>  
 <span data-ttu-id="e5fdb-134">En el siguiente ejemplo, se muestra cómo utilizar **bcp_exec**:</span><span class="sxs-lookup"><span data-stu-id="e5fdb-134">The following example shows how to use **bcp_exec**:</span></span>  
  
```  
// Variables like henv not specified.  
HDBC      hdbc;  
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
if (bcp_init(hdbc, _T("pubs..authors"), _T("authors.sav"), NULL, DB_OUT)  
   == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
// Now, execute the bulk copy.   
if (bcp_exec(hdbc, &nRowsProcessed) == FAIL)  
   {  
   if (nRowsProcessed == -1)  
      {  
      printf_s("No rows processed on bulk copy execution.\n");  
      }  
   else  
      {  
      printf_s("Incomplete bulk copy.   Only %ld row%s copied.\n",  
         nRowsProcessed, (nRowsProcessed == 1) ? "": "s");  
      }  
   return;  
   }  
  
printf_s("%ld rows processed.\n", nRowsProcessed);  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5fdb-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5fdb-135">See Also</span></span>  
 [<span data-ttu-id="e5fdb-136">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="e5fdb-136">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
