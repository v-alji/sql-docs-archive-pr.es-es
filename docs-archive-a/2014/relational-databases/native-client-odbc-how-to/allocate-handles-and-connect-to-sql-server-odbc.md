---
title: Asignar identificadores y conectarse a SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- handles [ODBC]
- handles [ODBC], connection
- handles [ODBC], about handles
ms.assetid: 6172cd52-9c9a-467d-992f-def07f3f3bb1
author: rothja
ms.author: jroth
ms.openlocfilehash: 615a6dbe966b4c681e9cd4285ff55864d7a13370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750902"
---
# <a name="allocate-handles-and-connect-to-sql-server-odbc"></a><span data-ttu-id="29a8e-102">Asignar identificadores y conectarse a SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="29a8e-102">Allocate Handles and Connect to SQL Server (ODBC)</span></span>
    
### <a name="to-allocate-handles-and-connect-to-sql-server"></a><span data-ttu-id="29a8e-103">Para asignar los identificadores y conectarse a SQL Server</span><span class="sxs-lookup"><span data-stu-id="29a8e-103">To allocate handles and connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="29a8e-104">Incluya los archivos de encabezado ODBC Sql.h, Sqlext.h, Sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="29a8e-104">Include the ODBC header files Sql.h, Sqlext.h, Sqltypes.h.</span></span>  
  
2.  <span data-ttu-id="29a8e-105">Incluya el archivo de encabezado específico del controlador [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Odbcss.h.</span><span class="sxs-lookup"><span data-stu-id="29a8e-105">Include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver-specific header file, Odbcss.h.</span></span>  
  
3.  <span data-ttu-id="29a8e-106">Llame a [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) con un `HandleType` de SQL_HANDLE_ENV para inicializar ODBC y asignar un identificador de entorno.</span><span class="sxs-lookup"><span data-stu-id="29a8e-106">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_ENV to initialize ODBC and allocate an environment handle.</span></span>  
  
4.  <span data-ttu-id="29a8e-107">Llame a [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) con `Attribute` establecido en SQL_ATTR_ODBC_VERSION y `ValuePtr` establezca en SQL_OV_ODBC3 para indicar que la aplicación usará las llamadas de función de formato ODBC 3. x.</span><span class="sxs-lookup"><span data-stu-id="29a8e-107">Call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with `Attribute` set to SQL_ATTR_ODBC_VERSION and `ValuePtr` set to SQL_OV_ODBC3 to indicate the application will use ODBC 3.x-format function calls.</span></span>  
  
5.  <span data-ttu-id="29a8e-108">Opcionalmente, llame a [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) para establecer otras opciones de entorno, o llame a [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) para obtener opciones de entorno.</span><span class="sxs-lookup"><span data-stu-id="29a8e-108">Optionally, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) to set other environment options, or call [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) to get environment options.</span></span>  
  
6.  <span data-ttu-id="29a8e-109">Llame a [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) con un `HandleType` de SQL_HANDLE_DBC para asignar un identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="29a8e-109">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_DBC to allocate a connection handle.</span></span>  
  
7.  <span data-ttu-id="29a8e-110">Opcionalmente, llame a [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) para establecer las opciones de conexión o llame a [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) para obtener las opciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="29a8e-110">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set connection options, or call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) to get connection options.</span></span>  
  
8.  <span data-ttu-id="29a8e-111">Llame a SQLConnect para usar un origen de datos existente con el que conectarse [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29a8e-111">Call SQLConnect to use an existing data source to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="29a8e-112">Or</span><span class="sxs-lookup"><span data-stu-id="29a8e-112">Or</span></span>  
  
     <span data-ttu-id="29a8e-113">Llame a [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) para usar una cadena de conexión para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29a8e-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) to use a connection string to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="29a8e-114">Una cadena de conexión [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] completa mínima tiene uno de dos formatos:</span><span class="sxs-lookup"><span data-stu-id="29a8e-114">A minimum complete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection string has one of two forms:</span></span>  
  
    ```  
    DSN=dsn_name;Trusted_connection=yes;  
    DRIVER={SQL Server Native Client 10.0};SERVER=server;Trusted_connection=yes;  
    ```  
  
     <span data-ttu-id="29a8e-115">Si la cadena de conexión no se ha completado, `SQLDriverConnect` puede solicitar la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="29a8e-115">If the connection string is not complete, `SQLDriverConnect` can prompt for the required information.</span></span> <span data-ttu-id="29a8e-116">Esto se controla mediante el valor especificado para el parámetro *DriverCompletion* .</span><span class="sxs-lookup"><span data-stu-id="29a8e-116">This is controlled by the value specified for the *DriverCompletion* parameter.</span></span>  
  
     <span data-ttu-id="29a8e-117">\- o -</span><span class="sxs-lookup"><span data-stu-id="29a8e-117">\- or -</span></span>  
  
     <span data-ttu-id="29a8e-118">Llame a [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) varias veces de manera iterativa para compilar la cadena de conexión y conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="29a8e-118">Call [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) multiple times in an iterative fashion to build the connection string and connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="29a8e-119">Opcionalmente, llame a [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) para obtener los atributos y el comportamiento del controlador para el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] origen de datos.</span><span class="sxs-lookup"><span data-stu-id="29a8e-119">Optionally, call [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) to get driver attributes and behavior for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source.</span></span>  
  
10. <span data-ttu-id="29a8e-120">Asigne y utilice las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="29a8e-120">Allocate and use statements.</span></span>  
  
11. <span data-ttu-id="29a8e-121">Llame a SQLDisconnect para desconectarse [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y hacer que el identificador de conexión esté disponible para una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="29a8e-121">Call SQLDisconnect to disconnect from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and make the connection handle available for a new connection.</span></span>  
  
12. <span data-ttu-id="29a8e-122">Llame a [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) con un `HandleType` de SQL_HANDLE_DBC para liberar el identificador de conexión.</span><span class="sxs-lookup"><span data-stu-id="29a8e-122">Call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) with a `HandleType` of SQL_HANDLE_DBC to free the connection handle.</span></span>  
  
13. <span data-ttu-id="29a8e-123">Llame a `SQLFreeHandle` con un `HandleType` de SQL_HANDLE_ENV para liberar el identificador del entorno.</span><span class="sxs-lookup"><span data-stu-id="29a8e-123">Call `SQLFreeHandle` with a `HandleType` of SQL_HANDLE_ENV to free the environment handle.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="29a8e-124">Siempre que sea posible, utilice la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="29a8e-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="29a8e-125">Si la autenticación de Windows no está disponible, solicite a los usuarios que escriban sus credenciales en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="29a8e-125">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="29a8e-126">No guarde las credenciales en un archivo.</span><span class="sxs-lookup"><span data-stu-id="29a8e-126">Avoid storing credentials in a file.</span></span> <span data-ttu-id="29a8e-127">Si debe conservar las credenciales, debe cifrarlas con la [API Crypto de Win32](https://go.microsoft.com/fwlink/?LinkId=64532).</span><span class="sxs-lookup"><span data-stu-id="29a8e-127">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29a8e-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29a8e-128">Example</span></span>  
 <span data-ttu-id="29a8e-129">En este ejemplo se muestra una llamada a `SQLDriverConnect` para conectarse a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sin necesidad de un origen de datos ODBC existente.</span><span class="sxs-lookup"><span data-stu-id="29a8e-129">This example shows a call to `SQLDriverConnect` to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without requiring an existing ODBC data source.</span></span> <span data-ttu-id="29a8e-130">El paso de una cadena de conexión incompleta a `SQLDriverConnect`, hace que el controlador ODBC solicite al usuario que escriba la información que falta.</span><span class="sxs-lookup"><span data-stu-id="29a8e-130">By passing an incomplete connection string to `SQLDriverConnect`, it causes the ODBC driver to prompt the user to enter the missing information.</span></span>  
  
```  
#define MAXBUFLEN   255  
  
SQLHENV      henv = SQL_NULL_HENV;  
SQLHDBC      hdbc1 = SQL_NULL_HDBC;  
SQLHSTMT      hstmt1 = SQL_NULL_HSTMT;  
  
SQLCHAR      ConnStrIn[MAXBUFLEN] =  
         "DRIVER={SQL Server Native Client 10.0};SERVER=MyServer";  
  
SQLCHAR      ConnStrOut[MAXBUFLEN];  
SQLSMALLINT   cbConnStrOut = 0;  
  
// Make connection without data source. Ask that driver   
// prompt if insufficient information. Driver returns  
// SQL_ERROR and application prompts user  
// for missing information. Window handle not needed for  
// SQL_DRIVER_NOPROMPT.  
retcode = SQLDriverConnect(hdbc1,      // Connection handle  
                  NULL,         // Window handle  
                  ConnStrIn,      // Input connect string  
                  SQL_NTS,         // Null-terminated string  
                  ConnStrOut,      // Address of output buffer  
                  MAXBUFLEN,      // Size of output buffer  
                  &cbConnStrOut,   // Address of output length  
                  SQL_DRIVER_PROMPT);  
```  
  
  
