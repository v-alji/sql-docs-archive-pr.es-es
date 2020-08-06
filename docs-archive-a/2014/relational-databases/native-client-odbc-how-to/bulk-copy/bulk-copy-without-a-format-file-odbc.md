---
title: Copia masiva sin un archivo de formato (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC]
- bulk copy [ODBC], data files
- bulk copy [ODBC], about bulk copy
ms.assetid: 4ee969a7-44ba-40d0-b9ab-8306f1a2b19d
author: rothja
ms.author: jroth
ms.openlocfilehash: a65f013d92f5a5d39a580cfb3a9bd77bc6f84e9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750886"
---
# <a name="bulk-copy-without-a-format-file-odbc"></a><span data-ttu-id="99c9f-102">Realizar una copia masiva sin un archivo de formato (ODBC)</span><span class="sxs-lookup"><span data-stu-id="99c9f-102">Bulk Copy Without a Format File (ODBC)</span></span>
  <span data-ttu-id="99c9f-103">Este ejemplo muestra cómo utilizar las funciones de copia masiva para crear un archivo de datos de modo nativo, sin archivo de formato.</span><span class="sxs-lookup"><span data-stu-id="99c9f-103">This sample shows how to use bulk copy functions to create a native mode data file, without a format file.</span></span> <span data-ttu-id="99c9f-104">Este ejemplo se desarrolló para la versión 3.0 o posterior de ODBC.</span><span class="sxs-lookup"><span data-stu-id="99c9f-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="99c9f-105">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="99c9f-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="99c9f-106">Si la autenticación de Windows no está disponible, solicite a los usuarios que escriban sus credenciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="99c9f-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="99c9f-107">No guarde las credenciales en un archivo.</span><span class="sxs-lookup"><span data-stu-id="99c9f-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="99c9f-108">Si debe conservar las credenciales, debe cifrarlas con la [API Crypto de Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="99c9f-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-bulk-copy-without-a-format-file"></a><span data-ttu-id="99c9f-109">Para realizar una copia masiva sin un archivo de formato</span><span class="sxs-lookup"><span data-stu-id="99c9f-109">To bulk copy without a format file</span></span>  
  
1.  <span data-ttu-id="99c9f-110">Asigne un identificador de entorno y un identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="99c9f-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="99c9f-111">Establezca SQL_COPT_SS_BCP y SQL_BCP_ON para habilitar las operaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="99c9f-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="99c9f-112">Conéctese a SQL Server.</span><span class="sxs-lookup"><span data-stu-id="99c9f-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="99c9f-113">Llame a [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) para establecer la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="99c9f-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="99c9f-114">El nombre de la tabla o vista desde la que se realizará la copia masiva o en la que se realizará la copia masiva.</span><span class="sxs-lookup"><span data-stu-id="99c9f-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="99c9f-115">El nombre del archivo de datos que contiene los datos que van a copiarse en la base de datos o que recibe los datos cuando se realiza una copia desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="99c9f-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="99c9f-116">El nombre de un archivo de datos donde recibir cualquier mensaje de error de la copia masiva (especifique NULL si no desea ningún archivo de mensajes).</span><span class="sxs-lookup"><span data-stu-id="99c9f-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="99c9f-117">La dirección de la copia: DB_IN desde el archivo a la vista o tabla o DB_OUT al archivo desde la tabla o vista.</span><span class="sxs-lookup"><span data-stu-id="99c9f-117">The direction of the copy: DB_IN from the file to the view or table, or DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="99c9f-118">Llame a [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) para ejecutar la operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="99c9f-118">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="99c9f-119">Cuando DB_OUT se establece con estos pasos, el archivo se crea en formato nativo.</span><span class="sxs-lookup"><span data-stu-id="99c9f-119">When DB_OUT is set with these steps, the file is created in native format.</span></span> <span data-ttu-id="99c9f-120">A continuación, se puede realizar la copia masiva del archivo a un servidor si se siguen estos mismos pasos, excepto que se establece DB_OUT en lugar de DB_IN.</span><span class="sxs-lookup"><span data-stu-id="99c9f-120">The file can then be bulk copied into a server by following these same steps, except that DB_OUT is set instead of DB_IN.</span></span> <span data-ttu-id="99c9f-121">Esto solamente funciona si las tablas de destino y origen tienen exactamente la misma estructura.</span><span class="sxs-lookup"><span data-stu-id="99c9f-121">This works only if both the source and target tables have exactly the same structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99c9f-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99c9f-122">Example</span></span>  
 <span data-ttu-id="99c9f-123">Este ejemplo no es compatible con IA64.</span><span class="sxs-lookup"><span data-stu-id="99c9f-123">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="99c9f-124">Necesitará un origen de datos ODBC denominado AdventureWorks, cuya base de datos predeterminada sea la base de datos de ejemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="99c9f-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="99c9f-125">(Puede descargar la base de datos de ejemplo AdventureWorks de la Página principal de [ejemplos y proyectos](https://go.microsoft.com/fwlink/?LinkID=85384) de la comunidad de Microsoft SQL Server). Este origen de datos debe estar basado en el controlador ODBC proporcionado por el sistema operativo (el nombre del controlador es "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="99c9f-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="99c9f-126">Si genera y ejecuta este ejemplo como una aplicación de 32 bits en un sistema operativo de 64 bits, debe crear el origen de datos ODBC con el Administrador ODBC en %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="99c9f-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="99c9f-127">Este ejemplo se conecta a la instancia predeterminada de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] del equipo.</span><span class="sxs-lookup"><span data-stu-id="99c9f-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="99c9f-128">Para conectarse a una instancia con nombre, cambie la definición del origen de datos ODBC para especificar la instancia utilizando el formato servidor\instanciaConNombre.</span><span class="sxs-lookup"><span data-stu-id="99c9f-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="99c9f-129">De forma predeterminada, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] se instala en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="99c9f-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="99c9f-130">Compile con odbc32.lib y odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="99c9f-130">Compile with odbc32.lib and odbcbcp.lib.</span></span>  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define MAXBUFLEN 256  
  
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
  
   // Bulk copy variables.  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and then connect.  
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
  
   // Sample uses Integrated Security, create the SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "Purchasing.Vendor", "BCPODBC.bcp", "BCPERROR.out", DB_OUT);  
   // Test is for the bulk copy return of SUCCEED, not the ODBC return of SQL_SUCCESS.  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
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
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="99c9f-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99c9f-131">See Also</span></span>  
 [<span data-ttu-id="99c9f-132">Temas de procedimientos de la copia masiva con el controlador ODBC de SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="99c9f-132">Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;</span></span>](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md)  
  
  
