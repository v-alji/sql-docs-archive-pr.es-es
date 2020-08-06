---
title: Crear una aplicación de controlador ODBC de SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, architecture
- SQL Server Native Client ODBC driver, creating applications
- ODBC function calls
- ODBC, header files
- ODBC applications
- ODBC applications, creating
- SQL Server Native Client ODBC driver, extensions
- applications [SQL Server Native Client]
- SQL Server Native Client ODBC driver, ODBC architecture
- extensions [ODBC]
- ODBC, driver extensions
- function calls [ODBC]
ms.assetid: c83c36e2-734e-4960-bc7e-92235910bc6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c8a1719f8b60885810d9b2f8a1f1023a7ffe6e47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748737"
---
# <a name="creating-a-sql-server-native-client-odbc-driver-application"></a><span data-ttu-id="b4e64-102">Crear una aplicación de controlador ODBC de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="b4e64-102">Creating a SQL Server Native Client ODBC Driver Application</span></span>
  <span data-ttu-id="b4e64-103">La arquitectura de ODBC tiene cuatro componentes que se encargan de realizar las funciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="b4e64-103">ODBC architecture has four components that perform the following functions.</span></span>  
  
|<span data-ttu-id="b4e64-104">Componente</span><span class="sxs-lookup"><span data-stu-id="b4e64-104">Component</span></span>|<span data-ttu-id="b4e64-105">Función</span><span class="sxs-lookup"><span data-stu-id="b4e64-105">Function</span></span>|  
|---------------|--------------|  
|<span data-ttu-id="b4e64-106">Application</span><span class="sxs-lookup"><span data-stu-id="b4e64-106">Application</span></span>|<span data-ttu-id="b4e64-107">Llama a las funciones ODBC para comunicarse con un origen de datos ODBC, envía instrucciones SQL y procesa los conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="b4e64-107">Calls ODBC functions to communicate with an ODBC data source, submits SQL statements, and processes result sets.</span></span>|  
|<span data-ttu-id="b4e64-108">Administrador de controladores</span><span class="sxs-lookup"><span data-stu-id="b4e64-108">Driver Manager</span></span>|<span data-ttu-id="b4e64-109">Administra la comunicación entre una aplicación y todos los controladores ODBC usados por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4e64-109">Manages communication between an application and all ODBC drivers used by the application.</span></span>|  
|<span data-ttu-id="b4e64-110">Controlador</span><span class="sxs-lookup"><span data-stu-id="b4e64-110">Driver</span></span>|<span data-ttu-id="b4e64-111">Procesa todas las llamadas de función ODBC desde la aplicación, se conecta a un origen de datos, pasa instrucciones SQL de la aplicación al origen de datos y devuelve resultados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b4e64-111">Processes all ODBC function calls from the application, connects to a data source, passes SQL statements from the application to the data source, and returns results to the application.</span></span> <span data-ttu-id="b4e64-112">Si es necesario, el controlador traduce el SQL de ODBC de la aplicación al SQL nativo usado por el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b4e64-112">If necessary, the driver translates ODBC SQL from the application to native SQL used by the data source.</span></span>|  
|<span data-ttu-id="b4e64-113">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="b4e64-113">Data source</span></span>|<span data-ttu-id="b4e64-114">Contiene toda la información que un controlador necesita para obtener acceso a una determinada instancia de datos en un DBMS.</span><span class="sxs-lookup"><span data-stu-id="b4e64-114">Contains all information a driver needs to access a specific instance of data in a DBMS.</span></span>|  
  
 <span data-ttu-id="b4e64-115">Una aplicación que utiliza el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client para comunicarse con una instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="b4e64-115">An application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to communicate with an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs the following tasks:</span></span>  
  
-   <span data-ttu-id="b4e64-116">Se conecta con un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b4e64-116">Connects with a data source</span></span>  
  
-   <span data-ttu-id="b4e64-117">Envía instrucciones SQL al origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b4e64-117">Sends SQL statements to the data source</span></span>  
  
-   <span data-ttu-id="b4e64-118">Procesa los resultados de las instrucciones desde el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b4e64-118">Processes the results of statements from the data source</span></span>  
  
-   <span data-ttu-id="b4e64-119">Procesa errores y mensajes.</span><span class="sxs-lookup"><span data-stu-id="b4e64-119">Processes errors and messages</span></span>  
  
-   <span data-ttu-id="b4e64-120">Termina la conexión con el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="b4e64-120">Terminates the connection to the data source</span></span>  
  
 <span data-ttu-id="b4e64-121">Una aplicación más compleja escrita para el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client también puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="b4e64-121">A more complex application written for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver might also perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b4e64-122">Usar cursores para controlar la ubicación en un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b4e64-122">Use cursors to control location in a result set</span></span>  
  
-   <span data-ttu-id="b4e64-123">Solicitar operaciones de confirmación o reversión para el control de transacciones.</span><span class="sxs-lookup"><span data-stu-id="b4e64-123">Request commit or rollback operations for transaction control</span></span>  
  
-   <span data-ttu-id="b4e64-124">Realizar transacciones distribuidas que impliquen dos o más servidores.</span><span class="sxs-lookup"><span data-stu-id="b4e64-124">Perform distributed transactions involving two or more servers</span></span>  
  
-   <span data-ttu-id="b4e64-125">Ejecutar procedimientos almacenados en el servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="b4e64-125">Run stored procedures on the remote server</span></span>  
  
-   <span data-ttu-id="b4e64-126">Llamar a funciones de catálogo para realizar consultas sobre los atributos de un conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b4e64-126">Call catalog functions to inquire about the attributes of a result set</span></span>  
  
-   <span data-ttu-id="b4e64-127">Realizar operaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="b4e64-127">Perform bulk copy operations</span></span>  
  
-   <span data-ttu-id="b4e64-128">Administrar operaciones de datos de gran tamaño (**VARCHAR (Max)**, **nvarchar (Max)** y **varbinary (Max)** Columns</span><span class="sxs-lookup"><span data-stu-id="b4e64-128">Manage large data (**varchar(max)**, **nvarchar(max)**, and **varbinary(max)** columns) operations</span></span>  
  
-   <span data-ttu-id="b4e64-129">Usar la lógica de reconexión para facilitar la conmutación por error al configurar la creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b4e64-129">Use reconnection logic to facilitate failover when database mirroring is configured</span></span>  
  
-   <span data-ttu-id="b4e64-130">Registrar datos de rendimiento y consultas de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="b4e64-130">Log performance data and long-running queries</span></span>  
  
 <span data-ttu-id="b4e64-131">Para realizar llamadas a funciones ODBC, una aplicación C o C++ debe incluir los archivos de encabezado sql.h, sqlext.h y sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="b4e64-131">To make ODBC function calls, a C or C++ application must include the sql.h, sqlext.h, and sqltypes.h header files.</span></span> <span data-ttu-id="b4e64-132">Para realizar llamadas a las funciones API del instalador ODBC, una aplicación debe incluir el archivo de encabezado odbcinst.h.</span><span class="sxs-lookup"><span data-stu-id="b4e64-132">To make calls to the ODBC installer API functions, an application must include the odbcinst.h header file.</span></span> <span data-ttu-id="b4e64-133">Una aplicación ODBC Unicode debe incluir el archivo de encabezado sqlucode.h.</span><span class="sxs-lookup"><span data-stu-id="b4e64-133">A Unicode ODBC application must include the sqlucode.h header file.</span></span> <span data-ttu-id="b4e64-134">Las aplicaciones ODBC deben estar vinculadas al archivo odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="b4e64-134">ODBC applications must be linked with the odbc32.lib file.</span></span> <span data-ttu-id="b4e64-135">Las aplicaciones ODBC que llaman a las funciones API del instalador ODBC deben estar vinculadas al archivo odbccp32.lib.</span><span class="sxs-lookup"><span data-stu-id="b4e64-135">ODBC applications that call the ODBC installer API functions must be linked with the odbccp32.lib file.</span></span> <span data-ttu-id="b4e64-136">Estos archivos se incluyen en Windows Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="b4e64-136">These files are included in the Windows Platform SDK.</span></span>  
  
 <span data-ttu-id="b4e64-137">Muchos controladores ODBC, incluido el [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client, ofrecen extensiones ODBC específicas del controlador.</span><span class="sxs-lookup"><span data-stu-id="b4e64-137">Many ODBC drivers, including the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, offer driver-specific ODBC extensions.</span></span> <span data-ttu-id="b4e64-138">Para aprovechar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] las extensiones específicas del controlador ODBC de Native Client, una aplicación debe incluir el archivo de encabezado SQLNCLI. h.</span><span class="sxs-lookup"><span data-stu-id="b4e64-138">To take advantage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific extensions, an application should include the sqlncli.h header file.</span></span> <span data-ttu-id="b4e64-139">Este archivo de encabezado incluye:</span><span class="sxs-lookup"><span data-stu-id="b4e64-139">This header file contains:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="b4e64-140">Atributos de conexión específicos del controlador ODBC de Native Client.</span><span class="sxs-lookup"><span data-stu-id="b4e64-140">Native Client ODBC driver-specific connection attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="b4e64-141">Atributos de instrucción específicos del controlador ODBC de Native Client.</span><span class="sxs-lookup"><span data-stu-id="b4e64-141">Native Client ODBC driver-specific statement attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="b4e64-142">Atributos de columna específicos del controlador ODBC de Native Client.</span><span class="sxs-lookup"><span data-stu-id="b4e64-142">Native Client ODBC driver-specific column attributes.</span></span>  
  
-   <span data-ttu-id="b4e64-143">Tipos de datos específicos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4e64-143">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific data types.</span></span>  
  
-   <span data-ttu-id="b4e64-144">Tipos de datos definidos por el usuario específicos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4e64-144">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific user-defined data types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="b4e64-145">Tipos de [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) específicos del controlador ODBC de Native Client.</span><span class="sxs-lookup"><span data-stu-id="b4e64-145">Native Client ODBC driver-specific [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="b4e64-146">Campos de diagnóstico del controlador ODBC de Native Client.</span><span class="sxs-lookup"><span data-stu-id="b4e64-146">Native Client ODBC driver diagnostics fields.</span></span>  
  
-   <span data-ttu-id="b4e64-147">Códigos de función dinámica de diagnóstico específicos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4e64-147">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific diagnostic dynamic function codes.</span></span>  
  
-   <span data-ttu-id="b4e64-148">Definiciones de tipo de C/C++ para tipos de datos C nativos específicos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (que se devuelven cuando las columnas están enlazadas al tipo de datos C SQL_C_BINARY).</span><span class="sxs-lookup"><span data-stu-id="b4e64-148">C/C++ type definitions for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific native C data types (returned when columns bound to C data type SQL_C_BINARY).</span></span>  
  
-   <span data-ttu-id="b4e64-149">Definición de tipo para la estructura de datos SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="b4e64-149">Type definition for the SQLPERF data structure.</span></span>  
  
-   <span data-ttu-id="b4e64-150">Prototipos y macros de copia masiva para admitir el uso de la API de copia masiva a través de una conexión ODBC.</span><span class="sxs-lookup"><span data-stu-id="b4e64-150">Bulk copy macros and prototypes to support bulk copy API usage through an ODBC connection.</span></span>  
  
-   <span data-ttu-id="b4e64-151">Llame a las funciones API de metadatos de consulta distribuida para obtener listas de servidores vinculados y sus catálogos.</span><span class="sxs-lookup"><span data-stu-id="b4e64-151">Call the distributed query metadata API functions for lists of linked servers and their catalogs.</span></span>  
  
 <span data-ttu-id="b4e64-152">Cualquier aplicación ODBC de C o C++ que use la característica de copia masiva del [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlador ODBC de Native Client debe estar vinculada al archivo sqlncli11. lib.</span><span class="sxs-lookup"><span data-stu-id="b4e64-152">Any C or C++ ODBC application that uses the bulk copy feature of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver must be linked with the sqlncli11.lib file.</span></span> <span data-ttu-id="b4e64-153">Las aplicaciones que llaman a las funciones API de metadatos de consulta distribuida también deben vincularse a sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="b4e64-153">Applications calling the distributed query metadata API functions must also be linked with sqlncli11.lib.</span></span> <span data-ttu-id="b4e64-154">Los archivos SQLNCLI. h y sqlncli11. lib se distribuyen como parte de las [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] herramientas del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="b4e64-154">The sqlncli.h and sqlncli11.lib files are distributed as part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developer's tools.</span></span> <span data-ttu-id="b4e64-155">Los directorios Include y Lib de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] deberían estar en las rutas de acceso LIB e INCLUDE del compilador, como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b4e64-155">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Include and Lib directories should be in the compiler's INCLUDE and LIB paths as in the following:</span></span>  
  
```  
LIB=c:\Program Files\Microsoft Data Access SDK 2.8\Libs\x86\lib;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Lib;  
INCLUDE=c:\Program Files\Microsoft Data Access SDK 2.8\inc;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Include;  
```  
  
 <span data-ttu-id="b4e64-156">Una decisión de diseño que se realiza al principio del proceso de generación de una aplicación es si la aplicación necesita tener varias llamadas ODBC pendientes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="b4e64-156">One design decision made early in the process of building an application is whether the application needs to have multiple ODBC calls outstanding at the same time.</span></span> <span data-ttu-id="b4e64-157">Hay dos métodos para admitir varias llamadas ODBC simultáneas, que se describen en los temas restantes en esta sección.</span><span class="sxs-lookup"><span data-stu-id="b4e64-157">There are two methods for supporting multiple concurrent ODBC calls, which are described in the remaining topics in this section.</span></span> <span data-ttu-id="b4e64-158">Para obtener más información, vea la [Referencia del programador de ODBC](https://go.microsoft.com/fwlink/?LinkId=45250).</span><span class="sxs-lookup"><span data-stu-id="b4e64-158">For more information, see the [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4e64-159">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b4e64-159">In This Section</span></span>  
  
-   [<span data-ttu-id="b4e64-160">Modo asincrónico y SQLCancel</span><span class="sxs-lookup"><span data-stu-id="b4e64-160">Asynchronous Mode and SQLCancel</span></span>](../../native-client-odbc-api/sqlcancel.md)  
  
-   [<span data-ttu-id="b4e64-161">Aplicaciones multiproceso</span><span class="sxs-lookup"><span data-stu-id="b4e64-161">Multithreaded Applications</span></span>](creating-a-driver-application-multithreaded-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4e64-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4e64-162">See Also</span></span>  
 [<span data-ttu-id="b4e64-163">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b4e64-163">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
