---
title: Clase de eventos Audit Schema Object Take Ownership | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Audit Schema Object Take Ownership event class
ms.assetid: 66f39d9b-9ec2-48a7-8a9e-1b42931299c9
author: stevestein
ms.author: sstein
ms.openlocfilehash: e4de7d9af6a9936a85842c6de6289e958272dadc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674836"
---
# <a name="audit-schema-object-take-ownership-event-class"></a><span data-ttu-id="25192-102">Audit Schema Object Take Ownership, clase de eventos</span><span class="sxs-lookup"><span data-stu-id="25192-102">Audit Schema Object Take Ownership Event Class</span></span>
  <span data-ttu-id="25192-103">La clase de eventos **Audit Schema Object Take Ownership** se produce cuando se comprueban los permisos para cambiar el propietario del objeto de esquema (como una tabla, procedimiento o función).</span><span class="sxs-lookup"><span data-stu-id="25192-103">The **Audit Schema Object Take Ownership** event class occurs when the permissions to change the owner of schema object (such as a table, procedure, or function) is checked.</span></span> <span data-ttu-id="25192-104">Esto sucede cuando se utiliza la instrucción ALTER AUTHORIZATION para asignar un propietario a un objeto.</span><span class="sxs-lookup"><span data-stu-id="25192-104">This happens when the ALTER AUTHORIZATION statement is used to assign an owner to an object.</span></span>  
  
## <a name="audit-schema-object-take-ownership-event-class-data-columns"></a><span data-ttu-id="25192-105">Columnas de datos de la clase de eventos Audit Schema Object Take Ownership</span><span class="sxs-lookup"><span data-stu-id="25192-105">Audit Schema Object Take Ownership Event Class Data Columns</span></span>  
  
|<span data-ttu-id="25192-106">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="25192-106">Data column name</span></span>|<span data-ttu-id="25192-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="25192-107">Data type</span></span>|<span data-ttu-id="25192-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="25192-108">Description</span></span>|<span data-ttu-id="25192-109">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="25192-109">Column ID</span></span>|<span data-ttu-id="25192-110">Filtrable</span><span class="sxs-lookup"><span data-stu-id="25192-110">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="25192-111">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="25192-111">**ApplicationName**</span></span>|<span data-ttu-id="25192-112">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-112">**nvarchar**</span></span>|<span data-ttu-id="25192-113">Nombre de la aplicación cliente que ha creado la conexión a una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25192-113">Name of the client application that created the connection to an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="25192-114">Esta columna se rellena con los valores que pasa la aplicación, en lugar de con el nombre que se muestra para el programa.</span><span class="sxs-lookup"><span data-stu-id="25192-114">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="25192-115">10</span><span class="sxs-lookup"><span data-stu-id="25192-115">10</span></span>|<span data-ttu-id="25192-116">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-116">Yes</span></span>|  
|<span data-ttu-id="25192-117">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="25192-117">**DatabaseID**</span></span>|<span data-ttu-id="25192-118">**int**</span><span class="sxs-lookup"><span data-stu-id="25192-118">**int**</span></span>|<span data-ttu-id="25192-119">Identificador de la base de datos especificada mediante la instrucción USE *database* o la base de datos predeterminada si no se emite la instrucción USE *database* para una determinada instancia.</span><span class="sxs-lookup"><span data-stu-id="25192-119">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="25192-120">muestra el nombre de la base de datos si se captura la columna de datos **ServerName** en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="25192-120">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="25192-121">Determina el valor de una base de datos mediante la función DB_ID.</span><span class="sxs-lookup"><span data-stu-id="25192-121">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="25192-122">3</span><span class="sxs-lookup"><span data-stu-id="25192-122">3</span></span>|<span data-ttu-id="25192-123">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-123">Yes</span></span>|  
|<span data-ttu-id="25192-124">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="25192-124">**DatabaseName**</span></span>|<span data-ttu-id="25192-125">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-125">**nvarchar**</span></span>|<span data-ttu-id="25192-126">Nombre de la base de datos en la que se ejecuta la instrucción del usuario.</span><span class="sxs-lookup"><span data-stu-id="25192-126">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="25192-127">35</span><span class="sxs-lookup"><span data-stu-id="25192-127">35</span></span>|<span data-ttu-id="25192-128">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-128">Yes</span></span>|  
|<span data-ttu-id="25192-129">**DBUserName**</span><span class="sxs-lookup"><span data-stu-id="25192-129">**DBUserName**</span></span>|<span data-ttu-id="25192-130">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-130">**nvarchar**</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="25192-131">del cliente.</span><span class="sxs-lookup"><span data-stu-id="25192-131">user name of the client.</span></span>|<span data-ttu-id="25192-132">40</span><span class="sxs-lookup"><span data-stu-id="25192-132">40</span></span>|<span data-ttu-id="25192-133">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-133">Yes</span></span>|  
|<span data-ttu-id="25192-134">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="25192-134">**EventSequence**</span></span>|<span data-ttu-id="25192-135">**int**</span><span class="sxs-lookup"><span data-stu-id="25192-135">**int**</span></span>|<span data-ttu-id="25192-136">Secuencia de un evento determinado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="25192-136">Sequence of a given event within the request.</span></span>|<span data-ttu-id="25192-137">51</span><span class="sxs-lookup"><span data-stu-id="25192-137">51</span></span>|<span data-ttu-id="25192-138">No</span><span class="sxs-lookup"><span data-stu-id="25192-138">No</span></span>|  
|<span data-ttu-id="25192-139">**HostName**</span><span class="sxs-lookup"><span data-stu-id="25192-139">**HostName**</span></span>|<span data-ttu-id="25192-140">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-140">**nvarchar**</span></span>|<span data-ttu-id="25192-141">Nombre del equipo en el que se está ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="25192-141">Name of the computer on which the client is running.</span></span> <span data-ttu-id="25192-142">Esta columna de datos se rellena si el cliente proporciona el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="25192-142">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="25192-143">Para determinar el nombre del host, utilice la función HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="25192-143">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="25192-144">8</span><span class="sxs-lookup"><span data-stu-id="25192-144">8</span></span>|<span data-ttu-id="25192-145">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-145">Yes</span></span>|  
|<span data-ttu-id="25192-146">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="25192-146">**IsSystem**</span></span>|<span data-ttu-id="25192-147">**int**</span><span class="sxs-lookup"><span data-stu-id="25192-147">**int**</span></span>|<span data-ttu-id="25192-148">Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="25192-148">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="25192-149">1 = sistema, 0 = usuario.</span><span class="sxs-lookup"><span data-stu-id="25192-149">1 = system, 0 = user.</span></span>|<span data-ttu-id="25192-150">60</span><span class="sxs-lookup"><span data-stu-id="25192-150">60</span></span>|<span data-ttu-id="25192-151">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-151">Yes</span></span>|  
|<span data-ttu-id="25192-152">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="25192-152">**LoginName**</span></span>|<span data-ttu-id="25192-153">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-153">**nvarchar**</span></span>|<span data-ttu-id="25192-154">Nombre del inicio de sesión del usuario (inicio de sesión de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenciales de inicio de sesión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con el formato DOMINIO\nombreDeUsuario).</span><span class="sxs-lookup"><span data-stu-id="25192-154">Name of the login of the user (either the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="25192-155">11</span><span class="sxs-lookup"><span data-stu-id="25192-155">11</span></span>|<span data-ttu-id="25192-156">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-156">Yes</span></span>|  
|<span data-ttu-id="25192-157">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="25192-157">**LoginSid**</span></span>|<span data-ttu-id="25192-158">**image**</span><span class="sxs-lookup"><span data-stu-id="25192-158">**image**</span></span>|<span data-ttu-id="25192-159">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="25192-159">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="25192-160">Puede encontrar esta información en la vista de catálogo **sys.server_principals** .</span><span class="sxs-lookup"><span data-stu-id="25192-160">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="25192-161">Cada SID es único para cada inicio de sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="25192-161">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="25192-162">41</span><span class="sxs-lookup"><span data-stu-id="25192-162">41</span></span>|<span data-ttu-id="25192-163">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-163">Yes</span></span>|  
|<span data-ttu-id="25192-164">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="25192-164">**NTDomainName**</span></span>|<span data-ttu-id="25192-165">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-165">**nvarchar**</span></span>|<span data-ttu-id="25192-166">Dominio de Windows al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="25192-166">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="25192-167">7</span><span class="sxs-lookup"><span data-stu-id="25192-167">7</span></span>|<span data-ttu-id="25192-168">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-168">Yes</span></span>|  
|<span data-ttu-id="25192-169">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="25192-169">**NTUserName**</span></span>|<span data-ttu-id="25192-170">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-170">**nvarchar**</span></span>|<span data-ttu-id="25192-171">Nombre del usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="25192-171">Windows user name.</span></span>|<span data-ttu-id="25192-172">6</span><span class="sxs-lookup"><span data-stu-id="25192-172">6</span></span>|<span data-ttu-id="25192-173">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-173">Yes</span></span>|  
|<span data-ttu-id="25192-174">**ObjectName**</span><span class="sxs-lookup"><span data-stu-id="25192-174">**ObjectName**</span></span>|<span data-ttu-id="25192-175">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-175">**nvarchar**</span></span>|<span data-ttu-id="25192-176">Nombre del objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="25192-176">Name of the object being referenced.</span></span>|<span data-ttu-id="25192-177">34</span><span class="sxs-lookup"><span data-stu-id="25192-177">34</span></span>|<span data-ttu-id="25192-178">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-178">Yes</span></span>|  
|<span data-ttu-id="25192-179">**ObjectType**</span><span class="sxs-lookup"><span data-stu-id="25192-179">**ObjectType**</span></span>|<span data-ttu-id="25192-180">**int**</span><span class="sxs-lookup"><span data-stu-id="25192-180">**int**</span></span>|<span data-ttu-id="25192-181">Valor que representa el tipo del objeto implicado en el evento.</span><span class="sxs-lookup"><span data-stu-id="25192-181">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="25192-182">El valor que se devuelve para esta columna es una combinación del valor correspondiente de la columna **type** en la vista de catálogo **sys.objects** y los valores enumerados en [Columna de evento de seguimiento ObjectType](objecttype-trace-event-column.md).</span><span class="sxs-lookup"><span data-stu-id="25192-182">The value returned for this column is a combination of the corresponding value in the **type** column in the **sys.objects** catalog view and the values listed in [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span>|<span data-ttu-id="25192-183">28</span><span class="sxs-lookup"><span data-stu-id="25192-183">28</span></span>|<span data-ttu-id="25192-184">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-184">Yes</span></span>|  
|<span data-ttu-id="25192-185">**OwnerName**</span><span class="sxs-lookup"><span data-stu-id="25192-185">**OwnerName**</span></span>|<span data-ttu-id="25192-186">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-186">**nvarchar**</span></span>|<span data-ttu-id="25192-187">Nombre de usuario de base de datos del propietario del objeto.</span><span class="sxs-lookup"><span data-stu-id="25192-187">Database user name of the object owner.</span></span>|<span data-ttu-id="25192-188">37</span><span class="sxs-lookup"><span data-stu-id="25192-188">37</span></span>|<span data-ttu-id="25192-189">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-189">Yes</span></span>|  
|<span data-ttu-id="25192-190">**ParentName**</span><span class="sxs-lookup"><span data-stu-id="25192-190">**ParentName**</span></span>|<span data-ttu-id="25192-191">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-191">**nvarchar**</span></span>|<span data-ttu-id="25192-192">Nombre del esquema en el que se encuentra el objeto.</span><span class="sxs-lookup"><span data-stu-id="25192-192">Name of the schema that the object is in.</span></span>|<span data-ttu-id="25192-193">59</span><span class="sxs-lookup"><span data-stu-id="25192-193">59</span></span>|<span data-ttu-id="25192-194">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-194">Yes</span></span>|  
|<span data-ttu-id="25192-195">**IdSolicitud**</span><span class="sxs-lookup"><span data-stu-id="25192-195">**RequestID**</span></span>|<span data-ttu-id="25192-196">**int**</span><span class="sxs-lookup"><span data-stu-id="25192-196">**int**</span></span>|<span data-ttu-id="25192-197">Identificador de la solicitud que contiene la instrucción.</span><span class="sxs-lookup"><span data-stu-id="25192-197">ID of the request containing the statement.</span></span>|<span data-ttu-id="25192-198">49</span><span class="sxs-lookup"><span data-stu-id="25192-198">49</span></span>|<span data-ttu-id="25192-199">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-199">Yes</span></span>|  
|<span data-ttu-id="25192-200">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="25192-200">**ServerName**</span></span>|<span data-ttu-id="25192-201">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-201">**nvarchar**</span></span>|<span data-ttu-id="25192-202">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="25192-202">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="25192-203">26</span><span class="sxs-lookup"><span data-stu-id="25192-203">26</span></span>|<span data-ttu-id="25192-204">No</span><span class="sxs-lookup"><span data-stu-id="25192-204">No</span></span>|  
|<span data-ttu-id="25192-205">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="25192-205">**SessionLoginName**</span></span>|<span data-ttu-id="25192-206">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-206">**nvarchar**</span></span>|<span data-ttu-id="25192-207">Nombre de inicio de sesión del usuario que originó la sesión.</span><span class="sxs-lookup"><span data-stu-id="25192-207">Login name of the user who originated the session.</span></span> <span data-ttu-id="25192-208">Por ejemplo, si se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando inicioDeSesión1 y ejecuta una instrucción como inicioDeSesión2, **SessionLoginName** muestra inicioDeSesión1 y **LoginName** muestra inicioDeSesión2.</span><span class="sxs-lookup"><span data-stu-id="25192-208">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="25192-209">En esta columna se muestran los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y de Windows.</span><span class="sxs-lookup"><span data-stu-id="25192-209">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="25192-210">64</span><span class="sxs-lookup"><span data-stu-id="25192-210">64</span></span>|<span data-ttu-id="25192-211">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-211">Yes</span></span>|  
|<span data-ttu-id="25192-212">**SPID**</span><span class="sxs-lookup"><span data-stu-id="25192-212">**SPID**</span></span>|<span data-ttu-id="25192-213">**int**</span><span class="sxs-lookup"><span data-stu-id="25192-213">**int**</span></span>|<span data-ttu-id="25192-214">Identificador de la sesión en la que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="25192-214">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="25192-215">12</span><span class="sxs-lookup"><span data-stu-id="25192-215">12</span></span>|<span data-ttu-id="25192-216">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-216">Yes</span></span>|  
|<span data-ttu-id="25192-217">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="25192-217">**StartTime**</span></span>|<span data-ttu-id="25192-218">**datetime**</span><span class="sxs-lookup"><span data-stu-id="25192-218">**datetime**</span></span>|<span data-ttu-id="25192-219">Hora a la que se inició el evento, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="25192-219">Time at which the event started, if available.</span></span>|<span data-ttu-id="25192-220">14</span><span class="sxs-lookup"><span data-stu-id="25192-220">14</span></span>|<span data-ttu-id="25192-221">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-221">Yes</span></span>|  
|<span data-ttu-id="25192-222">**Success**</span><span class="sxs-lookup"><span data-stu-id="25192-222">**Success**</span></span>|<span data-ttu-id="25192-223">**int**</span><span class="sxs-lookup"><span data-stu-id="25192-223">**int**</span></span>|<span data-ttu-id="25192-224">1 = correcto.</span><span class="sxs-lookup"><span data-stu-id="25192-224">1 = success.</span></span> <span data-ttu-id="25192-225">0 = error</span><span class="sxs-lookup"><span data-stu-id="25192-225">0 = failure.</span></span> <span data-ttu-id="25192-226">Por ejemplo, el valor 1 significa que se ha comprobado un permiso correctamente y el valor 0 indica que se ha producido un error en la comprobación.</span><span class="sxs-lookup"><span data-stu-id="25192-226">For example, a value of 1 indicates success of a permissions check and a value of 0 indicates failure of that check.</span></span>|<span data-ttu-id="25192-227">23</span><span class="sxs-lookup"><span data-stu-id="25192-227">23</span></span>|<span data-ttu-id="25192-228">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-228">Yes</span></span>|  
|<span data-ttu-id="25192-229">**TargetUserName**</span><span class="sxs-lookup"><span data-stu-id="25192-229">**TargetUserName**</span></span>|<span data-ttu-id="25192-230">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="25192-230">**nvarchar**</span></span>|<span data-ttu-id="25192-231">Para acciones dirigidas a un usuario de base de datos (por ejemplo, conceder permiso a un usuario), el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="25192-231">For actions that target a database user (for example, granting permission to a user), the name of that user.</span></span>|<span data-ttu-id="25192-232">39</span><span class="sxs-lookup"><span data-stu-id="25192-232">39</span></span>|<span data-ttu-id="25192-233">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-233">Yes</span></span>|  
|<span data-ttu-id="25192-234">**TextData**</span><span class="sxs-lookup"><span data-stu-id="25192-234">**TextData**</span></span>|<span data-ttu-id="25192-235">**ntext**</span><span class="sxs-lookup"><span data-stu-id="25192-235">**ntext**</span></span>|<span data-ttu-id="25192-236">Valor de texto que depende de la clase de eventos capturada en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="25192-236">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="25192-237">1</span><span class="sxs-lookup"><span data-stu-id="25192-237">1</span></span>|<span data-ttu-id="25192-238">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-238">Yes</span></span>|  
|<span data-ttu-id="25192-239">**TransactionID**</span><span class="sxs-lookup"><span data-stu-id="25192-239">**TransactionID**</span></span>|<span data-ttu-id="25192-240">**bigint**</span><span class="sxs-lookup"><span data-stu-id="25192-240">**bigint**</span></span>|<span data-ttu-id="25192-241">Id. de la transacción asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="25192-241">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="25192-242">4</span><span class="sxs-lookup"><span data-stu-id="25192-242">4</span></span>|<span data-ttu-id="25192-243">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-243">Yes</span></span>|  
|<span data-ttu-id="25192-244">**XactSequence**</span><span class="sxs-lookup"><span data-stu-id="25192-244">**XactSequence**</span></span>|<span data-ttu-id="25192-245">**bigint**</span><span class="sxs-lookup"><span data-stu-id="25192-245">**bigint**</span></span>|<span data-ttu-id="25192-246">Token que se utiliza para describir la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="25192-246">Token used to describe the current transaction.</span></span>|<span data-ttu-id="25192-247">50</span><span class="sxs-lookup"><span data-stu-id="25192-247">50</span></span>|<span data-ttu-id="25192-248">Sí</span><span class="sxs-lookup"><span data-stu-id="25192-248">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25192-249">Consulte también</span><span class="sxs-lookup"><span data-stu-id="25192-249">See Also</span></span>  
 <span data-ttu-id="25192-250">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25192-250">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="25192-251">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="25192-251">ALTER AUTHORIZATION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-authorization-transact-sql)  
  
  