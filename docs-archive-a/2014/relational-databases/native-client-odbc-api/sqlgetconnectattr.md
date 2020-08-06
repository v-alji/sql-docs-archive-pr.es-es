---
title: SQLGetConnectAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetConnectAttr function
ms.assetid: 26e4e69a-44fd-45e3-b47a-ae39184f041b
author: rothja
ms.author: jroth
ms.openlocfilehash: f82a0fb71103e811b36280f9722c160791023e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662015"
---
# <a name="sqlgetconnectattr"></a><span data-ttu-id="77223-102">SQLGetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="77223-102">SQLGetConnectAttr</span></span>
  <span data-ttu-id="77223-103">El controlador ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define los atributos de conexión específicos del controlador.</span><span class="sxs-lookup"><span data-stu-id="77223-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines driver-specific connection attributes.</span></span> <span data-ttu-id="77223-104">Algunos de los atributos están disponibles para `SQLGetConnectAttr` y la función se usa para notificar su configuración actual.</span><span class="sxs-lookup"><span data-stu-id="77223-104">Some of the attributes are available to `SQLGetConnectAttr`, and the function is used to report their current settings.</span></span> <span data-ttu-id="77223-105">Los valores presentados para estos atributos no se garantizan hasta que se haya realizado una conexión o el atributo se haya establecido mediante [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="77223-105">The values reported for these attributes are not guaranteed until after a connection has been made or the attribute has been set using [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="77223-106">En este tema se enumeran los atributos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="77223-106">This topic lists the read only attributes.</span></span> <span data-ttu-id="77223-107">Para obtener información sobre otros atributos de conexión específicos del controlador de ODBC de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, vea [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="77223-107">For information about the other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific connection attributes, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="sql_copt_ss_connection_dead"></a><span data-ttu-id="77223-108">SQL_COPT_SS_CONNECTION_DEAD</span><span class="sxs-lookup"><span data-stu-id="77223-108">SQL_COPT_SS_CONNECTION_DEAD</span></span>  
 <span data-ttu-id="77223-109">El atributo SQL_COPT_SS_CONNECTION_DEAD notifica el estado de una conexión a un servidor.</span><span class="sxs-lookup"><span data-stu-id="77223-109">The SQL_COPT_SS_CONNECTION_DEAD attribute reports the state of a connection to a server.</span></span> <span data-ttu-id="77223-110">El controlador consulta el estado actual de la conexión en la red.</span><span class="sxs-lookup"><span data-stu-id="77223-110">The driver queries the network for the current state of the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="77223-111">El atributo de conexión ODBC estándar SQL_ATTR_CONNECTION_DEAD devuelve el estado más reciente de la conexión.</span><span class="sxs-lookup"><span data-stu-id="77223-111">The standard ODBC connection attribute SQL_ATTR_CONNECTION_DEAD returns the most recent state of the connection.</span></span> <span data-ttu-id="77223-112">Éste podría no ser el estado de la conexión actual.</span><span class="sxs-lookup"><span data-stu-id="77223-112">This might not be the current connection state.</span></span>  
  
|<span data-ttu-id="77223-113">Value</span><span class="sxs-lookup"><span data-stu-id="77223-113">Value</span></span>|<span data-ttu-id="77223-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="77223-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77223-115">SQL_CD_TRUE</span><span class="sxs-lookup"><span data-stu-id="77223-115">SQL_CD_TRUE</span></span>|<span data-ttu-id="77223-116">Se ha perdido la conexión al servidor.</span><span class="sxs-lookup"><span data-stu-id="77223-116">The connection to the server has been lost.</span></span>|  
|<span data-ttu-id="77223-117">SQL_CD_FALSE</span><span class="sxs-lookup"><span data-stu-id="77223-117">SQL_CD_FALSE</span></span>|<span data-ttu-id="77223-118">La conexión está abierta y disponible para procesar una instrucción.</span><span class="sxs-lookup"><span data-stu-id="77223-118">The connection is open and available for statement processing.</span></span>|  
  
## <a name="sql_copt_ss_client_connection_id"></a><span data-ttu-id="77223-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span><span class="sxs-lookup"><span data-stu-id="77223-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span></span>  
 <span data-ttu-id="77223-120">El atributo de SQL_COPT_SS_CLIENT_CONNECTION_ID recupera el identificador de conexión del cliente, el cual se puede utilizar para encontrar:</span><span class="sxs-lookup"><span data-stu-id="77223-120">The SQL_COPT_SS_CLIENT_CONNECTION_ID attribute retrieves the client connection ID, which can then be used to locate:</span></span>  
  
-   <span data-ttu-id="77223-121">Información de diagnóstico en el registro de XEvents, si se ha habilitado.</span><span class="sxs-lookup"><span data-stu-id="77223-121">Diagnostic information in the XEvents log, when enabled.</span></span>  
  
-   <span data-ttu-id="77223-122">Información sobre errores de conexión en el búfer del anillo de conexión.</span><span class="sxs-lookup"><span data-stu-id="77223-122">Connection error information in the connection ring buffer.</span></span>  
  
-   <span data-ttu-id="77223-123">Información de diagnóstico de los registros de seguimiento de acceso a datos, si se ha habilitado.</span><span class="sxs-lookup"><span data-stu-id="77223-123">Diagnostic information in the data access tracing logs, when enabled.</span></span>  
  
 <span data-ttu-id="77223-124">Para obtener más información, vea [acceso a la información de diagnóstico en el registro de eventos extendidos](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="77223-124">For more information, see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
|<span data-ttu-id="77223-125">Value</span><span class="sxs-lookup"><span data-stu-id="77223-125">Value</span></span>|<span data-ttu-id="77223-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="77223-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77223-127">SQL_ERROR</span><span class="sxs-lookup"><span data-stu-id="77223-127">SQL_ERROR</span></span>|<span data-ttu-id="77223-128">Error en la conexión</span><span class="sxs-lookup"><span data-stu-id="77223-128">The connection failed.</span></span>|  
|<span data-ttu-id="77223-129">SQL_SUCCESS</span><span class="sxs-lookup"><span data-stu-id="77223-129">SQL_SUCCESS</span></span>|<span data-ttu-id="77223-130">La conexión se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="77223-130">The connection succeeded.</span></span> <span data-ttu-id="77223-131">El identificador de conexión del cliente se encuentra en el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="77223-131">The client connection ID will be found in the output buffer.</span></span>|  
  
## <a name="sql_copt_ss_perf_data"></a><span data-ttu-id="77223-132">SQL_COPT_SS_PERF_DATA</span><span class="sxs-lookup"><span data-stu-id="77223-132">SQL_COPT_SS_PERF_DATA</span></span>  
 <span data-ttu-id="77223-133">El atributo SQL_COPT_SS_PERF_DATA devuelve un puntero a una estructura SQLPERF que contiene las estadísticas de rendimiento del controlador actual.</span><span class="sxs-lookup"><span data-stu-id="77223-133">The SQL_COPT_SS_PERF_DATA attribute returns a pointer to a SQLPERF structure containing the current driver performance statistics.</span></span> <span data-ttu-id="77223-134">`SQLGetConnectAttr`devolverá NULL si el registro de rendimiento no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="77223-134">`SQLGetConnectAttr` will return NULL if performance logging is not enabled.</span></span> <span data-ttu-id="77223-135">El controlador no actualiza de manera dinámica las estadísticas en la estructura SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="77223-135">The statistics in the SQLPERF structure are not dynamically updated by the driver.</span></span> <span data-ttu-id="77223-136">Llame `SQLGetConnectAttr` cada vez que sea necesario actualizar las estadísticas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="77223-136">Call `SQLGetConnectAttr` each time the performance statistics need to be refreshed.</span></span>  
  
|<span data-ttu-id="77223-137">Value</span><span class="sxs-lookup"><span data-stu-id="77223-137">Value</span></span>|<span data-ttu-id="77223-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="77223-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77223-139">NULL</span><span class="sxs-lookup"><span data-stu-id="77223-139">NULL</span></span>|<span data-ttu-id="77223-140">El registro de rendimiento no está habilitado.</span><span class="sxs-lookup"><span data-stu-id="77223-140">Performance logging is not enabled.</span></span>|  
|<span data-ttu-id="77223-141">Cualquier otro valor</span><span class="sxs-lookup"><span data-stu-id="77223-141">Any other value</span></span>|<span data-ttu-id="77223-142">Un puntero a una estructura SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="77223-142">A pointer to a SQLPERF structure.</span></span>|  
  
## <a name="sql_copt_ss_perf_query"></a><span data-ttu-id="77223-143">SQL_COPT_SS_PERF_QUERY</span><span class="sxs-lookup"><span data-stu-id="77223-143">SQL_COPT_SS_PERF_QUERY</span></span>  
 <span data-ttu-id="77223-144">El atributo SQL_COPT_SS_PERF_QUERY devuelve TRUE si está habilitado el registro de consultas de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="77223-144">The SQL_COPT_SS_PERF_QUERY attribute returns TRUE if logging of long running queries is enabled.</span></span> <span data-ttu-id="77223-145">La solicitud devuelve FALSE si el registro de consultas no está activo.</span><span class="sxs-lookup"><span data-stu-id="77223-145">The request returns FALSE if query logging is not active.</span></span>  
  
## <a name="sql_copt_ss_user_data"></a><span data-ttu-id="77223-146">SQL_COPT_SS_USER_DATA</span><span class="sxs-lookup"><span data-stu-id="77223-146">SQL_COPT_SS_USER_DATA</span></span>  
 <span data-ttu-id="77223-147">El atributo SQL_COPT_SS_USER_DATA recupera el puntero de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="77223-147">The SQL_COPT_SS_USER_DATA attribute retrieves the user-data pointer.</span></span> <span data-ttu-id="77223-148">Los datos de usuario se almacenan en la memoria propiedad del cliente y se registran por conexión.</span><span class="sxs-lookup"><span data-stu-id="77223-148">User data is stored in client-owned memory and recorded per connection.</span></span> <span data-ttu-id="77223-149">Si el puntero de datos de usuario no se ha establecido, SQL_UD_NOTSET, se devuelve un puntero NULL.</span><span class="sxs-lookup"><span data-stu-id="77223-149">If the user-data pointer has not been set, SQL_UD_NOTSET, a NULL pointer, is returned.</span></span>  
  
|<span data-ttu-id="77223-150">Value</span><span class="sxs-lookup"><span data-stu-id="77223-150">Value</span></span>|<span data-ttu-id="77223-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="77223-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="77223-152">SQL_UD_NOTSET</span><span class="sxs-lookup"><span data-stu-id="77223-152">SQL_UD_NOTSET</span></span>|<span data-ttu-id="77223-153">No se establece ningún puntero de datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="77223-153">No user-data pointer is set.</span></span>|  
|<span data-ttu-id="77223-154">Cualquier otro valor</span><span class="sxs-lookup"><span data-stu-id="77223-154">Any other value</span></span>|<span data-ttu-id="77223-155">Un puntero a los datos de usuario.</span><span class="sxs-lookup"><span data-stu-id="77223-155">A pointer to the user data.</span></span>|  
  
## <a name="sqlgetconnectattr-support-for-service-principal-names-spns"></a><span data-ttu-id="77223-156">Compatibilidad de SQLGetConnectAttr con los Nombres principales de servicio (SPN)</span><span class="sxs-lookup"><span data-stu-id="77223-156">SQLGetConnectAttr Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="77223-157">SQLGetConnectAttr se puede usar para consultar el valor de los nuevos atributos de conexión SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED y SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span><span class="sxs-lookup"><span data-stu-id="77223-157">SQLGetConnectAttr can be used to query the value of the new connection attributes SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED, and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span></span> <span data-ttu-id="77223-158">(SQLGetConnectOption también se puede usar para consultar estos valores).</span><span class="sxs-lookup"><span data-stu-id="77223-158">(SQLGetConnectOption can also be used to query these values.)</span></span>  
  
 <span data-ttu-id="77223-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD solo está disponible para las conexiones abiertas que usan la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="77223-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD is only available for open connections that use Windows Authentication.</span></span>  
  
 <span data-ttu-id="77223-160">Si no se ha establecido SQL_COPT_SS_SERVER_SPN o SQL_COPT_SS_FAILOVER_PARTNER, se devuelve el valor predeterminado (una cadena vacía).</span><span class="sxs-lookup"><span data-stu-id="77223-160">If SQL_COPT_SS_SERVER_SPN or SQL_COPT_SS_FAILOVER_PARTNER has not been set, the default value (an empty string) is returned.</span></span>  
  
 <span data-ttu-id="77223-161">Para obtener más información acerca de los SPN, consulte [nombres de entidad de seguridad de servicio &#40;spn&#41; en conexiones de cliente &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="77223-161">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77223-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77223-162">See Also</span></span>  
 <span data-ttu-id="77223-163">[SQLGetConnectAttr función)](https://go.microsoft.com/fwlink/?LinkId=59347) </span><span class="sxs-lookup"><span data-stu-id="77223-163">[SQLGetConnectAttr Function](https://go.microsoft.com/fwlink/?LinkId=59347) </span></span>  
 <span data-ttu-id="77223-164">[Detalles de implementación de la API de ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="77223-164">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="77223-165">[ESTABLECER QUOTED_IDENTIFIER &#40;&#41;de Transact-SQL](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77223-165">[SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span></span>  
 <span data-ttu-id="77223-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77223-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="77223-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="77223-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="77223-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="77223-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
