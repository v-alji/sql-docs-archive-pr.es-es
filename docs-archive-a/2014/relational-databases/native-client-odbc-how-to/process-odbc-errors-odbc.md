---
title: Procesar errores de ODBC (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- errors [ODBC]
ms.assetid: 66ab0762-79fe-4a31-b655-27dd215a0af7
author: rothja
ms.author: jroth
ms.openlocfilehash: 9f42223ffda8462ec740b94eb584565dfe286e0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748762"
---
# <a name="process-odbc-errors-odbc"></a><span data-ttu-id="05beb-102">Procesar errores de ODBC (ODBC)</span><span class="sxs-lookup"><span data-stu-id="05beb-102">Process ODBC Errors (ODBC)</span></span>
  <span data-ttu-id="05beb-103">Se pueden usar dos llamadas a la función de ODBC para recuperar los mensajes de ODBC: [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) y [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md).</span><span class="sxs-lookup"><span data-stu-id="05beb-103">Two ODBC function calls can be used to retrieve ODBC messages: [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) and [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md).</span></span> <span data-ttu-id="05beb-104">Para obtener la información principal relacionada con ODBC de los campos de diagnóstico **SQLState**, **pfNative** y **ErrorMessage**, llame a [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) hasta que devuelva SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="05beb-104">To obtain primary ODBC-related information in the **SQLState**, **pfNative**, and **ErrorMessage** diagnostic fields, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="05beb-105">Para cada registro de diagnóstico, se puede llamar a [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) para recuperar los campos individuales.</span><span class="sxs-lookup"><span data-stu-id="05beb-105">For each diagnostic record, [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) can be called to retrieve individual fields.</span></span> <span data-ttu-id="05beb-106">Todos los campos específicos del controlador se deben recuperar utilizando `SQLGetDiagField`.</span><span class="sxs-lookup"><span data-stu-id="05beb-106">All driver-specific fields must be retrieved using `SQLGetDiagField`.</span></span>  
  
 <span data-ttu-id="05beb-107">[SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) y [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) los procesa el Administrador de controladores ODBC, no un controlador individual.</span><span class="sxs-lookup"><span data-stu-id="05beb-107">[SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) and [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) are processed by ODBC Driver Manager, not an individual driver.</span></span> <span data-ttu-id="05beb-108">El Administrador de controladores ODBC no almacena en memoria caché los campos de diagnóstico específicos del controlador hasta que no se ha realizado una conexión correcta.</span><span class="sxs-lookup"><span data-stu-id="05beb-108">ODBC Driver Manager does not cache driver-specific diagnostic fields until a successful connection has been made.</span></span> <span data-ttu-id="05beb-109">No se puede llamar a [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) para los campos de diagnóstico específicos del controlador antes de que la conexión no sea correcta.</span><span class="sxs-lookup"><span data-stu-id="05beb-109">Calling [SQLGetDiagField](../native-client-odbc-api/sqlgetdiagfield.md) for driver-specific diagnostic fields is not possible before a successful connection.</span></span> <span data-ttu-id="05beb-110">Esto incluye los comandos de conexión ODBC, aun cuando devuelvan SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="05beb-110">This includes the ODBC connection commands, even if they return SQL_SUCCESS_WITH_INFO.</span></span> <span data-ttu-id="05beb-111">Los campos de diagnóstico específicos del controlador no estarán disponibles hasta la llamada a función de ODBC siguiente.</span><span class="sxs-lookup"><span data-stu-id="05beb-111">Driver-specific diagnostic fields will not be available until the next ODBC function call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05beb-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05beb-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="05beb-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="05beb-113">Description</span></span>  
 <span data-ttu-id="05beb-114">En este ejemplo se muestra un controlador de errores simple que llama a [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) para la información ODBC estándar.</span><span class="sxs-lookup"><span data-stu-id="05beb-114">This sample shows a simple error handler that calls [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) for the standard ODBC information.</span></span> <span data-ttu-id="05beb-115">Después, comprueba si hay una conexión válida y, si la hay, llama a `SQLGetDiagField` para los campos de diagnóstico específicos del controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05beb-115">It then tests for a valid connection, and if one exists, it calls `SQLGetDiagField` for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific diagnostic fields.</span></span> <span data-ttu-id="05beb-116">Este ejemplo no es compatible con IA64.</span><span class="sxs-lookup"><span data-stu-id="05beb-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="05beb-117">Este ejemplo se desarrolló para la versión 3.0 o posterior de ODBC.</span><span class="sxs-lookup"><span data-stu-id="05beb-117">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="05beb-118">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="05beb-118">When possible, use Windows Authentication.</span></span> <span data-ttu-id="05beb-119">Si la autenticación de Windows no está disponible, solicite a los usuarios que escriban sus credenciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05beb-119">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="05beb-120">No guarde las credenciales en un archivo.</span><span class="sxs-lookup"><span data-stu-id="05beb-120">Avoid storing credentials in a file.</span></span> <span data-ttu-id="05beb-121">Si debe conservar las credenciales, debe cifrarlas con la [API Crypto de Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="05beb-121">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
 <span data-ttu-id="05beb-122">Necesitará un origen de datos ODBC denominado AdventureWorks, cuya base de datos predeterminada sea la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="05beb-122">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="05beb-123">(Puede descargar la base de datos de ejemplo AdventureWorks de la Página principal de [ejemplos y proyectos](https://go.microsoft.com/fwlink/?LinkID=85384) de la comunidad de Microsoft SQL Server). Este origen de datos debe estar basado en el controlador ODBC proporcionado por el sistema operativo (el nombre del controlador es "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="05beb-123">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="05beb-124">Si genera y ejecuta este ejemplo como una aplicación de 32 bits en un sistema operativo de 64 bits, debe crear el origen de datos ODBC con el Administrador ODBC en %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="05beb-124">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="05beb-125">Este ejemplo se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="05beb-125">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="05beb-126">Para conectarse a una instancia con nombre, cambie la definición del origen de datos ODBC para especificar la instancia utilizando el formato servidor\instanciaConNombre.</span><span class="sxs-lookup"><span data-stu-id="05beb-126">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="05beb-127">De forma predeterminada, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="05beb-127">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="05beb-128">Ejecute el primer fragmento de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para crear el procedimiento almacenado utilizado en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="05beb-128">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the stored procedure used by this sample.</span></span>  
  
 <span data-ttu-id="05beb-129">Compile el segundo fragmento de código (C++) con odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="05beb-129">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="05beb-130">A continuación, ejecute el programa.</span><span class="sxs-lookup"><span data-stu-id="05beb-130">Then, execute the program.</span></span>  
  
 <span data-ttu-id="05beb-131">Ejecute el tercer fragmento de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para eliminar el procedimiento almacenado que se usa en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="05beb-131">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the stored procedure used by this sample.</span></span>  
  
### <a name="code"></a><span data-ttu-id="05beb-132">Código</span><span class="sxs-lookup"><span data-stu-id="05beb-132">Code</span></span>  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BadOne')  
   DROP PROCEDURE BadOne  
  
Go  
  
CREATE PROCEDURE BadOne   
AS   
SELECT * FROM Purchasing.Vendor  
Go  
```  
  
### <a name="code"></a><span data-ttu-id="05beb-133">Código</span><span class="sxs-lookup"><span data-stu-id="05beb-133">Code</span></span>  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 256  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;       
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void ProcessLogMessages(SQLSMALLINT plm_handle_type, SQLHANDLE plm_handle, char *logstring, int ConnInd);  
  
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
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER)SQL_OV_ODBC3, SQL_IS_INTEGER);  
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
  
   // This sample use Integrated Security. Please create the SQL Server   
   // DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) &&  
      (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         ProcessLogMessages(SQL_HANDLE_DBC, hdbc1, "SQLConnect() Failed\n\n", FALSE);  
         Cleanup();  
         return(9);  
   }  
   else {  
      ProcessLogMessages(SQL_HANDLE_DBC, hdbc1,  
         "\nConnect Successful\n\n", FALSE);  
   }  
  
   // Allocate statement handle, and then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      ProcessLogMessages(SQL_HANDLE_DBC, hdbc1, "SQLAllocHandle(hstmt1) Failed\n\n", TRUE);  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"exec BadOne", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         ProcessLogMessages(SQL_HANDLE_STMT, hstmt1, "SQLExecute() Failed\n\n", TRUE);  
         Cleanup();  
         return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA )  
      ;  
  
   // Clean up.   
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
void ProcessLogMessages(SQLSMALLINT plm_handle_type, SQLHANDLE plm_handle, char *logstring, int ConnInd) {  
   RETCODE plm_retcode = SQL_SUCCESS;  
   UCHAR plm_szSqlState[MAXBUFLEN] = "", plm_szErrorMsg[MAXBUFLEN] = "";  
   SDWORD plm_pfNativeError = 0L;  
   SWORD plm_pcbErrorMsg = 0;  
   SQLSMALLINT plm_cRecNmbr = 1;  
   SDWORD plm_SS_MsgState = 0, plm_SS_Severity = 0;  
   SQLINTEGER plm_Rownumber = 0;  
   USHORT plm_SS_Line;  
   SQLSMALLINT plm_cbSS_Procname, plm_cbSS_Srvname;  
   SQLCHAR plm_SS_Procname[MAXNAME], plm_SS_Srvname[MAXNAME];  
  
   if (logstring)  
      printf(logstring);  
  
   while (plm_retcode != SQL_NO_DATA_FOUND) {  
      plm_retcode = SQLGetDiagRec(plm_handle_type, plm_handle, plm_cRecNmbr,   
                                  plm_szSqlState, &plm_pfNativeError, plm_szErrorMsg,   
                                  MAXBUFLEN - 1, &plm_pcbErrorMsg);  
  
      // Note that if the application has not yet made a successful connection,   
      // the SQLGetDiagField information has not yet been cached by ODBC Driver Manager and   
      // these calls to SQLGetDiagField will fail.  
      if (plm_retcode != SQL_NO_DATA_FOUND) {  
         if (ConnInd) {   
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                                        SQL_DIAG_ROW_NUMBER, &plm_Rownumber,  
                                                        SQL_IS_INTEGER, NULL);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                           SQL_DIAG_SS_LINE, &plm_SS_Line, SQL_IS_INTEGER, NULL);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,   
                                           SQL_DIAG_SS_MSGSTATE, &plm_SS_MsgState,  
                                           SQL_IS_INTEGER, NULL);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                           SQL_DIAG_SS_SEVERITY, &plm_SS_Severity,  
                                           SQL_IS_INTEGER, NULL);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                           SQL_DIAG_SS_PROCNAME, &plm_SS_Procname,  
                                           sizeof(plm_SS_Procname), &plm_cbSS_Procname);  
  
            plm_retcode = SQLGetDiagField( plm_handle_type, plm_handle, plm_cRecNmbr,  
                                           SQL_DIAG_SS_SRVNAME, &plm_SS_Srvname,   
                                           sizeof(plm_SS_Srvname), &plm_cbSS_Srvname);  
         }  
  
         printf("szSqlState = %s\n", plm_szSqlState);  
         printf("pfNativeError = %d\n", plm_pfNativeError);  
         printf("szErrorMsg = %s\n", plm_szErrorMsg);  
         printf("pcbErrorMsg = %d\n\n", plm_pcbErrorMsg);  
  
         if (ConnInd) {  
            printf("ODBCRowNumber = %d\n", plm_Rownumber);  
            printf("SSrvrLine = %d\n", plm_Rownumber);  
            printf("SSrvrMsgState = %d\n", plm_SS_MsgState);  
            printf("SSrvrSeverity = %d\n", plm_SS_Severity);  
            printf("SSrvrProcname = %s\n", plm_SS_Procname);  
            printf("SSrvrSrvname = %s\n\n", plm_SS_Srvname);  
         }  
      }  
  
      plm_cRecNmbr++;   // Increment to next diagnostic record.  
   }  
}  
```  
  
### <a name="code"></a><span data-ttu-id="05beb-134">Código</span><span class="sxs-lookup"><span data-stu-id="05beb-134">Code</span></span>  
  
```  
use AdventureWorks  
DROP PROCEDURE BadOne  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="05beb-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05beb-135">See Also</span></span>  
 [<span data-ttu-id="05beb-136">Temas de procedimientos de ODBC</span><span class="sxs-lookup"><span data-stu-id="05beb-136">ODBC How-to Topics</span></span>](odbc-how-to-topics.md)  
  
  
