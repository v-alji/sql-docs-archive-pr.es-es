---
title: Clase de evento Guía de plan correcta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Plan Guide Successful event class
ms.assetid: fecfbb6c-56c9-4db4-84d3-00d6e338355a
author: stevestein
ms.author: sstein
ms.openlocfilehash: b521c230d1789b031903aecdf8f42f9be3ffc0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674805"
---
# <a name="plan-guide-successful-event-class"></a><span data-ttu-id="6b53f-102">Clase de evento Guía de plan correcta</span><span class="sxs-lookup"><span data-stu-id="6b53f-102">Plan Guide Successful Event Class</span></span>
  <span data-ttu-id="6b53f-103">La clase de eventos Guía de plan correcta indica que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pudo generar correctamente un plan de ejecución para una consulta o lote que contenía una guía de plan.</span><span class="sxs-lookup"><span data-stu-id="6b53f-103">The Plan Guide Successful event class indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] successfully produced an execution plan for a query or batch that contained a plan guide.</span></span> <span data-ttu-id="6b53f-104">El evento se disparará cuando se cumplan las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="6b53f-104">The event fires when the following conditions are true:</span></span>  
  
-   <span data-ttu-id="6b53f-105">El lote o módulo de la definición de la guía de plan coincide con el lote o módulo que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="6b53f-105">The batch or module in the plan guide definition matches the batch or module that is being executed.</span></span>  
  
-   <span data-ttu-id="6b53f-106">La consulta de la definición de la guía de plan coincide con la consulta que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="6b53f-106">The query in the plan guide definition matches the query being executed.</span></span>  
  
-   <span data-ttu-id="6b53f-107">Las sugerencias en la definición de la guía de plan, incluyendo la sugerencia USE PLAN, se aplicaron correctamente a la consulta.</span><span class="sxs-lookup"><span data-stu-id="6b53f-107">The hints in the plan guide definition, including the USE PLAN hint, were applied successfully to the query.</span></span> <span data-ttu-id="6b53f-108">Es decir, el plan de consulta compilado cumplió con las sugerencias especificadas.</span><span class="sxs-lookup"><span data-stu-id="6b53f-108">That is, the compiled query plan honors the specified hints.</span></span>  
  
## <a name="plan-guide-successful-event-class-data-columns"></a><span data-ttu-id="6b53f-109">Columnas de datos de la clase de eventos Guía de plan correcta</span><span class="sxs-lookup"><span data-stu-id="6b53f-109">Plan Guide Successful Event Class Data Columns</span></span>  
  
|<span data-ttu-id="6b53f-110">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="6b53f-110">Data column name</span></span>|<span data-ttu-id="6b53f-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="6b53f-111">Data type</span></span>|<span data-ttu-id="6b53f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b53f-112">Description</span></span>|<span data-ttu-id="6b53f-113">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="6b53f-113">Column ID</span></span>|<span data-ttu-id="6b53f-114">Filtrable</span><span class="sxs-lookup"><span data-stu-id="6b53f-114">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="6b53f-115">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="6b53f-115">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="6b53f-116">Nombre de la aplicación cliente que ha creado la conexión a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b53f-116">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6b53f-117">Esta columna se rellena con los valores que pasa la aplicación, en lugar de con el nombre que se muestra del programa.</span><span class="sxs-lookup"><span data-stu-id="6b53f-117">This column is populated with the values that are passed by the application instead of the displayed name of the program.</span></span>|<span data-ttu-id="6b53f-118">10</span><span class="sxs-lookup"><span data-stu-id="6b53f-118">10</span></span>|<span data-ttu-id="6b53f-119">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-119">Yes</span></span>|  
|<span data-ttu-id="6b53f-120">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="6b53f-120">ClientProcessID</span></span>|`int`|<span data-ttu-id="6b53f-121">Identificador que el equipo host asigna al proceso en el que se ejecuta la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="6b53f-121">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="6b53f-122">Esta columna de datos se rellena si el cliente proporciona el identificador de proceso del cliente.</span><span class="sxs-lookup"><span data-stu-id="6b53f-122">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="6b53f-123">9</span><span class="sxs-lookup"><span data-stu-id="6b53f-123">9</span></span>|<span data-ttu-id="6b53f-124">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-124">Yes</span></span>|  
|<span data-ttu-id="6b53f-125">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="6b53f-125">DatabaseID</span></span>|`int`|<span data-ttu-id="6b53f-126">Identificador de la base de datos especificada mediante la instrucción USE *database* o la base de datos predeterminada si no se emite la instrucción USE *database* para una determinada instancia.</span><span class="sxs-lookup"><span data-stu-id="6b53f-126">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a specified instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="6b53f-127">muestra el nombre de la base de datos si se captura la columna de datos ServerName en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="6b53f-127">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="6b53f-128">Determina el valor de una base de datos mediante la función DB_ID.</span><span class="sxs-lookup"><span data-stu-id="6b53f-128">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="6b53f-129">3</span><span class="sxs-lookup"><span data-stu-id="6b53f-129">3</span></span>|<span data-ttu-id="6b53f-130">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-130">Yes</span></span>|  
|<span data-ttu-id="6b53f-131">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="6b53f-131">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="6b53f-132">Nombre de la base de datos en la que se ejecuta la instrucción del usuario.</span><span class="sxs-lookup"><span data-stu-id="6b53f-132">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="6b53f-133">35</span><span class="sxs-lookup"><span data-stu-id="6b53f-133">35</span></span>|<span data-ttu-id="6b53f-134">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-134">Yes</span></span>|  
|<span data-ttu-id="6b53f-135">EventClass</span><span class="sxs-lookup"><span data-stu-id="6b53f-135">EventClass</span></span>|`int`|<span data-ttu-id="6b53f-136">Tipo de evento = 214.</span><span class="sxs-lookup"><span data-stu-id="6b53f-136">Type of event = 214.</span></span>|<span data-ttu-id="6b53f-137">27</span><span class="sxs-lookup"><span data-stu-id="6b53f-137">27</span></span>|<span data-ttu-id="6b53f-138">No</span><span class="sxs-lookup"><span data-stu-id="6b53f-138">No</span></span>|  
|<span data-ttu-id="6b53f-139">EventSequence</span><span class="sxs-lookup"><span data-stu-id="6b53f-139">EventSequence</span></span>|`int`|<span data-ttu-id="6b53f-140">Secuencia de un evento determinado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="6b53f-140">Sequence of a specific event within the request.</span></span>|<span data-ttu-id="6b53f-141">51</span><span class="sxs-lookup"><span data-stu-id="6b53f-141">51</span></span>|<span data-ttu-id="6b53f-142">No</span><span class="sxs-lookup"><span data-stu-id="6b53f-142">No</span></span>|  
|<span data-ttu-id="6b53f-143">HostName</span><span class="sxs-lookup"><span data-stu-id="6b53f-143">HostName</span></span>|`nvarchar`|<span data-ttu-id="6b53f-144">Nombre del equipo en el que se está ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="6b53f-144">Name of the computer on which the client is running.</span></span> <span data-ttu-id="6b53f-145">Esta columna de datos se rellena si el cliente proporciona el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="6b53f-145">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="6b53f-146">Para determinar el nombre del host, utilice la función HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="6b53f-146">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="6b53f-147">8</span><span class="sxs-lookup"><span data-stu-id="6b53f-147">8</span></span>|<span data-ttu-id="6b53f-148">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-148">Yes</span></span>|  
|<span data-ttu-id="6b53f-149">IsSystem</span><span class="sxs-lookup"><span data-stu-id="6b53f-149">IsSystem</span></span>|`int`|<span data-ttu-id="6b53f-150">Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario1 = sistema, 0 = usuario.</span><span class="sxs-lookup"><span data-stu-id="6b53f-150">Indicates whether the event occurred on a system process or a user process: 1 = system, 0 = user.</span></span>|<span data-ttu-id="6b53f-151">60</span><span class="sxs-lookup"><span data-stu-id="6b53f-151">60</span></span>|<span data-ttu-id="6b53f-152">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-152">Yes</span></span>|  
|<span data-ttu-id="6b53f-153">LoginName</span><span class="sxs-lookup"><span data-stu-id="6b53f-153">LoginName</span></span>|`nvarchar`|<span data-ttu-id="6b53f-154">Nombre del inicio de sesión del usuario ( [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Inicio de sesión de seguridad de o [!INCLUDE[msCoName](../../includes/msconame-md.md)] credenciales de inicio de sesión de Windows con el formato dominio \\ *nombreDeUsuario*).</span><span class="sxs-lookup"><span data-stu-id="6b53f-154">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\\*username*).</span></span>|<span data-ttu-id="6b53f-155">11</span><span class="sxs-lookup"><span data-stu-id="6b53f-155">11</span></span>|<span data-ttu-id="6b53f-156">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-156">Yes</span></span>|  
|<span data-ttu-id="6b53f-157">LoginSid</span><span class="sxs-lookup"><span data-stu-id="6b53f-157">LoginSid</span></span>|`image`|<span data-ttu-id="6b53f-158">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="6b53f-158">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="6b53f-159">Encontrará esta información en la vista [sys.server_principals](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) o en las vistas de catálogo [sys.sql_logins](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="6b53f-159">You can find this information in the [sys.server_principals](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql) or the [sys.sql_logins](/sql/relational-databases/system-catalog-views/sys-sql-logins-transact-sql) catalog views.</span></span> <span data-ttu-id="6b53f-160">Cada SID es único para cada inicio de sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="6b53f-160">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="6b53f-161">41</span><span class="sxs-lookup"><span data-stu-id="6b53f-161">41</span></span>|<span data-ttu-id="6b53f-162">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-162">Yes</span></span>|  
|<span data-ttu-id="6b53f-163">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="6b53f-163">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="6b53f-164">Dominio de Windows al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="6b53f-164">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="6b53f-165">7</span><span class="sxs-lookup"><span data-stu-id="6b53f-165">7</span></span>|<span data-ttu-id="6b53f-166">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-166">Yes</span></span>|  
|<span data-ttu-id="6b53f-167">NTUserName</span><span class="sxs-lookup"><span data-stu-id="6b53f-167">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="6b53f-168">Nombre del usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="6b53f-168">Windows user name.</span></span>|<span data-ttu-id="6b53f-169">6</span><span class="sxs-lookup"><span data-stu-id="6b53f-169">6</span></span>|<span data-ttu-id="6b53f-170">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-170">Yes</span></span>|  
|<span data-ttu-id="6b53f-171">ObjectID</span><span class="sxs-lookup"><span data-stu-id="6b53f-171">ObjectID</span></span>|`int`|<span data-ttu-id="6b53f-172">Id. de objeto del módulo que se estaba compilando cuando se aplicó la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="6b53f-172">Object ID of the module that was being compiled when the plan guide was applied.</span></span> <span data-ttu-id="6b53f-173">Si la guía de plan no se aplicó a un módulo, esta columna estará establecida en NULL.</span><span class="sxs-lookup"><span data-stu-id="6b53f-173">If the plan guide was not applied to a module, this column is set to NULL.</span></span>|<span data-ttu-id="6b53f-174">22</span><span class="sxs-lookup"><span data-stu-id="6b53f-174">22</span></span>|<span data-ttu-id="6b53f-175">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-175">Yes</span></span>|  
|<span data-ttu-id="6b53f-176">RequestID</span><span class="sxs-lookup"><span data-stu-id="6b53f-176">RequestID</span></span>|`int`|<span data-ttu-id="6b53f-177">Id. de la solicitud que contiene la instrucción.</span><span class="sxs-lookup"><span data-stu-id="6b53f-177">ID of the request that contains the statement.</span></span>|<span data-ttu-id="6b53f-178">49</span><span class="sxs-lookup"><span data-stu-id="6b53f-178">49</span></span>|<span data-ttu-id="6b53f-179">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-179">Yes</span></span>|  
|<span data-ttu-id="6b53f-180">nombreDeServidor</span><span class="sxs-lookup"><span data-stu-id="6b53f-180">ServerName</span></span>|`nvarchar`|<span data-ttu-id="6b53f-181">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cuyo seguimiento se realiza.</span><span class="sxs-lookup"><span data-stu-id="6b53f-181">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is being traced.</span></span>|<span data-ttu-id="6b53f-182">26</span><span class="sxs-lookup"><span data-stu-id="6b53f-182">26</span></span>|<span data-ttu-id="6b53f-183">No</span><span class="sxs-lookup"><span data-stu-id="6b53f-183">No</span></span>|  
|<span data-ttu-id="6b53f-184">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="6b53f-184">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="6b53f-185">Nombre de inicio de sesión del usuario que originó la sesión.</span><span class="sxs-lookup"><span data-stu-id="6b53f-185">Login name of the user who originated the session.</span></span> <span data-ttu-id="6b53f-186">Por ejemplo, si se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando inicioDeSesión1 y ejecuta una instrucción como inicioDeSesión2, SessionLoginName muestra inicioDeSesión1 y LoginName muestra inicioDeSesión2.</span><span class="sxs-lookup"><span data-stu-id="6b53f-186">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="6b53f-187">En esta columna se muestran los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y de Windows.</span><span class="sxs-lookup"><span data-stu-id="6b53f-187">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="6b53f-188">64</span><span class="sxs-lookup"><span data-stu-id="6b53f-188">64</span></span>|<span data-ttu-id="6b53f-189">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-189">Yes</span></span>|  
|<span data-ttu-id="6b53f-190">SPID</span><span class="sxs-lookup"><span data-stu-id="6b53f-190">SPID</span></span>|`int`|<span data-ttu-id="6b53f-191">Identificador de la sesión en la que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="6b53f-191">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="6b53f-192">12</span><span class="sxs-lookup"><span data-stu-id="6b53f-192">12</span></span>|<span data-ttu-id="6b53f-193">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-193">Yes</span></span>|  
|<span data-ttu-id="6b53f-194">StartTime</span><span class="sxs-lookup"><span data-stu-id="6b53f-194">StartTime</span></span>|`datetime`|<span data-ttu-id="6b53f-195">Hora a la que se inició el evento, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="6b53f-195">Time at which the event started, if available.</span></span>|<span data-ttu-id="6b53f-196">14</span><span class="sxs-lookup"><span data-stu-id="6b53f-196">14</span></span>|<span data-ttu-id="6b53f-197">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-197">Yes</span></span>|  
|<span data-ttu-id="6b53f-198">TextData</span><span class="sxs-lookup"><span data-stu-id="6b53f-198">TextData</span></span>|`ntext`|<span data-ttu-id="6b53f-199">Nombre de la guía de plan.</span><span class="sxs-lookup"><span data-stu-id="6b53f-199">Name of the plan guide.</span></span>|<span data-ttu-id="6b53f-200">1</span><span class="sxs-lookup"><span data-stu-id="6b53f-200">1</span></span>|<span data-ttu-id="6b53f-201">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-201">Yes</span></span>|  
|<span data-ttu-id="6b53f-202">TransactionID</span><span class="sxs-lookup"><span data-stu-id="6b53f-202">TransactionID</span></span>|`bigint`|<span data-ttu-id="6b53f-203">Id. de la transacción asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="6b53f-203">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="6b53f-204">4</span><span class="sxs-lookup"><span data-stu-id="6b53f-204">4</span></span>|<span data-ttu-id="6b53f-205">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-205">Yes</span></span>|  
|<span data-ttu-id="6b53f-206">XactSequence</span><span class="sxs-lookup"><span data-stu-id="6b53f-206">XactSequence</span></span>|`bigint`|<span data-ttu-id="6b53f-207">Token que describe la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="6b53f-207">Token that describes the current transaction.</span></span>|<span data-ttu-id="6b53f-208">50</span><span class="sxs-lookup"><span data-stu-id="6b53f-208">50</span></span>|<span data-ttu-id="6b53f-209">Sí</span><span class="sxs-lookup"><span data-stu-id="6b53f-209">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b53f-210">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b53f-210">See Also</span></span>  
 <span data-ttu-id="6b53f-211">[Guía de plan incorrecta (clase de eventos)](plan-guide-unsuccessful-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="6b53f-211">[Plan Guide Unsuccessful Event Class](plan-guide-unsuccessful-event-class.md) </span></span>  
 <span data-ttu-id="6b53f-212">[Eventos extendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="6b53f-212">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="6b53f-213">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6b53f-213">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  