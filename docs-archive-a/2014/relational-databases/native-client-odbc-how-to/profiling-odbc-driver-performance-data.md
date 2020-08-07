---
title: Datos de rendimiento del controlador de perfil (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- driver performance data [ODBC]
ms.assetid: b997790a-8cc6-4800-8867-74c1bef07be3
author: rothja
ms.author: jroth
ms.openlocfilehash: 3575cfd304d526bdb25eee6a2578d67c6bb67bc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745282"
---
# <a name="profile-driver-performance-data-odbc"></a><span data-ttu-id="75bcf-102">Crear perfiles de datos de rendimiento del controlador (ODBC)</span><span class="sxs-lookup"><span data-stu-id="75bcf-102">Profile Driver Performance Data (ODBC)</span></span>
  <span data-ttu-id="75bcf-103">En este ejemplo se muestran las opciones específicas del controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para registrar estadísticas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to record performance statistics.</span></span> <span data-ttu-id="75bcf-104">En el ejemplo se crea un archivo: odbcperf.log. En este ejemplo se muestra la creación de un registro de datos de rendimiento y se muestran estos datos directamente a partir de la estructura de datos SQLPERF (la estructura de datos SQLPERF se define en Odbcss.h).</span><span class="sxs-lookup"><span data-stu-id="75bcf-104">The sample creates one file: odbcperf.log.This sample shows both the creation of a performance data log file and displaying performance data directly from the SQLPERF data structure (The SQLPERF structure is defined in Odbcss.h.).</span></span> <span data-ttu-id="75bcf-105">Este ejemplo se desarrolló para la versión 3.0 o posterior de ODBC.</span><span class="sxs-lookup"><span data-stu-id="75bcf-105">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="75bcf-106">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="75bcf-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="75bcf-107">Si la autenticación de Windows no está disponible, solicite a los usuarios que escriban sus credenciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="75bcf-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="75bcf-108">No guarde las credenciales en un archivo.</span><span class="sxs-lookup"><span data-stu-id="75bcf-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="75bcf-109">Si debe conservar las credenciales, debe cifrarlas con la [API Crypto de Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="75bcf-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-driver-performance-data-using-odbc-administrator"></a><span data-ttu-id="75bcf-110">Para registrar los datos de rendimiento del controlador mediante el Administrador ODBC</span><span class="sxs-lookup"><span data-stu-id="75bcf-110">To log driver performance data using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="75bcf-111">En el **Panel de control**, haga doble clic en **herramientas administrativas** y, a continuación, haga doble clic en **orígenes de datos (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="75bcf-111">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="75bcf-112">De modo alternativo, puede invocar odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="75bcf-112">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="75bcf-113">Haga clic en la pestaña **DSN de usuario**, **DSN de sistema**o DSN de **archivo** .</span><span class="sxs-lookup"><span data-stu-id="75bcf-113">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="75bcf-114">Haga clic en el origen de datos para el que desea registrar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-114">Click the data source for which to log performance.</span></span>  
  
4.  <span data-ttu-id="75bcf-115">Haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="75bcf-115">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="75bcf-116">En el Asistente para configurar DSN de Microsoft SQL Server, vaya a la página con el **registro de estadísticas del controlador ODBC de registro en el archivo de registro**.</span><span class="sxs-lookup"><span data-stu-id="75bcf-116">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Log ODBC driver statistics to the log file**.</span></span>  
  
6.  <span data-ttu-id="75bcf-117">Seleccione **registrar estadísticas del controlador ODBC en el archivo de registro**.</span><span class="sxs-lookup"><span data-stu-id="75bcf-117">Select **Log ODBC driver statistics to the log file**.</span></span> <span data-ttu-id="75bcf-118">En el cuadro, incluya el nombre del archivo donde se deben registrar las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="75bcf-118">In the box, place the name of the file where the statistics should be logged.</span></span> <span data-ttu-id="75bcf-119">Opcionalmente, haga clic en **examinar** para buscar el registro de estadísticas en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="75bcf-119">Optionally, click **Browse** to browse the file system for the statistics log.</span></span>  
  
### <a name="to-log-driver-performance-data-programmatically"></a><span data-ttu-id="75bcf-120">Para registrar mediante programación los datos de rendimiento del controlador</span><span class="sxs-lookup"><span data-stu-id="75bcf-120">To log driver performance data programmatically</span></span>  
  
1.  <span data-ttu-id="75bcf-121">Llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA_LOG y la ruta de acceso completa y el nombre de archivo del archivo de registro de datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-121">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA_LOG and the full path and file name of the performance data log file.</span></span> <span data-ttu-id="75bcf-122">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="75bcf-122">For example:</span></span>  
  
    ```  
    "C:\\Odbcperf.log"  
    ```  
  
2.  <span data-ttu-id="75bcf-123">Llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA y SQL_PERF_START para iniciar el registro de datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start logging performance data.</span></span>  
  
3.  <span data-ttu-id="75bcf-124">Opcionalmente, llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_LOG_NOW y null para escribir un registro delimitado por tabuladores de datos de rendimiento en el archivo de registro de datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-124">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_LOG_NOW and NULL to write a tab-delimited record of performance data to the performance data log file.</span></span> <span data-ttu-id="75bcf-125">Esto se puede hacer varias veces cuando se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75bcf-125">This can be done multiple times as the application runs.</span></span>  
  
4.  <span data-ttu-id="75bcf-126">Llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA y SQL_PERF_STOP para detener el registro de datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
### <a name="to-pull-driver-performance-data-into-an-application"></a><span data-ttu-id="75bcf-127">Para extraer los datos de rendimiento del controlador en una aplicación</span><span class="sxs-lookup"><span data-stu-id="75bcf-127">To pull driver performance data into an application</span></span>  
  
1.  <span data-ttu-id="75bcf-128">Llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA y SQL_PERF_START para iniciar la generación de perfiles de datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-128">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start profiling performance data.</span></span>  
  
2.  <span data-ttu-id="75bcf-129">Llame a [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) con SQL_COPT_SS_PERF_DATA y la dirección de un puntero a una estructura SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="75bcf-129">Call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) with SQL_COPT_SS_PERF_DATA and the address of a pointer to a SQLPERF structure.</span></span> <span data-ttu-id="75bcf-130">La primera vez dicha llamada establece el puntero en la dirección de una estructura SQLPERF válida que contiene los datos de rendimiento actuales.</span><span class="sxs-lookup"><span data-stu-id="75bcf-130">The first such call sets the pointer to the address of a valid SQLPERF structure that contains current performance data.</span></span> <span data-ttu-id="75bcf-131">El controlador no actualiza continuamente los datos de la estructura de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-131">The driver does not continually refresh the data in the performance structure.</span></span> <span data-ttu-id="75bcf-132">La aplicación debe repetir la llamada a [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) cada vez que necesite actualizar la estructura con datos de rendimiento más actuales.</span><span class="sxs-lookup"><span data-stu-id="75bcf-132">The application must repeat the call to [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) any time it needs to refresh the structure with more current performance data.</span></span>  
  
3.  <span data-ttu-id="75bcf-133">Llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) con SQL_COPT_SS_PERF_DATA y SQL_PERF_STOP para detener el registro de datos de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="75bcf-133">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75bcf-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75bcf-134">Example</span></span>  
 <span data-ttu-id="75bcf-135">Necesitará un origen de datos ODBC denominado AdventureWorks, cuya base de datos predeterminada sea la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="75bcf-135">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="75bcf-136">(Puede descargar la base de datos de ejemplo AdventureWorks de la Página principal de [ejemplos y proyectos](https://go.microsoft.com/fwlink/?LinkID=85384) de la comunidad de Microsoft SQL Server). Este origen de datos debe estar basado en el controlador ODBC proporcionado por el sistema operativo (el nombre del controlador es "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="75bcf-136">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="75bcf-137">Si genera y ejecuta este ejemplo como una aplicación de 32 bits en un sistema operativo de 64 bits, debe crear el origen de datos ODBC con el Administrador ODBC en %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="75bcf-137">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="75bcf-138">Este ejemplo se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="75bcf-138">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="75bcf-139">Para conectarse a una instancia con nombre, cambie la definición del origen de datos ODBC para especificar la instancia utilizando el formato servidor\instanciaConNombre.</span><span class="sxs-lookup"><span data-stu-id="75bcf-139">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="75bcf-140">De forma predeterminada, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="75bcf-140">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="75bcf-141">Compilación con odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="75bcf-141">Compile with odbc32.lib.</span></span>  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
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
  
   // Pointer to the ODBC driver performance structure.  
   SQLPERF *PerfPtr;  
   SQLINTEGER cbPerfPtr;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
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
  
   // This sample use Integrated Security. Please create the SQL Server   
   // DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log performance statistics.  Specify file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG, &"odbcperf.log", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the performance statistics log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Write current statistics to the performance log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG_NOW, (SQLPOINTER)NULL, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get pointer to current SQLPerf structure.  
   // Print a couple of statistics.  
   retcode =   
      SQLGetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)&PerfPtr, SQL_IS_POINTER, &cbPerfPtr);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLGetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("SQLSelects = %d, SQLSelectRows = %d\n", PerfPtr->SQLSelects, PerfPtr->SQLSelectRows);  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="75bcf-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="75bcf-142">See Also</span></span>  
 <span data-ttu-id="75bcf-143">[Temas de procedimientos de generación de perfiles de rendimiento del controlador ODBC &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="75bcf-143">[Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span></span>  
 [<span data-ttu-id="75bcf-144">Generar perfiles del rendimiento del controlador ODBC</span><span class="sxs-lookup"><span data-stu-id="75bcf-144">Profiling ODBC Driver Performance</span></span>](../native-client/odbc/profiling-odbc-driver-performance.md)  
  
  
