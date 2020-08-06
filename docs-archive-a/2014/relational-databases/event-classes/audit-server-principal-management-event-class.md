---
title: Clase de eventos Audit Server Principal Management | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Audit Server Principal Management event class
ms.assetid: 7894850c-91fe-47c0-a03c-baacbc10d29c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6373db514bcd6a0d0691eb812f4d5521f2017f4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672979"
---
# <a name="audit-server-principal-management-event-class"></a><span data-ttu-id="dd34d-102">Audit Server Principal Management, clase de eventos</span><span class="sxs-lookup"><span data-stu-id="dd34d-102">Audit Server Principal Management Event Class</span></span>
  <span data-ttu-id="dd34d-103">La clase de eventos **Audit Server Principal Management** se produce cuando se crean, modifican o quitan entidades de seguridad del servidor.</span><span class="sxs-lookup"><span data-stu-id="dd34d-103">The **Audit Server Principal Management** event class occurs when server principals are created, altered, or dropped.</span></span>  
  
## <a name="audit-server-principal-management-event-class-data-columns"></a><span data-ttu-id="dd34d-104">Columnas de datos de la clase de eventos Audit Server Principal Management</span><span class="sxs-lookup"><span data-stu-id="dd34d-104">Audit Server Principal Management Event Class Data Columns</span></span>  
  
|<span data-ttu-id="dd34d-105">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="dd34d-105">Data column name</span></span>|<span data-ttu-id="dd34d-106">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="dd34d-106">Data type</span></span>|<span data-ttu-id="dd34d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dd34d-107">Description</span></span>|<span data-ttu-id="dd34d-108">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="dd34d-108">Column ID</span></span>|<span data-ttu-id="dd34d-109">Filtrable</span><span class="sxs-lookup"><span data-stu-id="dd34d-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="dd34d-110">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-110">**ApplicationName**</span></span>|<span data-ttu-id="dd34d-111">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-111">**nvarchar**</span></span>|<span data-ttu-id="dd34d-112">Nombre de la aplicación cliente que ha creado la conexión a una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd34d-112">Name of the client application that created the connection to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dd34d-113">Esta columna se rellena con los valores que pasa la aplicación, en lugar de con el nombre que se muestra para el programa.</span><span class="sxs-lookup"><span data-stu-id="dd34d-113">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="dd34d-114">10</span><span class="sxs-lookup"><span data-stu-id="dd34d-114">10</span></span>|<span data-ttu-id="dd34d-115">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-115">Yes</span></span>|  
|<span data-ttu-id="dd34d-116">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="dd34d-116">**DatabaseID**</span></span>|<span data-ttu-id="dd34d-117">**int**</span><span class="sxs-lookup"><span data-stu-id="dd34d-117">**int**</span></span>|<span data-ttu-id="dd34d-118">Identificador de la base de datos especificada mediante la instrucción USE *database* o la base de datos predeterminada si no se emite la instrucción USE *database* para una determinada instancia.</span><span class="sxs-lookup"><span data-stu-id="dd34d-118">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="dd34d-119">muestra el nombre de la base de datos si se captura la columna de datos **ServerName** en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="dd34d-119">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="dd34d-120">Determina el valor de una base de datos mediante la función DB_ID.</span><span class="sxs-lookup"><span data-stu-id="dd34d-120">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="dd34d-121">3</span><span class="sxs-lookup"><span data-stu-id="dd34d-121">3</span></span>|<span data-ttu-id="dd34d-122">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-122">Yes</span></span>|  
|<span data-ttu-id="dd34d-123">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-123">**DatabaseName**</span></span>|<span data-ttu-id="dd34d-124">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-124">**nvarchar**</span></span>|<span data-ttu-id="dd34d-125">Nombre de la base de datos en la que se ejecuta la instrucción del usuario.</span><span class="sxs-lookup"><span data-stu-id="dd34d-125">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="dd34d-126">35</span><span class="sxs-lookup"><span data-stu-id="dd34d-126">35</span></span>|<span data-ttu-id="dd34d-127">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-127">Yes</span></span>|  
|<span data-ttu-id="dd34d-128">**DBUserName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-128">**DBUserName**</span></span>|<span data-ttu-id="dd34d-129">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-129">**nvarchar**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dd34d-130">del cliente.</span><span class="sxs-lookup"><span data-stu-id="dd34d-130">user name of the client.</span></span>|<span data-ttu-id="dd34d-131">40</span><span class="sxs-lookup"><span data-stu-id="dd34d-131">40</span></span>|<span data-ttu-id="dd34d-132">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-132">Yes</span></span>|  
|<span data-ttu-id="dd34d-133">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="dd34d-133">**EventSequence**</span></span>|<span data-ttu-id="dd34d-134">**int**</span><span class="sxs-lookup"><span data-stu-id="dd34d-134">**int**</span></span>|<span data-ttu-id="dd34d-135">Secuencia de un evento determinado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="dd34d-135">Sequence of a given event within the request.</span></span>|<span data-ttu-id="dd34d-136">51</span><span class="sxs-lookup"><span data-stu-id="dd34d-136">51</span></span>|<span data-ttu-id="dd34d-137">No</span><span class="sxs-lookup"><span data-stu-id="dd34d-137">No</span></span>|  
|<span data-ttu-id="dd34d-138">**EventSubClass**</span><span class="sxs-lookup"><span data-stu-id="dd34d-138">**EventSubClass**</span></span>|<span data-ttu-id="dd34d-139">**int**</span><span class="sxs-lookup"><span data-stu-id="dd34d-139">**int**</span></span>|<span data-ttu-id="dd34d-140">Tipo de la subclase de eventos.</span><span class="sxs-lookup"><span data-stu-id="dd34d-140">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="dd34d-141">1=Crear</span><span class="sxs-lookup"><span data-stu-id="dd34d-141">1=Create</span></span><br /><br /> <span data-ttu-id="dd34d-142">2=Modificar</span><span class="sxs-lookup"><span data-stu-id="dd34d-142">2=Alter</span></span><br /><br /> <span data-ttu-id="dd34d-143">3=Quitar</span><span class="sxs-lookup"><span data-stu-id="dd34d-143">3=Drop</span></span><br /><br /> <span data-ttu-id="dd34d-144">4=Volcar</span><span class="sxs-lookup"><span data-stu-id="dd34d-144">4=Dump</span></span><br /><br /> <span data-ttu-id="dd34d-145">5=Deshabilitar</span><span class="sxs-lookup"><span data-stu-id="dd34d-145">5=Disable</span></span><br /><br /> <span data-ttu-id="dd34d-146">6=Habilitar</span><span class="sxs-lookup"><span data-stu-id="dd34d-146">6=Enable</span></span><br /><br /> <span data-ttu-id="dd34d-147">11=Cargar</span><span class="sxs-lookup"><span data-stu-id="dd34d-147">11=Load</span></span>|<span data-ttu-id="dd34d-148">21</span><span class="sxs-lookup"><span data-stu-id="dd34d-148">21</span></span>|<span data-ttu-id="dd34d-149">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-149">Yes</span></span>|  
|<span data-ttu-id="dd34d-150">**HostName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-150">**HostName**</span></span>|<span data-ttu-id="dd34d-151">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-151">**nvarchar**</span></span>|<span data-ttu-id="dd34d-152">Nombre del equipo en el que se está ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="dd34d-152">Name of the computer on which the client is running.</span></span> <span data-ttu-id="dd34d-153">Esta columna de datos se rellena si el cliente proporciona el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="dd34d-153">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="dd34d-154">Para determinar el nombre del host, utilice la función HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="dd34d-154">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="dd34d-155">8</span><span class="sxs-lookup"><span data-stu-id="dd34d-155">8</span></span>|<span data-ttu-id="dd34d-156">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-156">Yes</span></span>|  
|<span data-ttu-id="dd34d-157">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="dd34d-157">**IsSystem**</span></span>|<span data-ttu-id="dd34d-158">**int**</span><span class="sxs-lookup"><span data-stu-id="dd34d-158">**int**</span></span>|<span data-ttu-id="dd34d-159">Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="dd34d-159">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="dd34d-160">1 = sistema, 0 = usuario.</span><span class="sxs-lookup"><span data-stu-id="dd34d-160">1 = system, 0 = user.</span></span>|<span data-ttu-id="dd34d-161">60</span><span class="sxs-lookup"><span data-stu-id="dd34d-161">60</span></span>|<span data-ttu-id="dd34d-162">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-162">Yes</span></span>|  
|<span data-ttu-id="dd34d-163">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="dd34d-163">**LoginSid**</span></span>|<span data-ttu-id="dd34d-164">**image**</span><span class="sxs-lookup"><span data-stu-id="dd34d-164">**image**</span></span>|<span data-ttu-id="dd34d-165">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="dd34d-165">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="dd34d-166">Puede encontrar esta información en la vista de catálogo **sys.server_principals** .</span><span class="sxs-lookup"><span data-stu-id="dd34d-166">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="dd34d-167">Cada SID es único para cada inicio de sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="dd34d-167">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="dd34d-168">41</span><span class="sxs-lookup"><span data-stu-id="dd34d-168">41</span></span>|<span data-ttu-id="dd34d-169">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-169">Yes</span></span>|  
|<span data-ttu-id="dd34d-170">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-170">**NTDomainName**</span></span>|<span data-ttu-id="dd34d-171">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-171">**nvarchar**</span></span>|<span data-ttu-id="dd34d-172">Dominio de Windows al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="dd34d-172">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="dd34d-173">7</span><span class="sxs-lookup"><span data-stu-id="dd34d-173">7</span></span>|<span data-ttu-id="dd34d-174">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-174">Yes</span></span>|  
|<span data-ttu-id="dd34d-175">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-175">**NTUserName**</span></span>|<span data-ttu-id="dd34d-176">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-176">**nvarchar**</span></span>|<span data-ttu-id="dd34d-177">Nombre del usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="dd34d-177">Windows user name.</span></span>|<span data-ttu-id="dd34d-178">6</span><span class="sxs-lookup"><span data-stu-id="dd34d-178">6</span></span>|<span data-ttu-id="dd34d-179">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-179">Yes</span></span>|  
|<span data-ttu-id="dd34d-180">**ObjectName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-180">**ObjectName**</span></span>|<span data-ttu-id="dd34d-181">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-181">**nvarchar**</span></span>|<span data-ttu-id="dd34d-182">Nombre del objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="dd34d-182">Name of the object being referenced.</span></span>|<span data-ttu-id="dd34d-183">34</span><span class="sxs-lookup"><span data-stu-id="dd34d-183">34</span></span>|<span data-ttu-id="dd34d-184">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-184">Yes</span></span>|  
|<span data-ttu-id="dd34d-185">**ObjectType**</span><span class="sxs-lookup"><span data-stu-id="dd34d-185">**ObjectType**</span></span>|<span data-ttu-id="dd34d-186">**int**</span><span class="sxs-lookup"><span data-stu-id="dd34d-186">**int**</span></span>|<span data-ttu-id="dd34d-187">Valor que representa el tipo del objeto implicado en el evento.</span><span class="sxs-lookup"><span data-stu-id="dd34d-187">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="dd34d-188">Este valor corresponde al de la columna Type de la vista de catálogo **sys.objects** .</span><span class="sxs-lookup"><span data-stu-id="dd34d-188">This value corresponds to the type column in the **sys.objects** catalog view.</span></span> <span data-ttu-id="dd34d-189">Para ver los valores, vea [Columna de evento de seguimiento ObjectType](objecttype-trace-event-column.md).</span><span class="sxs-lookup"><span data-stu-id="dd34d-189">For values, see [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span>|<span data-ttu-id="dd34d-190">28</span><span class="sxs-lookup"><span data-stu-id="dd34d-190">28</span></span>|<span data-ttu-id="dd34d-191">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-191">Yes</span></span>|  
|<span data-ttu-id="dd34d-192">**OwnerName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-192">**OwnerName**</span></span>|<span data-ttu-id="dd34d-193">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-193">**nvarchar**</span></span>|<span data-ttu-id="dd34d-194">Nombre de usuario de base de datos del propietario del objeto.</span><span class="sxs-lookup"><span data-stu-id="dd34d-194">Database user name of the object owner.</span></span>|<span data-ttu-id="dd34d-195">37</span><span class="sxs-lookup"><span data-stu-id="dd34d-195">37</span></span>|<span data-ttu-id="dd34d-196">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-196">Yes</span></span>|  
|<span data-ttu-id="dd34d-197">**IdSolicitud**</span><span class="sxs-lookup"><span data-stu-id="dd34d-197">**RequestID**</span></span>|<span data-ttu-id="dd34d-198">**int**</span><span class="sxs-lookup"><span data-stu-id="dd34d-198">**int**</span></span>|<span data-ttu-id="dd34d-199">Identificador de la solicitud que contiene la instrucción.</span><span class="sxs-lookup"><span data-stu-id="dd34d-199">ID of the request containing the statement.</span></span>|<span data-ttu-id="dd34d-200">49</span><span class="sxs-lookup"><span data-stu-id="dd34d-200">49</span></span>|<span data-ttu-id="dd34d-201">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-201">Yes</span></span>|  
|<span data-ttu-id="dd34d-202">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-202">**ServerName**</span></span>|<span data-ttu-id="dd34d-203">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-203">**nvarchar**</span></span>|<span data-ttu-id="dd34d-204">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dd34d-204">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="dd34d-205">26</span><span class="sxs-lookup"><span data-stu-id="dd34d-205">26</span></span>|<span data-ttu-id="dd34d-206">No</span><span class="sxs-lookup"><span data-stu-id="dd34d-206">No</span></span>|  
|<span data-ttu-id="dd34d-207">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="dd34d-207">**SessionLoginName**</span></span>|<span data-ttu-id="dd34d-208">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="dd34d-208">**nvarchar**</span></span>|<span data-ttu-id="dd34d-209">Nombre de inicio de sesión del usuario que originó la sesión.</span><span class="sxs-lookup"><span data-stu-id="dd34d-209">Login name of the user who originated the session.</span></span> <span data-ttu-id="dd34d-210">Por ejemplo, si se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando inicioDeSesión1 y ejecuta una instrucción como inicioDeSesión2, **SessionLoginName** muestra inicioDeSesión1 y **LoginName** muestra inicioDeSesión2.</span><span class="sxs-lookup"><span data-stu-id="dd34d-210">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="dd34d-211">En esta columna se muestran los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y de Windows.</span><span class="sxs-lookup"><span data-stu-id="dd34d-211">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="dd34d-212">64</span><span class="sxs-lookup"><span data-stu-id="dd34d-212">64</span></span>|<span data-ttu-id="dd34d-213">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-213">Yes</span></span>|  
|<span data-ttu-id="dd34d-214">**SPID**</span><span class="sxs-lookup"><span data-stu-id="dd34d-214">**SPID**</span></span>|<span data-ttu-id="dd34d-215">**int**</span><span class="sxs-lookup"><span data-stu-id="dd34d-215">**int**</span></span>|<span data-ttu-id="dd34d-216">Identificador de la sesión en la que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="dd34d-216">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="dd34d-217">12</span><span class="sxs-lookup"><span data-stu-id="dd34d-217">12</span></span>|<span data-ttu-id="dd34d-218">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-218">Yes</span></span>|  
|<span data-ttu-id="dd34d-219">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="dd34d-219">**StartTime**</span></span>|<span data-ttu-id="dd34d-220">**datetime**</span><span class="sxs-lookup"><span data-stu-id="dd34d-220">**datetime**</span></span>|<span data-ttu-id="dd34d-221">Hora a la que se inició el evento, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="dd34d-221">Time at which the event started, if available.</span></span>|<span data-ttu-id="dd34d-222">14</span><span class="sxs-lookup"><span data-stu-id="dd34d-222">14</span></span>|<span data-ttu-id="dd34d-223">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-223">Yes</span></span>|  
|<span data-ttu-id="dd34d-224">**Success**</span><span class="sxs-lookup"><span data-stu-id="dd34d-224">**Success**</span></span>|<span data-ttu-id="dd34d-225">**int**</span><span class="sxs-lookup"><span data-stu-id="dd34d-225">**int**</span></span>|<span data-ttu-id="dd34d-226">1 = correcto.</span><span class="sxs-lookup"><span data-stu-id="dd34d-226">1 = success.</span></span> <span data-ttu-id="dd34d-227">0 = error</span><span class="sxs-lookup"><span data-stu-id="dd34d-227">0 = failure.</span></span> <span data-ttu-id="dd34d-228">Por ejemplo, el valor 1 significa que se ha comprobado un permiso correctamente y el valor 0 indica que se ha producido un error en la comprobación.</span><span class="sxs-lookup"><span data-stu-id="dd34d-228">For example, a value of 1 indicates success of a permissions check and a value of 0 indicates failure of that check.</span></span>|<span data-ttu-id="dd34d-229">23</span><span class="sxs-lookup"><span data-stu-id="dd34d-229">23</span></span>|<span data-ttu-id="dd34d-230">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-230">Yes</span></span>|  
|<span data-ttu-id="dd34d-231">**XactSequence**</span><span class="sxs-lookup"><span data-stu-id="dd34d-231">**XactSequence**</span></span>|<span data-ttu-id="dd34d-232">**bigint**</span><span class="sxs-lookup"><span data-stu-id="dd34d-232">**bigint**</span></span>|<span data-ttu-id="dd34d-233">Token que se utiliza para describir la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="dd34d-233">Token used to describe the current transaction.</span></span>|<span data-ttu-id="dd34d-234">50</span><span class="sxs-lookup"><span data-stu-id="dd34d-234">50</span></span>|<span data-ttu-id="dd34d-235">Sí</span><span class="sxs-lookup"><span data-stu-id="dd34d-235">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd34d-236">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dd34d-236">See Also</span></span>  
 <span data-ttu-id="dd34d-237">[Eventos extendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="dd34d-237">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="dd34d-238">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="dd34d-238">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  