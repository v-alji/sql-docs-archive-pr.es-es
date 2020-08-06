---
title: bcp_setbulkmode | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bcp_setbulkmode function
ms.assetid: de56f206-1f7e-4c03-bf22-da9c7f9f4433
author: rothja
ms.author: jroth
ms.openlocfilehash: 1b7a68dfb3c868422b2e01cccf511a623d3afe52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674095"
---
# <a name="bcp_setbulkmode"></a><span data-ttu-id="bc0bd-102">bcp_setbulkmode</span><span class="sxs-lookup"><span data-stu-id="bc0bd-102">bcp_setbulkmode</span></span>
  <span data-ttu-id="bc0bd-103">bcp_setbulkmode permite especificar el formato de columna en una operación de copia masiva, estableciendo todos los atributos de columna en una única llamada de función.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-103">bcp_setbulkmode lets you specify the column format in a bulk copy operation, setting all the column attributes in a single function call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc0bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc0bd-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_setbulkmode (  
   HDBC   
hdbc  
,  
   INT   
property  
,  
   void *   
pField  
,  
   INT   
cbField  
,  
   void *   
pRow  
,  
   INT   
cbRow  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="bc0bd-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bc0bd-105">Arguments</span></span>  
 <span data-ttu-id="bc0bd-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="bc0bd-106">*hdbc*</span></span>  
 <span data-ttu-id="bc0bd-107">Identificador de la conexión ODBC habilitado para la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-107">The bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="bc0bd-108">*property*</span><span class="sxs-lookup"><span data-stu-id="bc0bd-108">*property*</span></span>  
 <span data-ttu-id="bc0bd-109">Constante de tipo BYTE.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-109">A constant of type BYTE.</span></span> <span data-ttu-id="bc0bd-110">Vea la tabla en la sección Comentarios para obtener una lista de las constantes.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-110">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="bc0bd-111">*pField*</span><span class="sxs-lookup"><span data-stu-id="bc0bd-111">*pField*</span></span>  
 <span data-ttu-id="bc0bd-112">Puntero al valor de terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-112">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="bc0bd-113">*cbField*</span><span class="sxs-lookup"><span data-stu-id="bc0bd-113">*cbField*</span></span>  
 <span data-ttu-id="bc0bd-114">Longitud (en bytes) del valor de terminador de campo.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-114">The length (in bytes) of the field terminator value.</span></span>  
  
 <span data-ttu-id="bc0bd-115">*pRow*</span><span class="sxs-lookup"><span data-stu-id="bc0bd-115">*pRow*</span></span>  
 <span data-ttu-id="bc0bd-116">Puntero al valor de terminador de fila.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-116">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="bc0bd-117">*cbRow*</span><span class="sxs-lookup"><span data-stu-id="bc0bd-117">*cbRow*</span></span>  
 <span data-ttu-id="bc0bd-118">Longitud en bytes del valor de terminador de fila.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-118">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="bc0bd-119">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="bc0bd-119">Returns</span></span>  
 <span data-ttu-id="bc0bd-120">SUCCEED o FAIL</span><span class="sxs-lookup"><span data-stu-id="bc0bd-120">SUCCEED or FAIL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc0bd-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc0bd-121">Remarks</span></span>  
 <span data-ttu-id="bc0bd-122">bcp_setbulkmode puede usarse para realizar una copia masiva de una consulta o una tabla.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-122">bcp_setbulkmode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="bc0bd-123">Cuando bcp_setbulkmode se utiliza para realizar una copia masiva de una instrucción de consulta, se debe llamar antes de llamar a bcp_control con BCP_HINT.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-123">When bcp_setbulkmode is used to bulk copy out a query statement, it must be called before calling bcp_control with BCP_HINT.</span></span>  
  
 <span data-ttu-id="bc0bd-124">bcp_setbulkmode es una alternativa al uso de [bcp_setcolfmt](bcp-setcolfmt.md) y [bcp_columns](bcp-columns.md), que solo permiten especificar el formato de una columna por cada llamada de función.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-124">bcp_setbulkmode is an alternative to using [bcp_setcolfmt](bcp-setcolfmt.md) and [bcp_columns](bcp-columns.md), which only let you specify the format of one column per function call.</span></span>  
  
 <span data-ttu-id="bc0bd-125">En la lista siguiente se enumeran las constantes del parámetro *property* .</span><span class="sxs-lookup"><span data-stu-id="bc0bd-125">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="bc0bd-126">Propiedad</span><span class="sxs-lookup"><span data-stu-id="bc0bd-126">Property</span></span>|<span data-ttu-id="bc0bd-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc0bd-127">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="bc0bd-128">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="bc0bd-128">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="bc0bd-129">Especifica el modo de salida de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-129">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="bc0bd-130">Corresponde a la opción-c en BCP.EXE y a bcp_setcolfmt con la `BCP_FMT_TYPE` propiedad establecida en `SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="bc0bd-130">Corresponds to the -c option in BCP.EXE, and to bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="bc0bd-131">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="bc0bd-131">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="bc0bd-132">Especifica el modo de salida de Unicode.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-132">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="bc0bd-133">Corresponde a la opción-w de BCP.EXE y bcp_setcolfmt con la `BCP_FMT_TYPE` propiedad establecida en `SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="bc0bd-133">Corresponds to the -w option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLNCHAR`.</span></span>|  
|<span data-ttu-id="bc0bd-134">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="bc0bd-134">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="bc0bd-135">Especifica los tipos nativos para los tipos no de caracteres y Unicode para los tipos de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-135">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="bc0bd-136">Corresponde a la opción-N de BCP.EXE y bcp_setcolfmt con `BCP_FMT_TYPE` la propiedad establecida en `SQLNCHAR` si el tipo de columna es una cadena (valor predeterminado si no es una cadena).</span><span class="sxs-lookup"><span data-stu-id="bc0bd-136">Corresponds to the -N option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to `SQLNCHAR` if the column type is a string (default if not a string).</span></span>|  
|<span data-ttu-id="bc0bd-137">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="bc0bd-137">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="bc0bd-138">Especifica los tipos de base de datos nativos.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-138">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="bc0bd-139">Corresponde a la opción-n de BCP.EXE y bcp_setcolfmt con `BCP_FMT_TYPE` la propiedad establecida en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-139">Corresponds to the -n option in BCP.EXE and bcp_setcolfmt with `BCP_FMT_TYPE` property set to the default.</span></span>|  
  
 <span data-ttu-id="bc0bd-140">No debe utilizar bcp_setbulkmode con una secuencia de llamadas de función que incluya bcp_setcolfmt, bcp_control y bcp_readfmt.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-140">You should not use bcp_setbulkmode with a sequence of function calls that includes bcp_setcolfmt, bcp_control, and bcp_readfmt.</span></span> <span data-ttu-id="bc0bd-141">Por ejemplo, no debe llamar a bcp_control (BCPTEXTFILE) y bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-141">For example, you should not call bcp_control(BCPTEXTFILE) and bcp_setbulkmode.</span></span>  
  
 <span data-ttu-id="bc0bd-142">Puede llamar a bcp_control y bcp_setbulkmode para bcp_control opciones que no entren en conflicto con bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-142">You can call bcp_control and bcp_setbulkmode for bcp_control options that do not conflict with bcp_setbulkmode.</span></span> <span data-ttu-id="bc0bd-143">Por ejemplo, puede llamar a bcp_control (BCPFIRST) y bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-143">For example, you can call bcp_control(BCPFIRST) and bcp_setbulkmode.</span></span>  
  
 <span data-ttu-id="bc0bd-144">Si intenta llamar a bcp_setbulkmode con una secuencia de llamadas a función que incluye bcp_setcolfmt, bcp_control y bcp_readfmt, una de las llamadas de función devolverá un error de secuencia.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-144">If you attempt to call bcp_setbulkmode with a sequence of function calls that includes bcp_setcolfmt, bcp_control, and bcp_readfmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="bc0bd-145">Si opta por corregir el error, llame a bcp_init para restablecer toda la configuración y volver a empezar.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-145">If you choose to correct the failure, call bcp_init to reset all the settings and start over.</span></span>  
  
 <span data-ttu-id="bc0bd-146">En la siguiente tabla se presentan algunos ejemplos de llamadas a función que producen un error de secuencia de función:</span><span class="sxs-lookup"><span data-stu-id="bc0bd-146">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="bc0bd-147">Secuencia de llamadas</span><span class="sxs-lookup"><span data-stu-id="bc0bd-147">Call sequence</span></span>  
  
```  
bcp_init("table", DB_IN);  
bcp_setbulkmode();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_setbulkmode();  
bcp_readfmt();  
```  
  
```  
bcp_init(NULL, DB_OUT);  
bcp_control(BCPHINTS, "select ...");  
bcp_setbulkmode();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_setbulkmode();  
bcp_setcolfmt();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_readfmt();  
bcp_setcolfmt();  
```  
  
```  
bcp_init(NULL, DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_setbulkmode();  
bcp_control(BCPHINTS, "select ...");  
bcp_readfmt();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_columns();  
```  
  
```  
bcp_init("table", DB_OUT);  
bcp_control(BCPDELAYREADFMT, true);  
bcp_setcolfmt();  
```  
  
## <a name="example"></a><span data-ttu-id="bc0bd-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc0bd-148">Example</span></span>  
 <span data-ttu-id="bc0bd-149">En el siguiente ejemplo se crean cuatro archivos con valores distintos de bcp_setbulkmode.</span><span class="sxs-lookup"><span data-stu-id="bc0bd-149">The following sample creates four files using different settings of bcp_setbulkmode.</span></span>  
  
```  
// compile with: sqlncli11.lib odbc32.lib  
  
#include <windows.h>  
#include <stdio.h>  
#include <tchar.h>  
#include <sqlext.h>  
#include "sqlncli.h"  
  
// Global variables  
SQLHENV g_hEnv = NULL;  
SQLHDBC g_hDbc = NULL;  
  
void ODBCCleanUp() {  
   if (g_hDbc) {  
      SQLDisconnect(g_hDbc);  
      SQLFreeHandle(SQL_HANDLE_DBC, g_hDbc);  
      g_hDbc = NULL;  
   }  
   if (g_hEnv) {  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      g_hEnv = NULL;  
   }  
}  
  
BOOL MakeODBCConnection(TCHAR * pszServer) {  
   TCHAR szConnectionString[500];  
   TCHAR szOutConnectionString[500];  
   SQLSMALLINT iLen;  
   SQLRETURN rc;  
  
   _sntprintf_s(szConnectionString, 500, TEXT("DRIVER={SQL Server Native Client 11.0};Server=%s;Trusted_connection=yes;"), pszServer);  
   rc = SQLAllocHandle(SQL_HANDLE_ENV, SQL_NULL_HANDLE,&g_hEnv);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLAllocHandle(SQL_HANDLE_ENV...) failed\n");  
      return false;  
   }  
   rc = SQLSetEnvAttr(g_hEnv,SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, SQL_IS_UINTEGER);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLSetEnvAttr failed\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      return false;  
   }  
   rc = SQLAllocHandle( SQL_HANDLE_DBC, g_hEnv , &g_hDbc);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLAllocHandle(SQL_HANDLE_DBC...) failed\n");  
      SQLFreeHandle(SQL_HANDLE_ENV, g_hEnv);  
      return false;  
   }  
   // Enable BCP  
   rc = SQLSetConnectAttr(g_hDbc, SQL_COPT_SS_BCP, (SQLPOINTER)SQL_BCP_ON, SQL_IS_INTEGER);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLSetConnectAttr(.. SQL_COPT_SS_BCP, (SQLPOINTER)SQL_BCP_ON ...) failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   // connecting ...  
   rc = SQLDriverConnect(g_hDbc,NULL, (SQLTCHAR*)szConnectionString, SQL_NTS, (SQLTCHAR*)szOutConnectionString, 500, &iLen, SQL_DRIVER_NOPROMPT);  
   if (SQL_SUCCESS != rc && SQL_SUCCESS_WITH_INFO != rc) {  
      printf("SQLDriverConnect(SQL_HANDLE_DBC...) failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   return true;  
}  
  
BOOL BCPSetBulkMode(TCHAR * pszServer, TCHAR * pszQureryOut, char BCPType, TCHAR * pszDataFile) {  
   SQLRETURN rc;  
  
   if (!MakeODBCConnection(pszServer))  
      return false;  
   rc = bcp_init(g_hDbc, NULL, pszDataFile, NULL, DB_OUT);   // bcp init for queryout  
   if (SUCCEED != rc) {  
      printf("bcp_init failed\n");  
      ODBCCleanUp();  
      return false;  
   }  
   // setbulkmode  
   char ColTerm[] = "\t";  
   char RowTerm[] = "\r\n";  
   wchar_t wColTerm[] = L"\t";  
   wchar_t wRowTerm[] = L"\r\n";  
   BYTE * pColTerm = NULL;  
   int cbColTerm = NULL;  
   BYTE * pRowTerm = 0;  
   int cbRowTerm = 0;  
   int bulkmode = -1;  
  
   if (BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if (BCPType == 'w') {   // bcp -w   
         pColTerm = (BYTE*)wColTerm;  
         pRowTerm = (BYTE*)wRowTerm;  
         cbColTerm = 2;  
         cbRowTerm = 4;  
         bulkmode = BCP_OUT_WIDE_CHARACTER_MODE;  
      }  
      else  
         if (BCPType == 'n')   // bcp -n  
            bulkmode = BCP_OUT_NATIVE_MODE;  
         else  
            if (BCPType == 'N')   // bcp -n  
               bulkmode = BCP_OUT_NATIVE_TEXT_MODE;  
            else {  
               printf("unknown bcp mode\n");  
               ODBCCleanUp();  
               return false;  
            }  
            rc = bcp_setbulkmode(g_hDbc, bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (SUCCEED != rc) {  
               printf("bcp_setbulkmode failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            // set queryout TSQL statement  
            rc = bcp_control(g_hDbc, BCPHINTS , pszQureryOut);  
            if (SUCCEED != rc) {  
               printf("bcp_control(..BCP_OPTION_HINTS..) failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBINT nRowsInserted = 0;  
            rc = bcp_exec(g_hDbc, &nRowsInserted);  
            if (SUCCEED != rc) {  
               printf("bcp_exec failed\n");  
               ODBCCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            ODBCCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', TEXT("bcpc.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', TEXT("bcpw.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', TEXT("bcpn.dat"));  
   BCPSetBulkMode(TEXT("localhost"), TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', TEXT("bcp_N.dat"));  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc0bd-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc0bd-150">See Also</span></span>  
 [<span data-ttu-id="bc0bd-151">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="bc0bd-151">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
