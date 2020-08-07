---
title: SQL Server Native Client (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQLNCLI, ODBC
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], ODBC
- SQL Server Native Client ODBC driver
- ODBC
- SQL Server Native Client, ODBC
- ODBC, about SQL Server Native Client ODBC driver
ms.assetid: 811d5ba3-a2b8-48c0-adbc-8c91f041f458
author: rothja
ms.author: jroth
ms.openlocfilehash: 16c73966e318ed1e7d326fa77f56195ebbd830df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746971"
---
# <a name="sql-server-native-client-odbc"></a><span data-ttu-id="3dcdc-102">SQL Server Native Client (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3dcdc-102">SQL Server Native Client (ODBC)</span></span>
  <span data-ttu-id="3dcdc-103">ODBC es una definición estándar de una interfaz de programación de aplicaciones (API) utilizada para tener acceso a los datos de bases de datos relacionales o de método de acceso secuencial indizado (ISAM).</span><span class="sxs-lookup"><span data-stu-id="3dcdc-103">ODBC is a standard definition of an application programming interface (API) used to access data in relational or indexed sequential access method (ISAM) databases.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="3dcdc-104">admite ODBC mediante el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, como una de las API nativas para escribir aplicaciones C y C++ que se comuniquen con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3dcdc-104">supports ODBC, via the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, as one of the native APIs for writing C and C++ applications that communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3dcdc-105">Los programas [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que se escriben utilizando el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client se comunican con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a través de llamadas a funciones C.</span><span class="sxs-lookup"><span data-stu-id="3dcdc-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] programs that are written using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver communicate with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through C function calls.</span></span> <span data-ttu-id="3dcdc-106">Las versiones específicas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de las funciones ODBC se implementan en el controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="3dcdc-106">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific versions of the ODBC functions are implemented in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="3dcdc-107">El controlador pasa las instrucciones SQL a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y devuelve los resultados de las instrucciones a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3dcdc-107">The driver passes SQL statements to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and returns the results of the statements to the application.</span></span>  
  
 <span data-ttu-id="3dcdc-108">El controlador ODBC de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client se ajusta a la especificación de Microsoft Win32 ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="3dcdc-108">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver complies with the Microsoft Win32 ODBC 3.51 specification.</span></span> <span data-ttu-id="3dcdc-109">El controlador admite las aplicaciones escritas utilizando versiones anteriores de ODBC tal y como se define en la especificación de ODBC 3.51.</span><span class="sxs-lookup"><span data-stu-id="3dcdc-109">The driver supports applications written using earlier versions of ODBC in the manner defined in the ODBC 3.51 specification.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3dcdc-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3dcdc-110">In This Section</span></span>  
  
-   [<span data-ttu-id="3dcdc-111">Nombres de origen de datos y sistemas operativos de 64 bits</span><span class="sxs-lookup"><span data-stu-id="3dcdc-111">Data Source Names and 64-Bit Operating Systems</span></span>](data-source-names-and-64-bit-operating-systems.md)  
  
-   [<span data-ttu-id="3dcdc-112">Crear una aplicación de controlador ODBC de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="3dcdc-112">Creating a SQL Server Native Client ODBC Driver Application</span></span>](creating-a-driver-application.md)  
  
-   [<span data-ttu-id="3dcdc-113">Comunicarse con SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3dcdc-113">Communicating with SQL Server &#40;ODBC&#41;</span></span>](../../native-client-odbc-communication/communicating-with-sql-server-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-114">Ejecutar consultas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3dcdc-114">Executing Queries &#40;ODBC&#41;</span></span>](../../native-client-odbc-queries/executing-queries-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-115">Procesar los resultados &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3dcdc-115">Processing Results &#40;ODBC&#41;</span></span>](../../native-client-odbc-results/processing-results-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-116">Usar cursores &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3dcdc-116">Using Cursors &#40;ODBC&#41;</span></span>](../../native-client-odbc-cursors/using-cursors-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-117">Realizar transacciones &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3dcdc-117">Performing Transactions &#40;ODBC&#41;</span></span>](../../../database-engine/dev-guide/performing-transactions-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-118">Controlar errores y mensajes</span><span class="sxs-lookup"><span data-stu-id="3dcdc-118">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
-   [<span data-ttu-id="3dcdc-119">Ejecutar procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="3dcdc-119">Running Stored Procedures</span></span>](../../native-client-odbc-stored-procedures/running-stored-procedures.md)  
  
-   [<span data-ttu-id="3dcdc-120">Utilizar funciones de catálogo</span><span class="sxs-lookup"><span data-stu-id="3dcdc-120">Using Catalog Functions</span></span>](using-catalog-functions.md)  
  
-   [<span data-ttu-id="3dcdc-121">Realizar operaciones de copia masiva &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3dcdc-121">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](../../native-client-odbc-bulk-copy-operations/performing-bulk-copy-operations-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-122">Administrar columnas de texto e imagen</span><span class="sxs-lookup"><span data-stu-id="3dcdc-122">Managing Text and Image Columns</span></span>](../../native-client-odbc-text-image-columns/managing-text-and-image-columns.md)  
  
-   [<span data-ttu-id="3dcdc-123">Generar perfiles del rendimiento del controlador ODBC</span><span class="sxs-lookup"><span data-stu-id="3dcdc-123">Profiling ODBC Driver Performance</span></span>](profiling-odbc-driver-performance.md)  
  
-   [<span data-ttu-id="3dcdc-124">Parámetros con valores de tabla &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3dcdc-124">Table-Valued Parameters &#40;ODBC&#41;</span></span>](../../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-125">Mejoras de fecha y hora &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3dcdc-125">Date and Time Improvements &#40;ODBC&#41;</span></span>](../../native-client-odbc-date-time/date-and-time-improvements-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-126">Tipos CLR grandes definidos por el usuario &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3dcdc-126">Large CLR User-Defined Types &#40;ODBC&#41;</span></span>](large-clr-user-defined-types-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-127">Compatibilidad de FILESTREAM &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3dcdc-127">FILESTREAM Support &#40;ODBC&#41;</span></span>](filestream-support-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-128">Nombres de entidad de seguridad de servicio &#40;SPNs&#41; en conexiones cliente &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3dcdc-128">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;</span></span>](service-principal-names-spns-in-client-connections-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-129">Compatibilidad con columnas dispersas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3dcdc-129">Sparse Columns Support &#40;ODBC&#41;</span></span>](sparse-columns-support-odbc.md)  
  
-   [<span data-ttu-id="3dcdc-130">SQL Server Native Client &#40;referencia de&#41; ODBC</span><span class="sxs-lookup"><span data-stu-id="3dcdc-130">SQL Server Native Client &#40;ODBC&#41; Reference</span></span>](../../../database-engine/dev-guide/sql-server-native-client-odbc-reference.md)  
  
-   [<span data-ttu-id="3dcdc-131">Temas de procedimientos de ODBC</span><span class="sxs-lookup"><span data-stu-id="3dcdc-131">ODBC How-to Topics</span></span>](../../native-client-odbc-how-to/odbc-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="3dcdc-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3dcdc-132">See Also</span></span>  
 <span data-ttu-id="3dcdc-133">[Programación de SQL Server Native Client](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="3dcdc-133">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 [<span data-ttu-id="3dcdc-134">Instalar SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="3dcdc-134">Installing SQL Server Native Client</span></span>](../applications/installing-sql-server-native-client.md)  
  
  
