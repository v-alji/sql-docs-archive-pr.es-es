---
title: Usar columnas de datos en ejecución (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data-at-execution
ms.assetid: 4eae58d1-03d4-40ca-8aa1-9b3ea10a38cf
author: rothja
ms.author: jroth
ms.openlocfilehash: 68690208b690f94909100132c966eb59d11e4652
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748768"
---
# <a name="use-data-at-execution-columns-odbc"></a><span data-ttu-id="b2d23-102">Usar columnas de datos en ejecución (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b2d23-102">Use Data-at-Execution Columns (ODBC)</span></span>
    
### <a name="to-use-data-at-execution-text-ntext-or-image-columns"></a><span data-ttu-id="b2d23-103">Para utilizar columnas text, ntext o image de datos en ejecución</span><span class="sxs-lookup"><span data-stu-id="b2d23-103">To use data-at-execution text, ntext, or image columns</span></span>  
  
1.  <span data-ttu-id="b2d23-104">Para cada columna de datos en ejecución, incluya valores especiales en los búferes previamente enlazados con [SQLBindCol](../native-client-odbc-api/sqlbindcol.md):</span><span class="sxs-lookup"><span data-stu-id="b2d23-104">For each data-at-execution column, put special values into the buffers previously bound by [SQLBindCol](../native-client-odbc-api/sqlbindcol.md):</span></span>  
  
    -   <span data-ttu-id="b2d23-105">Para el último parámetro, utilice SQL_LEN_DATA_AT_EXEC(longitud) donde longitud es la longitud total de los datos de la columna text, ntext o image en bytes.</span><span class="sxs-lookup"><span data-stu-id="b2d23-105">For the last parameter, use SQL_LEN_DATA_AT_EXEC(length) where length is the total length of the text, ntext, or image column data in bytes.</span></span>  
  
    -   <span data-ttu-id="b2d23-106">Para el cuarto parámetro, incluya un identificador de columna definido por el programa.</span><span class="sxs-lookup"><span data-stu-id="b2d23-106">For the fourth parameter, put a program-defined column identifier.</span></span>  
  
2.  <span data-ttu-id="b2d23-107">La llamada a [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) devuelve SQL_NEED_DATA, que indica las columnas de datos en ejecución listas para procesarse.</span><span class="sxs-lookup"><span data-stu-id="b2d23-107">Calling [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) returns SQL_NEED_DATA, which indicates that data-at-execution columns are ready for processing.</span></span>  
  
3.  <span data-ttu-id="b2d23-108">Para cada columna de datos en ejecución:</span><span class="sxs-lookup"><span data-stu-id="b2d23-108">For each data-at-execution column:</span></span>  
  
    -   <span data-ttu-id="b2d23-109">Llame a [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) para obtener el puntero a la matriz de columnas.</span><span class="sxs-lookup"><span data-stu-id="b2d23-109">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to get the column array pointer.</span></span> <span data-ttu-id="b2d23-110">Devolverá SQL_NEED_DATA si hay otra columna de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="b2d23-110">It will return SQL_NEED_DATA if there is another data-at-execution column.</span></span>  
  
    -   <span data-ttu-id="b2d23-111">Llame a [SQLPutData](../native-client-odbc-api/sqlputdata.md) una o más veces para enviar los datos de columna, hasta que se envíe la longitud.</span><span class="sxs-lookup"><span data-stu-id="b2d23-111">Call [SQLPutData](../native-client-odbc-api/sqlputdata.md) one or more times to send the column data, until length is sent.</span></span>  
  
4.  <span data-ttu-id="b2d23-112">Llame a [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) para indicar que se han enviado todos los datos de la columna de datos en ejecución final.</span><span class="sxs-lookup"><span data-stu-id="b2d23-112">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to indicate that all the data for the final data-at-execution column is sent.</span></span> <span data-ttu-id="b2d23-113">No devolverá SQL_NEED_DATA.</span><span class="sxs-lookup"><span data-stu-id="b2d23-113">It will not return SQL_NEED_DATA.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2d23-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2d23-114">Example</span></span>  
 <span data-ttu-id="b2d23-115">En este ejemplo se muestra cómo leer datos de caracteres variables SQL_LONG mediante SQLGetData.</span><span class="sxs-lookup"><span data-stu-id="b2d23-115">The sample shows how to read a SQL_LONG variable character data using SQLGetData.</span></span> <span data-ttu-id="b2d23-116">Este ejemplo no es compatible con IA64.</span><span class="sxs-lookup"><span data-stu-id="b2d23-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="b2d23-117">Necesitará un origen de datos ODBC denominado AdventureWorks, cuya base de datos predeterminada sea la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b2d23-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="b2d23-118">(Puede descargar la base de datos de ejemplo AdventureWorks de la Página principal de [ejemplos y proyectos](https://go.microsoft.com/fwlink/?LinkID=85384) de la comunidad de Microsoft SQL Server). Este origen de datos debe estar basado en el controlador ODBC proporcionado por el sistema operativo (el nombre del controlador es "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="b2d23-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="b2d23-119">Si genera y ejecuta este ejemplo como una aplicación de 32 bits en un sistema operativo de 64 bits, debe crear el origen de datos ODBC con el Administrador ODBC en %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="b2d23-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="b2d23-120">Este ejemplo se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="b2d23-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b2d23-121">Para conectarse a una instancia con nombre, cambie la definición del origen de datos ODBC para especificar la instancia utilizando el formato servidor\instanciaConNombre.</span><span class="sxs-lookup"><span data-stu-id="b2d23-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="b2d23-122">De forma predeterminada, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="b2d23-122">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="b2d23-123">Ejecute la primera lista de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para crear la tabla utilizada por el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b2d23-123">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the table used by the sample.</span></span>  
  
 <span data-ttu-id="b2d23-124">Compile el segundo fragmento de código (C++) con odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="b2d23-124">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="b2d23-125">A continuación, ejecute el programa.</span><span class="sxs-lookup"><span data-stu-id="b2d23-125">Then execute the program.</span></span>  
  
 <span data-ttu-id="b2d23-126">Ejecute la tercera lista de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para eliminar la tabla utilizada por el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b2d23-126">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
CREATE TABLE emp3 (NAME char(30), AGE int, BIRTHDAY datetime, Memo1 text)  
INSERT INTO emp3 (NAME, AGE, Memo1) VALUES   ('Name1', '12', 'This is the first employee')  
INSERT INTO emp3 (NAME, AGE, Memo1) VALUES   ('Name2', '18', 'This is the second employee')  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define BUFFERSIZE  450  
  
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
};  
  
int main() {  
   RETCODE retcode;  
   SWORD cntr;  
  
   // SQLGetData variables.  
   UCHAR Data[BUFFERSIZE];  
   SDWORD cbBatch = (SDWORD)sizeof(Data)-1;  
   SQLLEN cbTxtSize;  
  
   // Clear data array.  
   for (cntr = 0 ; cntr < BUFFERSIZE ; cntr++)  
      Data[cntr] = 0x00;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
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
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle; prepare, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT Memo1 FROM emp3", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get first row.  
   retcode = SQLFetch(hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLFetch(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get the SQL_LONG column.  
   cntr = 1;  
   while ( (retcode = SQLGetData(hstmt1, 1, SQL_C_CHAR, Data, cbBatch, &cbTxtSize)) != SQL_NO_DATA) {  
      printf("GetData iteration %d, pcbValue = %d,\n", cntr++, cbTxtSize);  
      printf("Data = %s\n\n", Data);  
  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("GetData(hstmt1) Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }   
  
   // Clean up  
   //SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'emp3')  
     DROP TABLE emp3  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2d23-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2d23-127">See Also</span></span>  
 [<span data-ttu-id="b2d23-128">Temas de procedimientos de administración de columnas de texto e imagen &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b2d23-128">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
  
