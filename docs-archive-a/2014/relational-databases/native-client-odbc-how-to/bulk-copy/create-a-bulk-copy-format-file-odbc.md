---
title: Crear un archivo de formato de copia masiva (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC], data files
ms.assetid: 0572fef3-daf5-409e-b557-c2a632f9a06d
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d35342b2f6b25a129df968383d204931d64bfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662892"
---
# <a name="create-a-bulk-copy-format-file-odbc"></a><span data-ttu-id="11fae-102">Crear un archivo de formato de copia masiva (ODBC)</span><span class="sxs-lookup"><span data-stu-id="11fae-102">Create a Bulk Copy Format File (ODBC)</span></span>
  <span data-ttu-id="11fae-103">En este ejemplo se muestra cómo usar las funciones de copia masiva para crear tanto un archivo de datos como un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="11fae-103">This sample shows how to use bulk copy functions to create both a data file and a format file.</span></span> <span data-ttu-id="11fae-104">Este ejemplo se desarrolló para la versión 3.0 o posterior de ODBC.</span><span class="sxs-lookup"><span data-stu-id="11fae-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="11fae-105">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="11fae-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="11fae-106">Si la autenticación de Windows no está disponible, solicite a los usuarios que escriban sus credenciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11fae-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="11fae-107">No guarde las credenciales en un archivo.</span><span class="sxs-lookup"><span data-stu-id="11fae-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="11fae-108">Si debe conservar las credenciales, debe cifrarlas con la [API Crypto de Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="11fae-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-create-a-bulk-copy-format-file"></a><span data-ttu-id="11fae-109">Para crear un archivo de formato de copia masiva</span><span class="sxs-lookup"><span data-stu-id="11fae-109">To create a bulk copy format file</span></span>  
  
1.  <span data-ttu-id="11fae-110">Asigne un identificador de entorno y un identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="11fae-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="11fae-111">Establezca SQL_COPT_SS_BCP y SQL_BCP_ON para habilitar las operaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="11fae-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="11fae-112">Conéctese a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="11fae-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="11fae-113">Llame a [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) para establecer la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="11fae-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="11fae-114">El nombre de la tabla o vista desde la que se realizará la copia masiva o en la que se realizará la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="11fae-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="11fae-115">El nombre del archivo de datos que contiene los datos que van a copiarse en la base de datos o que recibe los datos cuando se realiza una copia desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="11fae-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="11fae-116">El nombre de un archivo de datos donde recibir cualquier mensaje de error de la copia masiva (especifique NULL si no desea ningún archivo de mensajes).</span><span class="sxs-lookup"><span data-stu-id="11fae-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="11fae-117">La dirección de la copia: DB_OUT al archivo desde la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="11fae-117">The direction of the copy: DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="11fae-118">Llame a [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) para establecer el número de columnas.</span><span class="sxs-lookup"><span data-stu-id="11fae-118">Call [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to set the number of columns.</span></span>  
  
6.  <span data-ttu-id="11fae-119">Llame a [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) de cada columna para definir sus características en el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="11fae-119">Call [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column to define its characteristics in the data file.</span></span>  
  
7.  <span data-ttu-id="11fae-120">Llame a [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) para crear un archivo de formato que describa el archivo de datos que va a crear la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="11fae-120">Call [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) to create a format file describing the data file to be created by the bulk copy operation.</span></span>  
  
8.  <span data-ttu-id="11fae-121">Llame a [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) para ejecutar la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="11fae-121">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="11fae-122">Una operación de copia masiva ejecutada de esta forma crea tanto un archivo de datos que contiene los datos copiados de forma masiva como un archivo de formato que describe el diseño del archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="11fae-122">A bulk copy operation run in this way creates both a data file containing the bulk copied data and a format file describing the layout of the data file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11fae-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="11fae-123">Example</span></span>  
 <span data-ttu-id="11fae-124">Necesitará un origen de datos ODBC denominado AdventureWorks, cuya base de datos predeterminada sea la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="11fae-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="11fae-125">(Puede descargar la base de datos de ejemplo AdventureWorks de la Página principal de [ejemplos y proyectos](https://go.microsoft.com/fwlink/?LinkID=85384) de la comunidad de Microsoft SQL Server). Este origen de datos debe estar basado en el controlador ODBC proporcionado por el sistema operativo (el nombre del controlador es "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="11fae-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="11fae-126">Si genera y ejecuta este ejemplo como una aplicación de 32 bits en un sistema operativo de 64 bits, debe crear el origen de datos ODBC con el Administrador ODBC en %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="11fae-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="11fae-127">Este ejemplo se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="11fae-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="11fae-128">Para conectarse a una instancia con nombre, cambie la definición del origen de datos ODBC para especificar la instancia utilizando el formato servidor\instanciaConNombre.</span><span class="sxs-lookup"><span data-stu-id="11fae-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="11fae-129">De forma predeterminada, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="11fae-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="11fae-130">Ejecute la primera lista de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para crear la tabla que usará el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="11fae-130">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="11fae-131">Compile la segunda lista de código (C++) con odbc32.lib y odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="11fae-131">Compile the second (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span>  
  
 <span data-ttu-id="11fae-132">Ejecute la tercer lista de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para eliminar la tabla que usó el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="11fae-132">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```  
use AdventureWorks  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
  
CREATE TABLE BCPDate (cola int, colb datetime)  
insert BCPDate(cola) values(1)   
insert BCPDate(cola) values(2)   
insert BCPDate(cola) values(3)   
insert BCPDate(cola) values(4)  
```  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;    
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
  
   // BCP variables.  
   SDWORD cRows;  
  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
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
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_OUT);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set the number of output columns.  
   retcode = bcp_columns(hdbc1, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 1 in the data file.  
   retcode = bcp_colfmt(hdbc1, 1, SQLCHARACTER, -1, 5, NULL, 0, 1);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 2 in the data file.  
   retcode = bcp_colfmt(hdbc1, 2, SQLCHARACTER, -1, 20, NULL, 0, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Create the format file.  
   retcode = bcp_writefmt(hdbc1, "c:\\BCPFMT.fmt");  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
   return(0);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="11fae-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11fae-133">See Also</span></span>  
 <span data-ttu-id="11fae-134">[Temas de procedimientos de la copia masiva con el controlador ODBC de SQL Server &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="11fae-134">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="11fae-135">Utilizar archivos de datos y archivos de formato</span><span class="sxs-lookup"><span data-stu-id="11fae-135">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
