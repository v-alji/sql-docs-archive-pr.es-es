---
title: SQLDriverConnect | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLDriverConnect function
ms.assetid: a1e38e2c-3a97-42d1-9c45-a0ca3282ffd1
author: rothja
ms.author: jroth
ms.openlocfilehash: 40691dfb381883b59155607fb56f4933820e3e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748100"
---
# <a name="sqldriverconnect"></a><span data-ttu-id="c5f06-102">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="c5f06-102">SQLDriverConnect</span></span>
  <span data-ttu-id="c5f06-103">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define atributos de conexión que o reemplazan o mejoran las palabras clave de cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c5f06-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines connection attributes that either replace or enhance connection-string keywords.</span></span> <span data-ttu-id="c5f06-104">Algunas palabras clave de cadena de conexión tienen valores predeterminados que especifica el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="c5f06-104">Several connection-string keywords have default values specified by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
 <span data-ttu-id="c5f06-105">Para obtener una lista de las palabras clave disponibles en el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client, vea [usar palabras clave de cadena de conexión con SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c5f06-105">For a list of the keywords available in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="c5f06-106">Para obtener más información acerca de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] los atributos de conexión y los comportamientos predeterminados del controlador, consulte [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="c5f06-106">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection attributes and driver default behaviors, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="c5f06-107">Para obtener una descripción de las palabras clave de cadena de conexión que son válidas para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, vea [usar palabras clave de cadena de conexión con SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c5f06-107">For a discussion of connection string keywords that are valid for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="c5f06-108">Cuando el `SQLDriverConnect` valor del parámetro *DriverCompletion* es SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE o SQL_DRIVER_COMPLETE_REQUIRED, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] controlador ODBC de Native Client recupera los valores de palabra clave del cuadro de diálogo que se muestra.</span><span class="sxs-lookup"><span data-stu-id="c5f06-108">When the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE, or SQL_DRIVER_COMPLETE_REQUIRED, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver retrieves keyword values from the displayed dialog box.</span></span> <span data-ttu-id="c5f06-109">Si el valor de palabra clave se pasa en la cadena de conexión y el usuario no modifica el valor de la palabra clave en el cuadro de diálogo, el controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client utiliza el valor de la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c5f06-109">If the keyword value is passed in the connection string and the user does not alter the value for the keyword in the dialog box, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses the value from the connection string.</span></span> <span data-ttu-id="c5f06-110">Si el valor no está establecido en la cadena de conexión y el usuario no realiza ninguna asignación en el cuadro de diálogo, el controlador utiliza el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c5f06-110">If the value is not set in the connection string and the user makes no assignment in the dialog box, the driver uses the default.</span></span>  
  
 <span data-ttu-id="c5f06-111">`SQLDriverConnect`se debe proporcionar un *WindowHandle* válido cuando cualquier valor de *DriverCompletion* requiere (o podría requerir) la presentación del cuadro de diálogo de conexión del controlador.</span><span class="sxs-lookup"><span data-stu-id="c5f06-111">`SQLDriverConnect` must be given a valid *WindowHandle* when any *DriverCompletion* value requires (or could require) the display of the driver's connection dialog box.</span></span> <span data-ttu-id="c5f06-112">Un identificador no válido devuelve SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="c5f06-112">An invalid handle returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="c5f06-113">Especifique las palabras clave DRIVER o DSN.</span><span class="sxs-lookup"><span data-stu-id="c5f06-113">Specify either the DRIVER or DSN keywords.</span></span> <span data-ttu-id="c5f06-114">Si se indican ambas, ODBC especifica que un controlador utiliza la palabra clave del extremo izquierdo y omite la otra.</span><span class="sxs-lookup"><span data-stu-id="c5f06-114">ODBC states that a driver uses the leftmost of these two keywords and ignores the other if both are specified.</span></span> <span data-ttu-id="c5f06-115">Si se especifica el controlador, o es el extremo izquierdo de los dos, y el `SQLDriverConnect` valor del parámetro *DriverCompletion* es SQL_DRIVER_NOPROMPT, se requiere la palabra clave Server y un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="c5f06-115">If DRIVER is specified, or is the leftmost of the two, and the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT, the SERVER keyword and an appropriate value are required.</span></span>  
  
 <span data-ttu-id="c5f06-116">Cuando se especifica SQL_DRIVER_NOPROMPT, las palabras clave de autenticación de usuario deben estar presentes con valores.</span><span class="sxs-lookup"><span data-stu-id="c5f06-116">When SQL_DRIVER_NOPROMPT is specified, user authentication keywords must be present with values.</span></span> <span data-ttu-id="c5f06-117">El controlador garantiza que la cadena "Trusted_Connection=yes" o que las palabras clave UID y PWD están presentes.</span><span class="sxs-lookup"><span data-stu-id="c5f06-117">The driver ensures that either the string "Trusted_Connection=yes" or both the UID and PWD keywords are present.</span></span>  
  
 <span data-ttu-id="c5f06-118">Si el valor del parámetro *DriverCompletion* es SQL_DRIVER_NOPROMPT o SQL_DRIVER_COMPLETE_REQUIRED y el lenguaje o la base de datos proceden de la cadena de conexión y no son válidos, `SQLDriverConnect` devuelve SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="c5f06-118">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the connection string and either is invalid, `SQLDriverConnect` returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="c5f06-119">Si el valor del parámetro *DriverCompletion* es SQL_DRIVER_NOPROMPT o SQL_DRIVER_COMPLETE_REQUIRED y el lenguaje o la base de datos proceden de las definiciones de origen de datos ODBC y no son válidos, `SQLDriverConnect` utiliza el idioma o la base de datos predeterminados para el ID. de usuario especificado y devuelve SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="c5f06-119">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the ODBC data source definitions and either is invalid, `SQLDriverConnect` uses the default language or database for the specified user ID and returns SQL_SUCCESS_WITH_INFO.</span></span>  
  
 <span data-ttu-id="c5f06-120">Si el valor del parámetro *DriverCompletion* es SQL_DRIVER_COMPLETE o SQL_DRIVER_PROMPT y si el idioma o la base de datos no son válidos, `SQLDriverConnect` vuelve a mostrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c5f06-120">If the *DriverCompletion* parameter value is SQL_DRIVER_COMPLETE or SQL_DRIVER_PROMPT and if the language or database is invalid, `SQLDriverConnect` redisplays the dialog box.</span></span>  
  
## <a name="sqldriverconnect-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="c5f06-121">Compatibilidad de SQLDriverConnect para la alta disponibilidad con recuperación de desastres</span><span class="sxs-lookup"><span data-stu-id="c5f06-121">SQLDriverConnect Support for High Availability, Disaster Recovery</span></span>  
 <span data-ttu-id="c5f06-122">Para obtener más información sobre `SQLDriverConnect` el uso de para conectarse a un [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] clúster, consulte [SQL Server Native Client compatibilidad con la alta disponibilidad y la recuperación ante desastres](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="c5f06-122">For more information about using `SQLDriverConnect` to connect to a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, see [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span></span>  
  
## <a name="sqldriverconnect-support-for-service-principal-names-spns"></a><span data-ttu-id="c5f06-123">Compatibilidad de SQLDriverConnect con los Nombres principales de servicio (SPN)</span><span class="sxs-lookup"><span data-stu-id="c5f06-123">SQLDriverConnect Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="c5f06-124">SQLDDriverConnect utilizará el cuadro de diálogo Inicio de sesión ODBC boxwhen se habilitará la solicitud.</span><span class="sxs-lookup"><span data-stu-id="c5f06-124">SQLDDriverConnect will use the ODBC Login dialog boxwhen prompting is enabled.</span></span> <span data-ttu-id="c5f06-125">Esto permite escribir SPN tanto para el servidor principal como para su asociado de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="c5f06-125">This allows SPNs to be entered for both the principal server and its failover partner.</span></span>  
  
 <span data-ttu-id="c5f06-126">SQLDriverConnect aceptará las nuevas palabras clave de cadena `ServerSPN` de conexión y `FailoverPartnerSPN` , y reconocerá los nuevos atributos de conexión SQL_COPT_SS_SERVER_SPN y SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span><span class="sxs-lookup"><span data-stu-id="c5f06-126">SQLDriverConnect will accept the new connection string keywords `ServerSPN` and `FailoverPartnerSPN`, and will recognize the new connection attributes SQL_COPT_SS_SERVER_SPN and SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span></span>  
  
 <span data-ttu-id="c5f06-127">Cuando un valor de atributo de conexión se especifica más de una vez, el valor que se establece mediante programación tiene prioridad sobre el valor de un DSN y el valor de una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c5f06-127">When a connection attribute value is specified more than once, a value that is set programmatically takes precedence over the value in a DSN and a value in a connection string.</span></span> <span data-ttu-id="c5f06-128">El valor de un DSN tiene prioridad sobre el valor de una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="c5f06-128">A value in a DSN takes precedence over a value in a connection string.</span></span>  
  
 <span data-ttu-id="c5f06-129">Cuando se abre una conexión, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client establece SQL_COPT_SS_MUTUALLY_AUTHENTICATED y SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD en el método de autenticación que se utiliza para abrir la conexión.</span><span class="sxs-lookup"><span data-stu-id="c5f06-129">When a connection is opened, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sets SQL_COPT_SS_MUTUALLY_AUTHENTICATED and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD to the authentication method used to open the connection.</span></span>  
  
 <span data-ttu-id="c5f06-130">Para obtener más información acerca de los SPN, consulte [nombres de entidad de seguridad de servicio &#40;spn&#41; en conexiones de cliente &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="c5f06-130">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c5f06-131">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c5f06-131">Examples</span></span>  
 <span data-ttu-id="c5f06-132">La siguiente llamada ilustra la cantidad mínima de datos necesarios para `SQLDriverConnect` :</span><span class="sxs-lookup"><span data-stu-id="c5f06-132">The following call illustrates the least amount of data required for `SQLDriverConnect`:</span></span>  
  
```  
SQLDriverConnect(hdbc, hwnd,  
    (SQLTCHAR*) TEXT("DRIVER={SQL Server Native Client 10};"), SQL_NTS, szOutConn,  
    MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
```  
  
 <span data-ttu-id="c5f06-133">Las cadenas de conexión siguientes ilustran los datos mínimos necesarios cuando el valor del parámetro *DriverCompletion* es SQL_DRIVER_NOPROMPT:</span><span class="sxs-lookup"><span data-stu-id="c5f06-133">The following connection strings illustrate minimum required data when the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT:</span></span>  
  
```  
"DSN=Human Resources;Trusted_Connection=yes"  
  
"FILEDSN=HR_FDSN;Trusted_Connection=yes"  
  
"DRIVER={SQL Server Native Client 10};SERVER=(local);Trusted_Connection=yes"  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5f06-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5f06-134">See Also</span></span>  
 <span data-ttu-id="c5f06-135">[SQLDriverConnect, función](https://go.microsoft.com/fwlink/?LinkId=59340) </span><span class="sxs-lookup"><span data-stu-id="c5f06-135">[SQLDriverConnect Function](https://go.microsoft.com/fwlink/?LinkId=59340) </span></span>  
 <span data-ttu-id="c5f06-136">[Detalles de implementación de la API de ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="c5f06-136">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="c5f06-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5f06-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="c5f06-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5f06-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="c5f06-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5f06-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
