---
title: Usar parámetros de datos en ejecución (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data-at-execution
ms.assetid: 2a738aef-c991-4f62-bdab-a5221c335f31
author: rothja
ms.author: jroth
ms.openlocfilehash: cf87309f1e325b94ff455d446fbd2e76d5c06ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748766"
---
# <a name="use-data-at-execution-parameters-odbc"></a><span data-ttu-id="03684-102">Usar parámetros de datos en ejecución (ODBC)</span><span class="sxs-lookup"><span data-stu-id="03684-102">Use Data-at-Execution Parameters (ODBC)</span></span>
    
### <a name="to-use-data-at-execution-text-ntext-or-image-parameters"></a><span data-ttu-id="03684-103">Para usar parámetros de datos en ejecución de tipo text, ntext o image</span><span class="sxs-lookup"><span data-stu-id="03684-103">To use data-at-execution text, ntext, or image parameters</span></span>  
  
1.  <span data-ttu-id="03684-104">Cuando llame a [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) para enlazar un búfer de programa al parámetro de instrucción:</span><span class="sxs-lookup"><span data-stu-id="03684-104">When calling [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) to bind a program buffer to the statement parameter:</span></span>  
  
    -   <span data-ttu-id="03684-105">Para el último parámetro, use SQL_LEN_DATA_AT_EXEC (*longitud*) donde *longitud* es la longitud total de los `text` `ntext` datos de parámetro, o `image` en bytes.</span><span class="sxs-lookup"><span data-stu-id="03684-105">For the last parameter, use SQL_LEN_DATA_AT_EXEC(*length*) where *length* is the total length of the `text`, `ntext`, or `image` parameter data in bytes.</span></span>  
  
    -   <span data-ttu-id="03684-106">Use un `rgbValue` (octavo parámetro) de un identificador de parámetros definido por el programa.</span><span class="sxs-lookup"><span data-stu-id="03684-106">Use an `rgbValue` (eighth parameter) of a program-defined parameter identifier.</span></span>  
  
2.  <span data-ttu-id="03684-107">Al llamar a [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) o [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) devuelve SQL_NEED_DATA, lo que indica que los parámetros de datos en ejecución están listos para procesar.</span><span class="sxs-lookup"><span data-stu-id="03684-107">Calling [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) or [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) returns SQL_NEED_DATA, which indicates that data-at-execution parameters are ready for processing.</span></span>  
  
3.  <span data-ttu-id="03684-108">Para cada parámetro de datos en ejecución:</span><span class="sxs-lookup"><span data-stu-id="03684-108">For each data-at-execution parameter:</span></span>  
  
    -   <span data-ttu-id="03684-109">Llame a [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) para obtener el identificador del parámetro definido por el programa.</span><span class="sxs-lookup"><span data-stu-id="03684-109">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to get the program-defined parameter ID.</span></span> <span data-ttu-id="03684-110">Devolverá SQL_NEED_DATA si hay otro parámetro de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="03684-110">It will return SQL_NEED_DATA if there is another data-at-execution parameter.</span></span>  
  
    -   <span data-ttu-id="03684-111">Llame a una o más veces a [SQLPutData](../native-client-odbc-api/sqlputdata.md) para enviar los datos del parámetro, hasta que se envíe la longitud.</span><span class="sxs-lookup"><span data-stu-id="03684-111">Call [SQLPutData](../native-client-odbc-api/sqlputdata.md) one or more times, to send the parameter data, until length is sent.</span></span>  
  
4.  <span data-ttu-id="03684-112">Llame a [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) para indicar que se envían todos los datos para el parámetro de datos en ejecución final.</span><span class="sxs-lookup"><span data-stu-id="03684-112">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to indicate that all the data for the final data-at-execution parameter is sent.</span></span> <span data-ttu-id="03684-113">No devolverá SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="03684-113">It will not return SQL_NEED_DATA.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03684-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="03684-114">Example</span></span>  
 <span data-ttu-id="03684-115">En este ejemplo, se muestra cómo leer datos de caracteres variables SQL_LONG mediante SQLParamData y SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="03684-115">The sample shows how to read SQL_LONG variable character data using SQLParamData and SQLPutData.</span></span> <span data-ttu-id="03684-116">Este ejemplo no es compatible con IA64.</span><span class="sxs-lookup"><span data-stu-id="03684-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="03684-117">Necesitará un origen de datos ODBC denominado AdventureWorks, cuya base de datos predeterminada sea la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="03684-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="03684-118">(Puede descargar la base de datos de ejemplo AdventureWorks de la Página principal de [ejemplos y proyectos](https://go.microsoft.com/fwlink/?LinkID=85384) de la comunidad de Microsoft SQL Server). Este origen de datos debe estar basado en el controlador ODBC proporcionado por el sistema operativo (el nombre del controlador es "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="03684-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="03684-119">Si genera y ejecuta este ejemplo como una aplicación de 32 bits en un sistema operativo de 64 bits, debe crear el origen de datos ODBC con el Administrador ODBC en %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="03684-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="03684-120">Este ejemplo se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="03684-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="03684-121">Para conectarse a una instancia con nombre, cambie la definición del origen de datos ODBC para especificar la instancia utilizando el formato servidor\instanciaConNombre.</span><span class="sxs-lookup"><span data-stu-id="03684-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="03684-122">De forma predeterminada, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="03684-122">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="03684-123">Ejecute la primera lista de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para crear la tabla utilizada por el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="03684-123">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the table used by the sample.</span></span>  
  
 <span data-ttu-id="03684-124">Compile el segundo fragmento de código (C++) con odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="03684-124">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="03684-125">A continuación, ejecute el programa.</span><span class="sxs-lookup"><span data-stu-id="03684-125">Then execute the program.</span></span>  
  
 <span data-ttu-id="03684-126">Ejecute la tercera lista de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para eliminar la tabla utilizada por el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="03684-126">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
CREATE TABLE emp4 (NAME char(30), AGE int, BIRTHDAY datetime, Memo1 text)  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define TEXTSIZE  12000  
#define MAXBUFLEN 256  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;       
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void Cleanup() {  
   if (hstmt1 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // SQLBindParameter variables.  
   SQLLEN cbTextSize, lbytes;  
  
   // SQLParamData variable.  
   PTR pParmID;  
  
   // SQLPutData variables.  
   UCHAR  Data[] =   
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyzabcdefghijklmnopqrstuvwxyz"  
      "abcdefghijklmnopqrstuvwxyz";  
  
   SDWORD cbBatch = (SDWORD)sizeof(Data) - 1;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set parameters based on total data to send.  
   lbytes = (SDWORD)TEXTSIZE;  
   cbTextSize = SQL_LEN_DATA_AT_EXEC(lbytes);  
  
   // Bind the parameter marker.  
   retcode = SQLBindParameter (hstmt1,           // hstmt  
                               1,                // ipar  
                               SQL_PARAM_INPUT,  // fParamType  
                               SQL_C_CHAR,       // fCType  
                               SQL_LONGVARCHAR,  // FSqlType  
                               lbytes,           // cbColDef  
                               0,                // ibScale  
                               (VOID *)1,        // rgbValue  
                               0,                // cbValueMax  
                               &cbTextSize);     // pcbValue  
  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLBindParameter Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the command.  
   retcode =   
      SQLExecDirect(hstmt1, (UCHAR*)"INSERT INTO emp4 VALUES('Paul Borm', 46,'1950-11-12 00:00:00', ?)", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_NEED_DATA) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Check to see if NEED_DATA; if yes, use SQLPutData.  
   retcode = SQLParamData(hstmt1, &pParmID);  
   if (retcode == SQL_NEED_DATA) {  
      while (lbytes > cbBatch) {  
         SQLPutData(hstmt1, Data, cbBatch);  
         lbytes -= cbBatch;  
      }  
      // Put final batch.  
      retcode = SQLPutData(hstmt1, Data, lbytes);   
   }  
  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLParamData Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Make final SQLParamData call.  
   retcode = SQLParamData(hstmt1, &pParmID);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("Final SQLParamData Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clean up.  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'emp4')  
     DROP TABLE emp4  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="03684-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="03684-127">See Also</span></span>  
 [<span data-ttu-id="03684-128">Temas de procedimientos de administración de columnas de texto e imagen &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="03684-128">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
  
