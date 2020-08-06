---
title: Copia masiva mediante un archivo de formato (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy using format file [ODBC]
- ODBC, bulk copy operations
ms.assetid: 970fd3af-f918-4fc3-a5b1-92596515d4de
author: rothja
ms.author: jroth
ms.openlocfilehash: 19959d5f1da7243275c60560963d577446f809b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750897"
---
# <a name="bulk-copy-by-using-a-format-file-odbc"></a><span data-ttu-id="b5bcf-102">Realizar una copia masiva con un archivo de formato (ODBC)</span><span class="sxs-lookup"><span data-stu-id="b5bcf-102">Bulk Copy by Using a Format File (ODBC)</span></span>
  <span data-ttu-id="b5bcf-103">En este ejemplo se muestra cómo se usa la función ODBC bcp_init con un archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-103">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
### <a name="to-bulk-copy-by-using-a-format-file"></a><span data-ttu-id="b5bcf-104">Para realizar una copia masiva con un archivo de formato</span><span class="sxs-lookup"><span data-stu-id="b5bcf-104">To bulk copy by using a format file</span></span>  
  
1.  <span data-ttu-id="b5bcf-105">Asigne un identificador de entorno y un identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-105">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="b5bcf-106">Establezca SQL_COPT_SS_BCP y SQL_BCP_ON para habilitar las operaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-106">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="b5bcf-107">Conéctese a Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-107">Connect to Microsoft SQL Server.</span></span>  
  
4.  <span data-ttu-id="b5bcf-108">Llame a [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) para establecer la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="b5bcf-108">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="b5bcf-109">El nombre de la tabla o vista desde la que se realizará la copia masiva o en la que se realizará la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-109">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="b5bcf-110">El nombre del archivo de datos que contiene los datos que van a copiarse en la base de datos o que recibe los datos cuando se realiza una copia desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-110">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="b5bcf-111">El nombre de un archivo de datos donde recibir cualquier mensaje de error de la copia masiva (especifique NULL si no desea ningún archivo de mensajes).</span><span class="sxs-lookup"><span data-stu-id="b5bcf-111">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="b5bcf-112">La dirección de la copia: DB_IN al archivo desde la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-112">The direction of the copy: DB_IN from the file to the table or view.</span></span>  
  
5.  <span data-ttu-id="b5bcf-113">Llame a [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) para leer el archivo de formato que describe el archivo de datos que se va a usar en la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-113">Call [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) to read the format file describing the data file to be used by the bulk copy operation.</span></span>  
  
6.  <span data-ttu-id="b5bcf-114">Llame a [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) para ejecutar la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-114">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5bcf-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5bcf-115">Example</span></span>  
 <span data-ttu-id="b5bcf-116">Este ejemplo no es compatible con IA64.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="b5bcf-117">Necesitará un origen de datos ODBC denominado AdventureWorks, cuya base de datos predeterminada sea la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="b5bcf-118">(Puede descargar la base de datos de ejemplo AdventureWorks de la Página principal de [ejemplos y proyectos](https://go.microsoft.com/fwlink/?LinkID=85384) de la comunidad de Microsoft SQL Server). Este origen de datos debe estar basado en el controlador ODBC proporcionado por el sistema operativo (el nombre del controlador es "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="b5bcf-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="b5bcf-119">Si genera y ejecuta este ejemplo como una aplicación de 32 bits en un sistema operativo de 64 bits, debe crear el origen de datos ODBC con el Administrador ODBC en %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="b5bcf-120">Este ejemplo se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="b5bcf-121">Para conectarse a una instancia con nombre, cambie la definición del origen de datos ODBC para especificar la instancia utilizando el formato servidor\instanciaConNombre.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="b5bcf-122">De forma predeterminada, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-122">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="b5bcf-123">Ejecute la primera lista de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para crear la tabla que usará el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-123">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="b5bcf-124">Copie la segunda lista de código y péguela en un archivo denominado Bcpfmt.fmt.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-124">Copy the second code listing and paste it into a file called Bcpfmt.fmt.</span></span> <span data-ttu-id="b5bcf-125">Cada columna de la tabla se separa con un carácter de tabulación.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-125">Each column in the table is separated by a tab character.</span></span>  
  
 <span data-ttu-id="b5bcf-126">Copie la tercera lista de código y péguela en un archivo denominado Bcpodbc.bcp.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-126">Copy the third code listing and paste it into a file called Bcpodbc.bcp.</span></span> <span data-ttu-id="b5bcf-127">Un carácter de tabulación precede a cada retorno de carro en el archivo.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-127">A tab character precedes each carriage return in the file.</span></span>  
  
 <span data-ttu-id="b5bcf-128">Compile la cuarta lista de código (C++) con odbc32.lib y odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-128">Compile the fourth (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span> <span data-ttu-id="b5bcf-129">Si la generación se realizó con MSBuild.exe, copie Bcpfmt.fmt y Bcpodbc.bcp del directorio del proyecto al directorio que contiene el archivo .exe y, a continuación, invóquelo.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-129">If you built with MSBuild.exe, copy Bcpfmt.fmt and Bcpodbc.bcp from the project directory into the directory with the .exe and then invoke the .exe.</span></span>  
  
 <span data-ttu-id="b5bcf-130">Ejecute la quinta lista de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para eliminar la tabla que usó el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b5bcf-130">Execute the fifth ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```sql
use AdventureWorks  
CREATE TABLE BCPDate (cola int, colb datetime)  
```  
  
```  
8.0  
2  
1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
```  
  
```  
1  
2  
```  
  
```cpp
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
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
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```sql
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5bcf-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5bcf-131">See Also</span></span>  
 <span data-ttu-id="b5bcf-132">[Temas de procedimientos de la copia masiva con el controlador ODBC de SQL Server &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="b5bcf-132">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="b5bcf-133">Utilizar archivos de datos y archivos de formato</span><span class="sxs-lookup"><span data-stu-id="b5bcf-133">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
