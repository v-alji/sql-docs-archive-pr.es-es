---
title: bcp_readfmt | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_readfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_readfmt function
ms.assetid: 654001c8-ae9f-425c-b820-f0191bf89367
author: rothja
ms.author: jroth
ms.openlocfilehash: 37032ec276be8b914d73e834453cc5d87cdedbbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671049"
---
# <a name="bcp_readfmt"></a><span data-ttu-id="d2607-102">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="d2607-102">bcp_readfmt</span></span>
  <span data-ttu-id="d2607-103">Lee una definición de formato de archivo de datos del archivo de formato especificado.</span><span class="sxs-lookup"><span data-stu-id="d2607-103">Reads a data file format definition from the specified format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2607-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2607-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_readfmt (  
HDBC   
hdbc  
,  
LPCTSTR   
szFormatFile  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d2607-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d2607-105">Arguments</span></span>  
 <span data-ttu-id="d2607-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="d2607-106">*hdbc*</span></span>  
 <span data-ttu-id="d2607-107">Es el identificador de la conexión ODBC habilitada para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="d2607-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="d2607-108">*szFormatFile*</span><span class="sxs-lookup"><span data-stu-id="d2607-108">*szFormatFile*</span></span>  
 <span data-ttu-id="d2607-109">Es la ruta de acceso y nombre del archivo que contiene los valores de formato para el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="d2607-109">Is the path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="d2607-110">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="d2607-110">Returns</span></span>  
 <span data-ttu-id="d2607-111">SUCCEED o FAIL.</span><span class="sxs-lookup"><span data-stu-id="d2607-111">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2607-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d2607-112">Remarks</span></span>  
 <span data-ttu-id="d2607-113">Después de `bcp_readfmt` leer los valores de formato, realiza las llamadas adecuadas a [bcp_columns](bcp-columns.md) y [bcp_colfmt](bcp-colfmt.md).</span><span class="sxs-lookup"><span data-stu-id="d2607-113">After `bcp_readfmt` reads the format values, it makes the appropriate calls to [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span> <span data-ttu-id="d2607-114">No es necesario que analice un archivo de formato y realice estas llamadas.</span><span class="sxs-lookup"><span data-stu-id="d2607-114">There is no need for you to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="d2607-115">Para conservar un archivo de formato, llame a [bcp_writefmt](bcp-writefmt.md).</span><span class="sxs-lookup"><span data-stu-id="d2607-115">To persist a format file, call [bcp_writefmt](bcp-writefmt.md).</span></span> <span data-ttu-id="d2607-116">Las llamadas a `bcp_readfmt` pueden hacer referencia a formatos guardados.</span><span class="sxs-lookup"><span data-stu-id="d2607-116">Calls to `bcp_readfmt` can reference saved formats.</span></span> <span data-ttu-id="d2607-117">Para obtener más información, vea [bcp_init](bcp-init.md).</span><span class="sxs-lookup"><span data-stu-id="d2607-117">For more information, see [bcp_init](bcp-init.md).</span></span>  
  
 <span data-ttu-id="d2607-118">Como alternativa, la utilidad de copia masiva (**BCP**) puede guardar los formatos de datos definidos por el usuario en archivos a los que puede hacer referencia `bcp_readfmt` .</span><span class="sxs-lookup"><span data-stu-id="d2607-118">Alternately, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by `bcp_readfmt`.</span></span> <span data-ttu-id="d2607-119">Para obtener más información acerca de la utilidad **BCP** y la estructura de los archivos de formato de datos **BCP** , vea [importación y exportación masivas de datos &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d2607-119">For more information about the **bcp** utility and the structure of **bcp** data format files, see [Bulk Import and Export of Data &#40;SQL Server&#41;](../import-export/bulk-import-and-export-of-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="d2607-120">El `BCPDELAYREADFMT` valor del parámetro *eOption* de [bcp_control](bcp-control.md) modifica el comportamiento de bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="d2607-120">The `BCPDELAYREADFMT` value of the *eOption* parameter of [bcp_control](bcp-control.md) modifies the behavior of bcp_readfmt.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2607-121">La versión 4.2 o posterior de la utilidad **bcp** debe haber generado el archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="d2607-121">The format file must have been produced by version 4.2 or later of the **bcp** utility.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2607-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2607-122">Example</span></span>  
  
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
if (bcp_init(hdbc, _T("myTable"), _T("myData.csv"),  
   _T("myErrors"),    DB_IN) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_readfmt(hdbc, _T("myFmtFile.fmt")) == FAIL)  
   {  
   // Raise error and return.  
   return;  
   }  
  
if (bcp_exec(hdbc, &nRowsProcessed) == SUCCEED)  
   {  
   cout << nRowsProcessed << " rows copied to SQL Server\n";  
   }  
  
// Carry on.  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2607-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2607-123">See Also</span></span>  
 [<span data-ttu-id="d2607-124">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="d2607-124">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
