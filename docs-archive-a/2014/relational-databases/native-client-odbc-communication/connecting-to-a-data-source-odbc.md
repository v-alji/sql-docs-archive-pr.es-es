---
title: Conectar con un origen de datos (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- checking connection states
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- SQLBrowseConnect function
- ODBC applications, connections
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLConnect function
- SQLDriveConnect function
- verifying connection states
- SQL Server Native Client ODBC driver, data sources
- SQL Server Native Client ODBC driver, connections
ms.assetid: ae30dd1d-06ae-452b-9618-8fd8cd7ba074
author: rothja
ms.author: jroth
ms.openlocfilehash: 25ce5954e45bb8070b5e99d8ebb7bfa9ad149c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672939"
---
# <a name="connecting-to-a-data-source-odbc"></a><span data-ttu-id="dc336-102">Conectar con un origen de datos (ODBC)</span><span class="sxs-lookup"><span data-stu-id="dc336-102">Connecting to a Data Source (ODBC)</span></span>
  <span data-ttu-id="dc336-103">Después de asignar el entorno y los identificadores de conexión y establecer los atributos de conexión, la aplicación se conecta al origen de datos o controlador.</span><span class="sxs-lookup"><span data-stu-id="dc336-103">After allocating environment and connection handles and setting any connection attributes, the application connects to the data source or driver.</span></span> <span data-ttu-id="dc336-104">Hay tres funciones que puede utilizar para conectarse:</span><span class="sxs-lookup"><span data-stu-id="dc336-104">There are three functions you can use to connect:</span></span>  
  
-   <span data-ttu-id="dc336-105">**SQLConnect**</span><span class="sxs-lookup"><span data-stu-id="dc336-105">**SQLConnect**</span></span>  
  
-   <span data-ttu-id="dc336-106">**SQLDriverConnect**</span><span class="sxs-lookup"><span data-stu-id="dc336-106">**SQLDriverConnect**</span></span>  
  
-   <span data-ttu-id="dc336-107">**SQLBrowseConnect**</span><span class="sxs-lookup"><span data-stu-id="dc336-107">**SQLBrowseConnect**</span></span>  
  
 <span data-ttu-id="dc336-108">Para obtener más información sobre cómo establecer conexiones a un origen de datos, incluidas las distintas opciones de cadena de conexión disponibles, vea [usar palabras clave de cadena de conexión con SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="dc336-108">For more information about making connections to a data source, including the various connection string options available, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
## <a name="sqlconnect"></a><span data-ttu-id="dc336-109">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="dc336-109">SQLConnect</span></span>  
 <span data-ttu-id="dc336-110">**SQLConnect** es la función de conexión más sencilla.</span><span class="sxs-lookup"><span data-stu-id="dc336-110">**SQLConnect** is the simplest connection function.</span></span> <span data-ttu-id="dc336-111">Acepta tres parámetros: nombre del origen de datos, identificador de usuario y contraseña.</span><span class="sxs-lookup"><span data-stu-id="dc336-111">It accepts three parameters: a data source name, a user ID, and a password.</span></span> <span data-ttu-id="dc336-112">Use **SQLConnect** cuando estos tres parámetros contengan toda la información necesaria para conectarse a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="dc336-112">Use **SQLConnect** when these three parameters contain all the information needed to connect to the database.</span></span> <span data-ttu-id="dc336-113">Para ello, cree una lista de orígenes de datos con **SQLDataSources**; solicitar al usuario un origen de datos, un identificador de usuario y una contraseña; y, a continuación, llame a **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="dc336-113">To do this, build a list of data sources using **SQLDataSources**; prompt the user for a data source, user ID, and password; and then call **SQLConnect**.</span></span>  
  
 <span data-ttu-id="dc336-114">**SQLConnect** supone que el nombre del origen de datos, el identificador de usuario y la contraseña son suficientes para conectarse a un origen de datos y que el origen de datos ODBC contiene toda la información necesaria para que el controlador ODBC realice la conexión.</span><span class="sxs-lookup"><span data-stu-id="dc336-114">**SQLConnect** assumes that a data source name, user ID, and password are sufficient to connect to a data source and that the ODBC data source contains all other information the ODBC driver needs to make the connection.</span></span> <span data-ttu-id="dc336-115">A diferencia de [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) y [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** no utiliza una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="dc336-115">Unlike [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) and [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** does not use a connection string.</span></span>  
  
## <a name="sqldriverconnect"></a><span data-ttu-id="dc336-116">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="dc336-116">SQLDriverConnect</span></span>  
 <span data-ttu-id="dc336-117">**SQLDriverConnect** se usa cuando se necesita más información que el nombre del origen de datos, el identificador de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="dc336-117">**SQLDriverConnect** is used when more information than the data source name, user ID, and password is required.</span></span> <span data-ttu-id="dc336-118">Uno de los parámetros para **SQLDriverConnect** es una cadena de conexión que contiene información específica del controlador.</span><span class="sxs-lookup"><span data-stu-id="dc336-118">One of the parameters to **SQLDriverConnect** is a connection string containing driver-specific information.</span></span> <span data-ttu-id="dc336-119">Puede usar **SQLDriverConnect** en lugar de **SQLConnect** por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc336-119">You might use **SQLDriverConnect** instead of **SQLConnect** for the following reasons:</span></span>  
  
-   <span data-ttu-id="dc336-120">Para especificar la información específica del controlador durante la conexión.</span><span class="sxs-lookup"><span data-stu-id="dc336-120">To specify driver-specific information at connect time.</span></span>  
  
-   <span data-ttu-id="dc336-121">Para solicitar que el controlador solicite al usuario la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="dc336-121">To request that the driver prompt the user for connection information.</span></span>  
  
-   <span data-ttu-id="dc336-122">Para conectarse sin utilizar un origen de datos ODBC.</span><span class="sxs-lookup"><span data-stu-id="dc336-122">To connect without using an ODBC data source.</span></span>  
  
 <span data-ttu-id="dc336-123">La cadena de conexión **SQLDriverConnect** contiene una serie de pares palabra clave-valor que especifican toda la información de conexión admitida por un controlador ODBC.</span><span class="sxs-lookup"><span data-stu-id="dc336-123">The **SQLDriverConnect** connection string contains a series of keyword-value pairs that specify all connection information supported by an ODBC driver.</span></span> <span data-ttu-id="dc336-124">Cada controlador admite las palabras clave de ODBC estándar (DSN, FILEDSN, DRIVER, UID, PWD y SAVEFILE) además de las palabras clave específicas del controlador para toda la información de conexión admitida por el controlador.</span><span class="sxs-lookup"><span data-stu-id="dc336-124">Each driver supports the standard ODBC keywords (DSN, FILEDSN, DRIVER, UID, PWD, and SAVEFILE) in addition to driver-specific keywords for all connection information supported by the driver.</span></span> <span data-ttu-id="dc336-125">**SQLDriverConnect** se puede usar para conectarse sin un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="dc336-125">**SQLDriverConnect** can be used to connect without a data source.</span></span> <span data-ttu-id="dc336-126">Por ejemplo, una aplicación diseñada para hacer una conexión "sin DSN" a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] puede llamar a **SQLDriverConnect** con una cadena de conexión que define el identificador de inicio de sesión, la contraseña, la biblioteca de red, el nombre del servidor al que se va a conectar y la base de datos predeterminada que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="dc336-126">For example, an application that is designed to make a "DSN-less" connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can call **SQLDriverConnect** with a connection string that defines the login ID, password, network library, server name to connect to, and default database to use.</span></span>  
  
 <span data-ttu-id="dc336-127">Al usar **SQLDriverConnect**, hay dos opciones para preguntar al usuario sobre la información de conexión necesaria:</span><span class="sxs-lookup"><span data-stu-id="dc336-127">When using **SQLDriverConnect**, there are two options for prompting the user for any needed connection information:</span></span>  
  
-   <span data-ttu-id="dc336-128">Cuadro de diálogo de la aplicación</span><span class="sxs-lookup"><span data-stu-id="dc336-128">Application dialog box</span></span>  
  
     <span data-ttu-id="dc336-129">Puede crear un cuadro de diálogo de aplicación que pida información de conexión y, a continuación, llame a **SQLDriverConnect** con un identificador de ventana nulo y *DriverCompletion* establecido en SQL_DRIVER_NOPROMPT.</span><span class="sxs-lookup"><span data-stu-id="dc336-129">You can create an application dialog box that prompts for connection information, and then calls **SQLDriverConnect** with a NULL window handle and *DriverCompletion* set to SQL_DRIVER_NOPROMPT.</span></span> <span data-ttu-id="dc336-130">Estos valores de parámetro evitan que el controlador ODBC abra su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="dc336-130">These parameter settings prevent the ODBC driver from opening its own dialog box.</span></span> <span data-ttu-id="dc336-131">Se utiliza este método cuando es importante controlar la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc336-131">This method is used when it is important to control the user interface of the application.</span></span>  
  
-   <span data-ttu-id="dc336-132">Cuadro de diálogo del controlador</span><span class="sxs-lookup"><span data-stu-id="dc336-132">Driver dialog box</span></span>  
  
     <span data-ttu-id="dc336-133">Puede codificar la aplicación para pasar un identificador de ventana válido a **SQLDriverConnect** y establecer el parámetro *DriverCompletion* en SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT o SQL_DRIVER_COMPLETE_REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="dc336-133">You can code the application to pass a valid window handle to **SQLDriverConnect** and set the *DriverCompletion* parameter to SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT, or SQL_DRIVER_COMPLETE_REQUIRED.</span></span> <span data-ttu-id="dc336-134">El controlador genera después un cuadro de diálogo para solicitar al usuario la información de conexión.</span><span class="sxs-lookup"><span data-stu-id="dc336-134">The driver then generates a dialog box to prompt the user for connection information.</span></span> <span data-ttu-id="dc336-135">Este método simplifica el código de aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc336-135">This method simplifies the application code.</span></span>  
  
## <a name="sqlbrowseconnect"></a><span data-ttu-id="dc336-136">SQLBrowseConnect</span><span class="sxs-lookup"><span data-stu-id="dc336-136">SQLBrowseConnect</span></span>  
 <span data-ttu-id="dc336-137">**SQLBrowseConnect**, como **SQLDriverConnect**, utiliza una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="dc336-137">**SQLBrowseConnect**, like **SQLDriverConnect**, uses a connection string.</span></span> <span data-ttu-id="dc336-138">Sin embargo, mediante **SQLBrowseConnect**, una aplicación puede crear una cadena de conexión completa de forma iterativa con el origen de datos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dc336-138">However, by using **SQLBrowseConnect**, an application can construct a complete connection string iteratively with the data source at run time.</span></span> <span data-ttu-id="dc336-139">Esto permite a la aplicación hacer dos cosas:</span><span class="sxs-lookup"><span data-stu-id="dc336-139">This allows the application to do two things:</span></span>  
  
-   <span data-ttu-id="dc336-140">Construir sus propios cuadros de diálogo para solicitar esta información, reteniendo así el control sobre la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="dc336-140">Build its own dialog boxes to prompt for this information, thereby retaining control over its user interface.</span></span>  
  
-   <span data-ttu-id="dc336-141">Buscar en el sistema los orígenes de datos que un controlador determinado puede utilizar, posiblemente en varios pasos.</span><span class="sxs-lookup"><span data-stu-id="dc336-141">Browse the system for data sources that can be used by a particular driver, possibly in several steps.</span></span>  
  
     <span data-ttu-id="dc336-142">Por ejemplo, el usuario podría buscar primero en la red los servidores y, después de elegir un servidor, buscar en el servidor las bases de datos accesibles para el controlador.</span><span class="sxs-lookup"><span data-stu-id="dc336-142">For example, the user might first browse the network for servers and, after choosing a server, browse the server for databases accessible by the driver.</span></span>  
  
 <span data-ttu-id="dc336-143">Cuando **SQLBrowseConnect** completa una conexión correcta, devuelve una cadena de conexión que se puede usar en las llamadas subsiguientes a **SQLDriverConnect**.</span><span class="sxs-lookup"><span data-stu-id="dc336-143">When **SQLBrowseConnect** completes a successful connection, it returns a connection string that can be used on subsequent calls to **SQLDriverConnect**.</span></span>  
  
 <span data-ttu-id="dc336-144">El [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client siempre devuelve SQL_SUCCESS_WITH_INFO con un **SQLConnect**, **SQLDriverConnect**o **SQLBrowseConnect**correctos.</span><span class="sxs-lookup"><span data-stu-id="dc336-144">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver always returns SQL_SUCCESS_WITH_INFO on a successful **SQLConnect**, **SQLDriverConnect**, or **SQLBrowseConnect**.</span></span> <span data-ttu-id="dc336-145">Cuando una aplicación ODBC llama a **SQLGetDiagRec** después de obtener SQL_SUCCESS_WITH_INFO, puede recibir los mensajes siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc336-145">When an ODBC application calls **SQLGetDiagRec** after getting SQL_SUCCESS_WITH_INFO, it can receive the following messages:</span></span>  
  
 <span data-ttu-id="dc336-146">5701</span><span class="sxs-lookup"><span data-stu-id="dc336-146">5701</span></span>  
 <span data-ttu-id="dc336-147">Indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pone el contexto del usuario en la base de datos predeterminada definida en el origen de datos, o en la base de datos predeterminada definida para el identificador de inicio de sesión utilizado en la conexión si el origen de datos no tenía una base de datos predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dc336-147">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] put the user's context into the default database defined in the data source, or into the default database defined for the login ID used in the connection if the data source did not have a default database.</span></span>  
  
 <span data-ttu-id="dc336-148">5703</span><span class="sxs-lookup"><span data-stu-id="dc336-148">5703</span></span>  
 <span data-ttu-id="dc336-149">Indica el lenguaje utilizado en el servidor.</span><span class="sxs-lookup"><span data-stu-id="dc336-149">Indicates the language being used on the server.</span></span>  
  
 <span data-ttu-id="dc336-150">En el ejemplo siguiente se muestra el mensaje devuelto por el administrador del sistema al realizarse una conexión correctamente:</span><span class="sxs-lookup"><span data-stu-id="dc336-150">The following example shows the message returned on a successful connection by the system administrator:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 5701,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed database context to 'pubs'."  
szSqlState = "01000", *pfNativeError = 5703,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed language setting to 'us_english'."  
```  
  
 <span data-ttu-id="dc336-151">Puede omitir los mensajes 5701 y 5703; solo son informativos.</span><span class="sxs-lookup"><span data-stu-id="dc336-151">You can ignore messages 5701 and 5703; they are only informational.</span></span> <span data-ttu-id="dc336-152">No debe, sin embargo, omitir un código de retorno SQL_SUCCESS_WITH_INFO porque se pueden devolver mensajes distintos de 5701 ó 5703.</span><span class="sxs-lookup"><span data-stu-id="dc336-152">You should not, however, ignore a SQL_SUCCESS_WITH_INFO return code because messages other than 5701 or 5703 may be returned.</span></span> <span data-ttu-id="dc336-153">Por ejemplo, si un controlador se conecta a un servidor que ejecuta una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con procedimientos almacenados de catálogo obsoletos, uno de los errores devueltos a través de **SQLGetDiagRec** después de un SQL_SUCCESS_WITH_INFO es:</span><span class="sxs-lookup"><span data-stu-id="dc336-153">For example, if a driver connects to a server running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with outdated catalog stored procedures, one of the errors returned through **SQLGetDiagRec** after a SQL_SUCCESS_WITH_INFO is:</span></span>  
  
```  
SqlState:   01000  
pfNative:   0  
szErrorMsg: "[Microsoft][SQL Server Native Client]The ODBC  
            catalog stored procedures installed on server  
            my65server are version 06.50.0193; version 07.00.0205  
            or later is required to ensure proper operation.  
            Please contact your system administrator."  
```  
  
 <span data-ttu-id="dc336-154">La función de control de errores de una aplicación para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] las conexiones debe llamar a **SQLGetDiagRec** hasta que devuelva SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="dc336-154">The error handling function of an application for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections should call **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="dc336-155">A continuación, debe actuar en cualquier mensaje distinto de los que tengan un código *pfNative* de 5701 o 5703.</span><span class="sxs-lookup"><span data-stu-id="dc336-155">It should then act on any messages other than the ones with a *pfNative* code of 5701 or 5703.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc336-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc336-156">See Also</span></span>  
 [<span data-ttu-id="dc336-157">Comunicarse con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="dc336-157">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
