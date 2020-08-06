---
title: Object:Deleted, clase de eventos |Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Object:Deleted event class
ms.assetid: d4db32bc-972d-4429-809a-a62047c33e79
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90bcc20e16d775e6497958fc1adc58269fb24296
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670406"
---
# <a name="objectdeleted-event-class"></a><span data-ttu-id="ab2eb-102">Object:Deleted, clase de eventos</span><span class="sxs-lookup"><span data-stu-id="ab2eb-102">Object:Deleted Event Class</span></span>
  <span data-ttu-id="ab2eb-103">La clase de eventos Object:Deleted indica que se ha eliminado un objeto; por ejemplo, mediante instrucciones DROP INDEX y DROP TABLE.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-103">The Object:Deleted event class indicates that an object has been deleted; for example, by DROP INDEX and DROP TABLE statements.</span></span> <span data-ttu-id="ab2eb-104">Esta clase de evento se puede utilizar para determinar si se están eliminando objetos; por ejemplo, con aplicaciones ODBC, que, a menudo, crean procedimientos almacenados temporales.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-104">This event class can be used to determine if objects are being deleted, for example, by ODBC applications that often create temporary stored procedures.</span></span>  
  
 <span data-ttu-id="ab2eb-105">Al supervisar las columnas de datos predeterminadas LoginName y NTUserName, además de las clases de eventos Objects, puede determinar el nombre del usuario que crea, elimina o tiene acceso a objetos.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-105">By monitoring the LoginName and NTUserName default data columns, in addition to the Objects event classes, you can determine the name of the user who is creating, deleting, or accessing objects.</span></span>  
  
## <a name="objectdeleted-event-class-data-columns"></a><span data-ttu-id="ab2eb-106">Columnas de datos de la clase de evento Object:Deleted</span><span class="sxs-lookup"><span data-stu-id="ab2eb-106">Object:Deleted Event Class Data Columns</span></span>  
  
|<span data-ttu-id="ab2eb-107">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="ab2eb-107">Data column name</span></span>|<span data-ttu-id="ab2eb-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="ab2eb-108">Data type</span></span>|<span data-ttu-id="ab2eb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab2eb-109">Description</span></span>|<span data-ttu-id="ab2eb-110">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="ab2eb-110">Column ID</span></span>|<span data-ttu-id="ab2eb-111">Filtrable</span><span class="sxs-lookup"><span data-stu-id="ab2eb-111">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="ab2eb-112">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="ab2eb-112">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-113">Nombre de la aplicación cliente que ha creado la conexión a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab2eb-113">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ab2eb-114">Esta columna se rellena con los valores que pasa la aplicación, en lugar de con el nombre que se muestra para el programa.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-114">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="ab2eb-115">10</span><span class="sxs-lookup"><span data-stu-id="ab2eb-115">10</span></span>|<span data-ttu-id="ab2eb-116">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-116">Yes</span></span>|  
|<span data-ttu-id="ab2eb-117">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="ab2eb-117">ClientProcessID</span></span>|`int`|<span data-ttu-id="ab2eb-118">Identificador que el equipo host asigna al proceso en el que se ejecuta la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-118">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="ab2eb-119">Esta columna de datos se rellena si el cliente proporciona su identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-119">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="ab2eb-120">9</span><span class="sxs-lookup"><span data-stu-id="ab2eb-120">9</span></span>|<span data-ttu-id="ab2eb-121">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-121">Yes</span></span>|  
|<span data-ttu-id="ab2eb-122">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="ab2eb-122">DatabaseID</span></span>|`int`|<span data-ttu-id="ab2eb-123">Identificador de la base de datos especificada mediante la instrucción USE *database* o la base de datos predeterminada si no se emite la instrucción USE *database* para una determinada instancia.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-123">ID of the database specified by the USE *database* statement or the default database if no USE *database* statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="ab2eb-124">muestra el nombre de la base de datos si se captura la columna de datos ServerName en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-124">displays the name of the database if the ServerName data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="ab2eb-125">Determina el valor de una base de datos mediante la función DB_ID.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-125">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="ab2eb-126">3</span><span class="sxs-lookup"><span data-stu-id="ab2eb-126">3</span></span>|<span data-ttu-id="ab2eb-127">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-127">Yes</span></span>|  
|<span data-ttu-id="ab2eb-128">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="ab2eb-128">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-129">Nombre de la base de datos en la que se ejecuta la instrucción del usuario.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-129">Name of the database in which the user statement is running.</span></span>|<span data-ttu-id="ab2eb-130">35</span><span class="sxs-lookup"><span data-stu-id="ab2eb-130">35</span></span>|<span data-ttu-id="ab2eb-131">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-131">Yes</span></span>|  
|<span data-ttu-id="ab2eb-132">EventClass</span><span class="sxs-lookup"><span data-stu-id="ab2eb-132">EventClass</span></span>|`int`|<span data-ttu-id="ab2eb-133">Tipo de evento = 47.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-133">Type of event = 47.</span></span>|<span data-ttu-id="ab2eb-134">27</span><span class="sxs-lookup"><span data-stu-id="ab2eb-134">27</span></span>|<span data-ttu-id="ab2eb-135">No</span><span class="sxs-lookup"><span data-stu-id="ab2eb-135">No</span></span>|  
|<span data-ttu-id="ab2eb-136">EventSequence</span><span class="sxs-lookup"><span data-stu-id="ab2eb-136">EventSequence</span></span>|`int`|<span data-ttu-id="ab2eb-137">Secuencia de un evento determinado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-137">Sequence of a given event within the request.</span></span>|<span data-ttu-id="ab2eb-138">51</span><span class="sxs-lookup"><span data-stu-id="ab2eb-138">51</span></span>|<span data-ttu-id="ab2eb-139">No</span><span class="sxs-lookup"><span data-stu-id="ab2eb-139">No</span></span>|  
|<span data-ttu-id="ab2eb-140">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="ab2eb-140">EventSubClass</span></span>|`int`|<span data-ttu-id="ab2eb-141">Tipo de la subclase de eventos.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-141">Type of event subclass.</span></span><br /><br /> <span data-ttu-id="ab2eb-142">0=Principio</span><span class="sxs-lookup"><span data-stu-id="ab2eb-142">0=Begin</span></span><br /><br /> <span data-ttu-id="ab2eb-143">1=Confirmar</span><span class="sxs-lookup"><span data-stu-id="ab2eb-143">1=Commit</span></span><br /><br /> <span data-ttu-id="ab2eb-144">2=Revertir</span><span class="sxs-lookup"><span data-stu-id="ab2eb-144">2=Rollback</span></span>|<span data-ttu-id="ab2eb-145">21</span><span class="sxs-lookup"><span data-stu-id="ab2eb-145">21</span></span>|<span data-ttu-id="ab2eb-146">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-146">Yes</span></span>|  
|<span data-ttu-id="ab2eb-147">GroupID</span><span class="sxs-lookup"><span data-stu-id="ab2eb-147">GroupID</span></span>|`int`|<span data-ttu-id="ab2eb-148">Id. del grupo de carga de trabajo donde se activa el evento de Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-148">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="ab2eb-149">66</span><span class="sxs-lookup"><span data-stu-id="ab2eb-149">66</span></span>|<span data-ttu-id="ab2eb-150">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-150">Yes</span></span>|  
|<span data-ttu-id="ab2eb-151">HostName</span><span class="sxs-lookup"><span data-stu-id="ab2eb-151">HostName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-152">Nombre del equipo en el que se está ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-152">Name of the computer on which the client is running.</span></span> <span data-ttu-id="ab2eb-153">Esta columna de datos se rellena si el cliente proporciona el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-153">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="ab2eb-154">Para determinar el nombre del host, utilice la función HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-154">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="ab2eb-155">8</span><span class="sxs-lookup"><span data-stu-id="ab2eb-155">8</span></span>|<span data-ttu-id="ab2eb-156">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-156">Yes</span></span>|  
|<span data-ttu-id="ab2eb-157">IndexID</span><span class="sxs-lookup"><span data-stu-id="ab2eb-157">IndexID</span></span>|`int`|<span data-ttu-id="ab2eb-158">Id. del índice del objeto afectado por el evento.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-158">ID for the index on the object affected by the event.</span></span> <span data-ttu-id="ab2eb-159">Para determinar el identificador de índice de un objeto, use la columna index_id de la vista de catálogo sys.indexes.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-159">To determine the index ID for an object, use the index_id column of the sys.indexes catalog view.</span></span>|<span data-ttu-id="ab2eb-160">24</span><span class="sxs-lookup"><span data-stu-id="ab2eb-160">24</span></span>|<span data-ttu-id="ab2eb-161">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-161">Yes</span></span>|  
|<span data-ttu-id="ab2eb-162">IntegerData</span><span class="sxs-lookup"><span data-stu-id="ab2eb-162">IntegerData</span></span>|`int`|<span data-ttu-id="ab2eb-163">Valor entero que depende de la clase de eventos capturada en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-163">Integer value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="ab2eb-164">25</span><span class="sxs-lookup"><span data-stu-id="ab2eb-164">25</span></span>|<span data-ttu-id="ab2eb-165">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-165">Yes</span></span>|  
|<span data-ttu-id="ab2eb-166">IsSystem</span><span class="sxs-lookup"><span data-stu-id="ab2eb-166">IsSystem</span></span>|`int`|<span data-ttu-id="ab2eb-167">Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-167">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="ab2eb-168">1 = sistema, 0 = usuario.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-168">1 = system, 0 = user.</span></span>|<span data-ttu-id="ab2eb-169">60</span><span class="sxs-lookup"><span data-stu-id="ab2eb-169">60</span></span>|<span data-ttu-id="ab2eb-170">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-170">Yes</span></span>|  
|<span data-ttu-id="ab2eb-171">LoginName</span><span class="sxs-lookup"><span data-stu-id="ab2eb-171">LoginName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-172">Nombre del inicio de sesión del usuario (inicio de sesión de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenciales de inicio de sesión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con el formato DOMINIO\nombreDeUsuario).</span><span class="sxs-lookup"><span data-stu-id="ab2eb-172">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="ab2eb-173">11</span><span class="sxs-lookup"><span data-stu-id="ab2eb-173">11</span></span>|<span data-ttu-id="ab2eb-174">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-174">Yes</span></span>|  
|<span data-ttu-id="ab2eb-175">LoginSid</span><span class="sxs-lookup"><span data-stu-id="ab2eb-175">LoginSid</span></span>|`image`|<span data-ttu-id="ab2eb-176">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-176">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="ab2eb-177">Puede buscar esta información en la vista de catálogo sys.server_principals.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-177">You can find this information in the sys.server_principals catalog view.</span></span> <span data-ttu-id="ab2eb-178">Cada SID es único para cada inicio de sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-178">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="ab2eb-179">41</span><span class="sxs-lookup"><span data-stu-id="ab2eb-179">41</span></span>|<span data-ttu-id="ab2eb-180">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-180">Yes</span></span>|  
|<span data-ttu-id="ab2eb-181">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="ab2eb-181">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-182">Dominio de Windows al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-182">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="ab2eb-183">7</span><span class="sxs-lookup"><span data-stu-id="ab2eb-183">7</span></span>|<span data-ttu-id="ab2eb-184">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-184">Yes</span></span>|  
|<span data-ttu-id="ab2eb-185">NTUserName</span><span class="sxs-lookup"><span data-stu-id="ab2eb-185">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-186">Nombre del usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-186">Windows user name.</span></span>|<span data-ttu-id="ab2eb-187">6</span><span class="sxs-lookup"><span data-stu-id="ab2eb-187">6</span></span>|<span data-ttu-id="ab2eb-188">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-188">Yes</span></span>|  
|<span data-ttu-id="ab2eb-189">ObjectID</span><span class="sxs-lookup"><span data-stu-id="ab2eb-189">ObjectID</span></span>|`int`|<span data-ttu-id="ab2eb-190">Identificador del objeto asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-190">System-assigned ID of the object.</span></span>|<span data-ttu-id="ab2eb-191">22</span><span class="sxs-lookup"><span data-stu-id="ab2eb-191">22</span></span>|<span data-ttu-id="ab2eb-192">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-192">Yes</span></span>|  
|<span data-ttu-id="ab2eb-193">ObjectID2</span><span class="sxs-lookup"><span data-stu-id="ab2eb-193">ObjectID2</span></span>|`bigint`|<span data-ttu-id="ab2eb-194">Id. de la entidad u objeto relacionado.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-194">ID of the related object or entity.</span></span>|<span data-ttu-id="ab2eb-195">56</span><span class="sxs-lookup"><span data-stu-id="ab2eb-195">56</span></span>|<span data-ttu-id="ab2eb-196">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-196">Yes</span></span>|  
|<span data-ttu-id="ab2eb-197">ObjectName</span><span class="sxs-lookup"><span data-stu-id="ab2eb-197">ObjectName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-198">Nombre del objeto al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-198">Name of the object being referenced.</span></span>|<span data-ttu-id="ab2eb-199">34</span><span class="sxs-lookup"><span data-stu-id="ab2eb-199">34</span></span>|<span data-ttu-id="ab2eb-200">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-200">Yes</span></span>|  
|<span data-ttu-id="ab2eb-201">ObjectType</span><span class="sxs-lookup"><span data-stu-id="ab2eb-201">ObjectType</span></span>|`int`|<span data-ttu-id="ab2eb-202">Valor que representa el tipo del objeto implicado en el evento.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-202">Value representing the type of the object involved in the event.</span></span> <span data-ttu-id="ab2eb-203">Este valor corresponde al de la columna Type de la tabla sys.objects.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-203">This value corresponds to the type column in sys.objects.</span></span> <span data-ttu-id="ab2eb-204">Para ver los valores, vea [Columna de evento de seguimiento ObjectType](objecttype-trace-event-column.md).</span><span class="sxs-lookup"><span data-stu-id="ab2eb-204">For values, see [ObjectType Trace Event Column](objecttype-trace-event-column.md).</span></span>|<span data-ttu-id="ab2eb-205">28</span><span class="sxs-lookup"><span data-stu-id="ab2eb-205">28</span></span>|<span data-ttu-id="ab2eb-206">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-206">Yes</span></span>|  
|<span data-ttu-id="ab2eb-207">RequestID</span><span class="sxs-lookup"><span data-stu-id="ab2eb-207">RequestID</span></span>|`int`|<span data-ttu-id="ab2eb-208">Identificador de la solicitud que contiene la instrucción.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-208">ID of the request containing the statement.</span></span>|<span data-ttu-id="ab2eb-209">49</span><span class="sxs-lookup"><span data-stu-id="ab2eb-209">49</span></span>|<span data-ttu-id="ab2eb-210">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-210">Yes</span></span>|  
|<span data-ttu-id="ab2eb-211">nombreDeServidor</span><span class="sxs-lookup"><span data-stu-id="ab2eb-211">ServerName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-212">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-212">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="ab2eb-213">26</span><span class="sxs-lookup"><span data-stu-id="ab2eb-213">26</span></span>|<span data-ttu-id="ab2eb-214">No</span><span class="sxs-lookup"><span data-stu-id="ab2eb-214">No</span></span>|  
|<span data-ttu-id="ab2eb-215">SessionLoginName</span><span class="sxs-lookup"><span data-stu-id="ab2eb-215">SessionLoginName</span></span>|`nvarchar`|<span data-ttu-id="ab2eb-216">Nombre de inicio de sesión del usuario que originó la sesión.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-216">The login name of the user who originated the session.</span></span> <span data-ttu-id="ab2eb-217">Por ejemplo, si se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando inicioDeSesión1 y ejecuta una instrucción como inicioDeSesión2, SessionLoginName muestra inicioDeSesión1 y LoginName muestra inicioDeSesión2.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-217">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, SessionLoginName shows Login1 and LoginName shows Login2.</span></span> <span data-ttu-id="ab2eb-218">En esta columna se muestran los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y de Windows.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-218">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="ab2eb-219">64</span><span class="sxs-lookup"><span data-stu-id="ab2eb-219">64</span></span>|<span data-ttu-id="ab2eb-220">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-220">Yes</span></span>|  
|<span data-ttu-id="ab2eb-221">SPID</span><span class="sxs-lookup"><span data-stu-id="ab2eb-221">SPID</span></span>|`int`|<span data-ttu-id="ab2eb-222">Identificador de la sesión en la que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-222">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="ab2eb-223">12</span><span class="sxs-lookup"><span data-stu-id="ab2eb-223">12</span></span>|<span data-ttu-id="ab2eb-224">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-224">Yes</span></span>|  
|<span data-ttu-id="ab2eb-225">StartTime</span><span class="sxs-lookup"><span data-stu-id="ab2eb-225">StartTime</span></span>|`datetime`|<span data-ttu-id="ab2eb-226">Hora a la que se inició el evento, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-226">Time at which the event started, if available.</span></span>|<span data-ttu-id="ab2eb-227">14</span><span class="sxs-lookup"><span data-stu-id="ab2eb-227">14</span></span>|<span data-ttu-id="ab2eb-228">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-228">Yes</span></span>|  
|<span data-ttu-id="ab2eb-229">TransactionID</span><span class="sxs-lookup"><span data-stu-id="ab2eb-229">TransactionID</span></span>|`bigint`|<span data-ttu-id="ab2eb-230">Id. de la transacción asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-230">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="ab2eb-231">4</span><span class="sxs-lookup"><span data-stu-id="ab2eb-231">4</span></span>|<span data-ttu-id="ab2eb-232">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-232">Yes</span></span>|  
|<span data-ttu-id="ab2eb-233">XactSequence</span><span class="sxs-lookup"><span data-stu-id="ab2eb-233">XactSequence</span></span>|`bigint`|<span data-ttu-id="ab2eb-234">Token que se utiliza para describir la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="ab2eb-234">Token used to describe the current transaction.</span></span>|<span data-ttu-id="ab2eb-235">50</span><span class="sxs-lookup"><span data-stu-id="ab2eb-235">50</span></span>|<span data-ttu-id="ab2eb-236">Sí</span><span class="sxs-lookup"><span data-stu-id="ab2eb-236">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab2eb-237">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ab2eb-237">See Also</span></span>  
 <span data-ttu-id="ab2eb-238">[Eventos extendidos](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="ab2eb-238">[Extended Events](../extended-events/extended-events.md) </span></span>  
 [<span data-ttu-id="ab2eb-239">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ab2eb-239">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  