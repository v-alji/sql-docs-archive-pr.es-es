---
title: Clase de eventos Lock:Escalation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Escalation event class
- lock escalation [SQL Server], event class
ms.assetid: d253b44c-7600-4afa-a3a7-03cc937c6a4b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9bf476175245000ba63e058ca333953d07276076
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674816"
---
# <a name="lockescalation-event-class"></a><span data-ttu-id="bd7a1-102">Lock:Escalation (clase de eventos)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-102">Lock:Escalation Event Class</span></span>
  <span data-ttu-id="bd7a1-103">La clase de eventos **Lock:Escalation** indica que un bloqueo específico se ha convertido en un bloqueo general; por ejemplo, un bloqueo de fila se ha convertido en un bloqueo de objeto.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-103">The **Lock:Escalation** event class indicates that a finer-grained lock has been converted to a coarser-grained lock; for example, a row lock that is converted to an object lock.</span></span> <span data-ttu-id="bd7a1-104">La clase de eventos de ampliación tiene Id. de Evento 60.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-104">The escalation event class is Event ID 60.</span></span>  
  
## <a name="lockescalation-event-class-data-columns"></a><span data-ttu-id="bd7a1-105">Columnas de datos de la clase de evento Lock:Escalation</span><span class="sxs-lookup"><span data-stu-id="bd7a1-105">Lock:Escalation Event Class Data Columns</span></span>  
  
|<span data-ttu-id="bd7a1-106">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="bd7a1-106">Data column name</span></span>|<span data-ttu-id="bd7a1-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="bd7a1-107">Data type</span></span>|<span data-ttu-id="bd7a1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd7a1-108">Description</span></span>|<span data-ttu-id="bd7a1-109">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="bd7a1-109">Column ID</span></span>|<span data-ttu-id="bd7a1-110">Filtrable</span><span class="sxs-lookup"><span data-stu-id="bd7a1-110">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="bd7a1-111">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-111">**ApplicationName**</span></span>|`nvarchar`|<span data-ttu-id="bd7a1-112">Nombre de la aplicación cliente que ha creado la conexión a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd7a1-112">Name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bd7a1-113">Esta columna se rellena con los valores que pasa la aplicación, en lugar de con el nombre que se muestra para el programa.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-113">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="bd7a1-114">10</span><span class="sxs-lookup"><span data-stu-id="bd7a1-114">10</span></span>|<span data-ttu-id="bd7a1-115">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-115">Yes</span></span>|  
|<span data-ttu-id="bd7a1-116">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-116">**ClientProcessID**</span></span>|`int`|<span data-ttu-id="bd7a1-117">Identificador que el equipo host asigna al proceso en el que se ejecuta la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-117">ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="bd7a1-118">Esta columna de datos se rellena si el cliente proporciona el identificador de proceso del cliente.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-118">This data column is populated if the client provides the client process ID.</span></span>|<span data-ttu-id="bd7a1-119">9</span><span class="sxs-lookup"><span data-stu-id="bd7a1-119">9</span></span>|<span data-ttu-id="bd7a1-120">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-120">Yes</span></span>|  
|<span data-ttu-id="bd7a1-121">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-121">**DatabaseID**</span></span>|`int`|<span data-ttu-id="bd7a1-122">Identificador de la base de datos en la que se ha adquirido el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-122">ID of the database in which the lock was acquired.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="bd7a1-123">muestra el nombre de la base de datos si se captura la columna de datos **ServerName** en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-123">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="bd7a1-124">Determina el valor de una base de datos mediante la función DB_ID.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-124">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="bd7a1-125">3</span><span class="sxs-lookup"><span data-stu-id="bd7a1-125">3</span></span>|<span data-ttu-id="bd7a1-126">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-126">Yes</span></span>|  
|<span data-ttu-id="bd7a1-127">**DatabaseName**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-127">**DatabaseName**</span></span>|`nvarchar`|<span data-ttu-id="bd7a1-128">Nombre de la base de datos en la que ha ocurrido la extensión.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-128">Name of the database in which the escalation occurred.</span></span>|<span data-ttu-id="bd7a1-129">35</span><span class="sxs-lookup"><span data-stu-id="bd7a1-129">35</span></span>|<span data-ttu-id="bd7a1-130">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-130">Yes</span></span>|  
|<span data-ttu-id="bd7a1-131">**EventClass**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-131">**EventClass**</span></span>|`int`|<span data-ttu-id="bd7a1-132">Tipo de evento = 60.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-132">Type of event = 60.</span></span>|<span data-ttu-id="bd7a1-133">27</span><span class="sxs-lookup"><span data-stu-id="bd7a1-133">27</span></span>|<span data-ttu-id="bd7a1-134">No</span><span class="sxs-lookup"><span data-stu-id="bd7a1-134">No</span></span>|  
|<span data-ttu-id="bd7a1-135">**EventSubClass**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-135">**EventSubClass**</span></span>|`int`|<span data-ttu-id="bd7a1-136">Causa de la ampliación del bloqueo:</span><span class="sxs-lookup"><span data-stu-id="bd7a1-136">Cause of the lock escalation:</span></span><br /><br /> <span data-ttu-id="bd7a1-137">**0 - LOCK_THRESHOLD** indica que la instrucción superó el umbral del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-137">**0 - LOCK_THRESHOLD** indicates the statement exceeded the lock threshold.</span></span><br /><br /> <span data-ttu-id="bd7a1-138">**1 - MEMORY_THRESHOLD** indica que la instrucción superó el umbral de memoria.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-138">**1 - MEMORY_THRESHOLD** indicates the statement exceeded the memory threshold.</span></span>|<span data-ttu-id="bd7a1-139">21</span><span class="sxs-lookup"><span data-stu-id="bd7a1-139">21</span></span>|<span data-ttu-id="bd7a1-140">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-140">Yes</span></span>|  
|<span data-ttu-id="bd7a1-141">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-141">**EventSequence**</span></span>|`int`|<span data-ttu-id="bd7a1-142">Secuencia de un evento determinado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-142">Sequence of a given event within the request.</span></span>|<span data-ttu-id="bd7a1-143">51</span><span class="sxs-lookup"><span data-stu-id="bd7a1-143">51</span></span>|<span data-ttu-id="bd7a1-144">No</span><span class="sxs-lookup"><span data-stu-id="bd7a1-144">No</span></span>|  
|<span data-ttu-id="bd7a1-145">**GroupID**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-145">**GroupID**</span></span>|`int`|<span data-ttu-id="bd7a1-146">Id. del grupo de carga de trabajo donde se activa el evento de Seguimiento de SQL.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-146">ID of the workload group where the SQL Trace event fires.</span></span>|<span data-ttu-id="bd7a1-147">66</span><span class="sxs-lookup"><span data-stu-id="bd7a1-147">66</span></span>|<span data-ttu-id="bd7a1-148">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-148">Yes</span></span>|  
|<span data-ttu-id="bd7a1-149">**HostName**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-149">**HostName**</span></span>|`nvarchar`|<span data-ttu-id="bd7a1-150">Nombre del equipo en el que se está ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-150">Name of the computer on which the client is running.</span></span> <span data-ttu-id="bd7a1-151">Esta columna de datos se rellena si el cliente proporciona el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-151">This data column is populated if the client provides the host name.</span></span> <span data-ttu-id="bd7a1-152">Para determinar el nombre del host, utilice la función HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-152">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="bd7a1-153">8</span><span class="sxs-lookup"><span data-stu-id="bd7a1-153">8</span></span>|<span data-ttu-id="bd7a1-154">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-154">Yes</span></span>|  
|<span data-ttu-id="bd7a1-155">**IntegerData**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-155">**IntegerData**</span></span>|`int`|<span data-ttu-id="bd7a1-156">Recuento de bloqueo de HoBT.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-156">HoBT lock count.</span></span> <span data-ttu-id="bd7a1-157">El número de bloqueos para el HoBT en el momento de la ampliación del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-157">The number of locks for the HoBT at the time of lock escalation.</span></span>|<span data-ttu-id="bd7a1-158">25</span><span class="sxs-lookup"><span data-stu-id="bd7a1-158">25</span></span>|<span data-ttu-id="bd7a1-159">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-159">Yes</span></span>|  
|<span data-ttu-id="bd7a1-160">**IntegerData2**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-160">**IntegerData2**</span></span>|`int`|<span data-ttu-id="bd7a1-161">Recuento de la ampliación del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-161">Escalated lock count.</span></span> <span data-ttu-id="bd7a1-162">El número total de bloqueos que se convirtieron.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-162">The total number of locks that were converted.</span></span> <span data-ttu-id="bd7a1-163">Se cancelan las asignaciones de estas estructuras de bloqueo porque ya están cubiertas por el bloqueo ampliado.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-163">These lock structures are deallocated because they are already covered by the escalated lock.</span></span>|<span data-ttu-id="bd7a1-164">55</span><span class="sxs-lookup"><span data-stu-id="bd7a1-164">55</span></span>|<span data-ttu-id="bd7a1-165">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-165">Yes</span></span>|  
|<span data-ttu-id="bd7a1-166">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-166">**IsSystem**</span></span>|`int`|<span data-ttu-id="bd7a1-167">Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-167">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="bd7a1-168">1 = sistema, 0 = usuario.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-168">1 = system, 0 = user.</span></span>|<span data-ttu-id="bd7a1-169">60</span><span class="sxs-lookup"><span data-stu-id="bd7a1-169">60</span></span>|<span data-ttu-id="bd7a1-170">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-170">Yes</span></span>|  
|<span data-ttu-id="bd7a1-171">**LineNumber**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-171">**LineNumber**</span></span>|`int`|<span data-ttu-id="bd7a1-172">Número de línea de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd7a1-172">Line number of [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>|<span data-ttu-id="bd7a1-173">5</span><span class="sxs-lookup"><span data-stu-id="bd7a1-173">5</span></span>|<span data-ttu-id="bd7a1-174">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-174">Yes</span></span>|  
|<span data-ttu-id="bd7a1-175">**LoginName**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-175">**LoginName**</span></span>|`nvarchar`|<span data-ttu-id="bd7a1-176">Nombre del inicio de sesión del usuario (inicio de sesión de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenciales de inicio de sesión de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows con el formato DOMINIO\nombreDeUsuario).</span><span class="sxs-lookup"><span data-stu-id="bd7a1-176">Name of the login of the user (either [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security login or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows login credentials in the form of DOMAIN\username).</span></span>|<span data-ttu-id="bd7a1-177">11</span><span class="sxs-lookup"><span data-stu-id="bd7a1-177">11</span></span>|<span data-ttu-id="bd7a1-178">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-178">Yes</span></span>|  
|<span data-ttu-id="bd7a1-179">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-179">**LoginSid**</span></span>|`image`|<span data-ttu-id="bd7a1-180">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-180">Security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="bd7a1-181">Puede encontrar esta información en la vista de catálogo **sys.server_principals** .</span><span class="sxs-lookup"><span data-stu-id="bd7a1-181">You can find this information in the **sys.server_principals** catalog view.</span></span> <span data-ttu-id="bd7a1-182">Cada SID es único para cada inicio de sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-182">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="bd7a1-183">41</span><span class="sxs-lookup"><span data-stu-id="bd7a1-183">41</span></span>|<span data-ttu-id="bd7a1-184">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-184">Yes</span></span>|  
|<span data-ttu-id="bd7a1-185">**Modo**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-185">**Mode**</span></span>|`int`|<span data-ttu-id="bd7a1-186">Modo de bloqueo que resulta después de la ampliación:</span><span class="sxs-lookup"><span data-stu-id="bd7a1-186">Resulting lock mode after the escalation:</span></span><br /><br /> <span data-ttu-id="bd7a1-187">0=NULL: Compatible con los demás modos de bloqueo (LCK_M_NL)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-187">0=NULL - Compatible with all other lock modes (LCK_M_NL)</span></span><br /><br /> <span data-ttu-id="bd7a1-188">1=Bloqueo Estabilidad del esquema (LCK_M_SCH_S)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-188">1=Schema Stability lock (LCK_M_SCH_S)</span></span><br /><br /> <span data-ttu-id="bd7a1-189">2=Bloqueo Modificación del esquema (LCK_M_SCH_M)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-189">2=Schema Modification Lock (LCK_M_SCH_M)</span></span><br /><br /> <span data-ttu-id="bd7a1-190">3=Bloqueo Compartido (LCK_M_S)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-190">3=Shared Lock (LCK_M_S)</span></span><br /><br /> <span data-ttu-id="bd7a1-191">4=Bloqueo Actualizar (LCK_M_U)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-191">4=Update Lock (LCK_M_U)</span></span><br /><br /> <span data-ttu-id="bd7a1-192">5=Bloqueo Exclusivo (LCK_M_X)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-192">5=Exclusive Lock (LCK_M_X)</span></span><br /><br /> <span data-ttu-id="bd7a1-193">6=Bloqueo Intención compartida (LCK_M_IS)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-193">6=Intent Shared Lock (LCK_M_IS)</span></span><br /><br /> <span data-ttu-id="bd7a1-194">7=Bloqueo Actualizar intención (LCK_M_IU)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-194">7=Intent Update Lock (LCK_M_IU)</span></span><br /><br /> <span data-ttu-id="bd7a1-195">8=Bloqueo Intención exclusiva (LCK_M_IX)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-195">8=Intent Exclusive Lock (LCK_M_IX)</span></span><br /><br /> <span data-ttu-id="bd7a1-196">9=Actualizar intención compartida (LCK_M_SIU)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-196">9=Shared with intent to Update (LCK_M_SIU)</span></span><br /><br /> <span data-ttu-id="bd7a1-197">10=Intención compartida exclusiva (LCK_M_SIX)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-197">10=Shared with Intent Exclusive (LCK_M_SIX)</span></span><br /><br /> <span data-ttu-id="bd7a1-198">11=Actualizar intención exclusiva (LCK_M_UIX)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-198">11=Update with Intent Exclusive (LCK_M_UIX)</span></span><br /><br /> <span data-ttu-id="bd7a1-199">12=Bloqueo Actualización masiva (LCK_M_BU)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-199">12=Bulk Update Lock (LCK_M_BU)</span></span><br /><br /> <span data-ttu-id="bd7a1-200">13=Intervalo de claves compartido/compartido (LCK_M_RS_S)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-200">13=Key range Shared/Shared (LCK_M_RS_S)</span></span><br /><br /> <span data-ttu-id="bd7a1-201">14=Intervalo de claves compartido/actualización (LCK_M_RS_U)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-201">14=Key range Shared/Update (LCK_M_RS_U)</span></span><br /><br /> <span data-ttu-id="bd7a1-202">15=Intervalo de claves de inserción NULL (LCK_M_RI_NL)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-202">15=Key Range Insert NULL (LCK_M_RI_NL)</span></span><br /><br /> <span data-ttu-id="bd7a1-203">16=Intervalo de claves de inserción compartido (LCK_M_RI_S)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-203">16=Key Range Insert Shared (LCK_M_RI_S)</span></span><br /><br /> <span data-ttu-id="bd7a1-204">17=Intervalo de claves de inserción de actualización (LCK_M_RI_U)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-204">17=Key Range Insert Update (LCK_M_RI_U)</span></span><br /><br /> <span data-ttu-id="bd7a1-205">18=Intervalo de claves de inserción exclusivo (LCK_M_RI_X)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-205">18=Key Range Insert Exclusive (LCK_M_RI_X)</span></span><br /><br /> <span data-ttu-id="bd7a1-206">19=Intervalo de claves exclusivo compartido (LCK_M_RX_S)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-206">19=Key Range Exclusive Shared (LCK_M_RX_S)</span></span><br /><br /> <span data-ttu-id="bd7a1-207">20=Intervalo de claves exclusivo de actualización (LCK_M_RX_U)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-207">20=Key Range Exclusive Update (LCK_M_RX_U)</span></span><br /><br /> <span data-ttu-id="bd7a1-208">21=Intervalo de claves exclusivo exclusivo (LCK_M_RX_X)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-208">21=Key Range Exclusive Exclusive (LCK_M_RX_X)</span></span>|<span data-ttu-id="bd7a1-209">32</span><span class="sxs-lookup"><span data-stu-id="bd7a1-209">32</span></span>|<span data-ttu-id="bd7a1-210">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-210">Yes</span></span>|  
|<span data-ttu-id="bd7a1-211">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-211">**NTDomainName**</span></span>|`nvarchar`|<span data-ttu-id="bd7a1-212">Dominio de Windows al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-212">Windows domain to which the user belongs.</span></span>|<span data-ttu-id="bd7a1-213">7</span><span class="sxs-lookup"><span data-stu-id="bd7a1-213">7</span></span>|<span data-ttu-id="bd7a1-214">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-214">Yes</span></span>|  
|<span data-ttu-id="bd7a1-215">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-215">**NTUserName**</span></span>|`nvarchar`|<span data-ttu-id="bd7a1-216">Nombre del usuario de Windows.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-216">Windows user name.</span></span>|<span data-ttu-id="bd7a1-217">6</span><span class="sxs-lookup"><span data-stu-id="bd7a1-217">6</span></span>|<span data-ttu-id="bd7a1-218">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-218">Yes</span></span>|  
|<span data-ttu-id="bd7a1-219">**ObjectID**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-219">**ObjectID**</span></span>|`int`|<span data-ttu-id="bd7a1-220">Id. asignado por sistema de la tabla para la que se inició la ampliación del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-220">System-assigned ID of the table for which lock escalation was triggered.</span></span>|<span data-ttu-id="bd7a1-221">22</span><span class="sxs-lookup"><span data-stu-id="bd7a1-221">22</span></span>|<span data-ttu-id="bd7a1-222">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-222">Yes</span></span>|  
|<span data-ttu-id="bd7a1-223">**ObjectID2**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-223">**ObjectID2**</span></span>|`bigint`|<span data-ttu-id="bd7a1-224">Id. de la entidad u objeto relacionado.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-224">ID of the related object or entity.</span></span> <span data-ttu-id="bd7a1-225">(Id. del HoBT para el que se inició la ampliación del bloqueo).</span><span class="sxs-lookup"><span data-stu-id="bd7a1-225">(HoBT ID for which the lock escalation was triggered.)</span></span>|<span data-ttu-id="bd7a1-226">56</span><span class="sxs-lookup"><span data-stu-id="bd7a1-226">56</span></span>|<span data-ttu-id="bd7a1-227">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-227">Yes</span></span>|  
|<span data-ttu-id="bd7a1-228">**Posición**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-228">**Offset**</span></span>|`int`|<span data-ttu-id="bd7a1-229">Desplazamiento inicial de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd7a1-229">Starting offset of [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>|<span data-ttu-id="bd7a1-230">61</span><span class="sxs-lookup"><span data-stu-id="bd7a1-230">61</span></span>|<span data-ttu-id="bd7a1-231">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-231">Yes</span></span>|  
|<span data-ttu-id="bd7a1-232">**OwnerID**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-232">**OwnerID**</span></span>|`int`|<span data-ttu-id="bd7a1-233">1=TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="bd7a1-233">1=TRANSACTION</span></span><br /><br /> <span data-ttu-id="bd7a1-234">2=CURSOR</span><span class="sxs-lookup"><span data-stu-id="bd7a1-234">2=CURSOR</span></span><br /><br /> <span data-ttu-id="bd7a1-235">3=SESSION</span><span class="sxs-lookup"><span data-stu-id="bd7a1-235">3=SESSION</span></span><br /><br /> <span data-ttu-id="bd7a1-236">4=SHARED_TRANSACTION_WORKSPACE</span><span class="sxs-lookup"><span data-stu-id="bd7a1-236">4=SHARED_TRANSACTION_WORKSPACE</span></span><br /><br /> <span data-ttu-id="bd7a1-237">5=EXCLUSIVE_TRANSACTION_WORKSPACE</span><span class="sxs-lookup"><span data-stu-id="bd7a1-237">5=EXCLUSIVE_TRANSACTION_WORKSPACE</span></span><br /><br /> <span data-ttu-id="bd7a1-238">6=WAITFOR_QUERY</span><span class="sxs-lookup"><span data-stu-id="bd7a1-238">6=WAITFOR_QUERY</span></span>|<span data-ttu-id="bd7a1-239">58</span><span class="sxs-lookup"><span data-stu-id="bd7a1-239">58</span></span>|<span data-ttu-id="bd7a1-240">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-240">Yes</span></span>|  
|<span data-ttu-id="bd7a1-241">**IdSolicitud**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-241">**RequestID**</span></span>|`int`|<span data-ttu-id="bd7a1-242">Identificador de la solicitud que contiene la instrucción.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-242">ID of the request containing the statement.</span></span>|<span data-ttu-id="bd7a1-243">49</span><span class="sxs-lookup"><span data-stu-id="bd7a1-243">49</span></span>|<span data-ttu-id="bd7a1-244">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-244">Yes</span></span>|  
|<span data-ttu-id="bd7a1-245">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-245">**ServerName**</span></span>|`nvarchar`|<span data-ttu-id="bd7a1-246">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-246">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="bd7a1-247">26</span><span class="sxs-lookup"><span data-stu-id="bd7a1-247">26</span></span>|<span data-ttu-id="bd7a1-248">No</span><span class="sxs-lookup"><span data-stu-id="bd7a1-248">No</span></span>|  
|<span data-ttu-id="bd7a1-249">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-249">**SessionLoginName**</span></span>|`nvarchar`|<span data-ttu-id="bd7a1-250">Nombre de inicio de sesión del usuario que originó la sesión.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-250">Login name of the user who originated the session.</span></span> <span data-ttu-id="bd7a1-251">Por ejemplo, si se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando inicioDeSesión1 y ejecuta una instrucción como inicioDeSesión2, **SessionLoginName** muestra inicioDeSesión1 y **LoginName** muestra inicioDeSesión2.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-251">For example, if you connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1 and **LoginName** shows Login2.</span></span> <span data-ttu-id="bd7a1-252">En esta columna se muestran los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y de Windows.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-252">This column displays both [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="bd7a1-253">64</span><span class="sxs-lookup"><span data-stu-id="bd7a1-253">64</span></span>|<span data-ttu-id="bd7a1-254">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-254">Yes</span></span>|  
|<span data-ttu-id="bd7a1-255">**SPID**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-255">**SPID**</span></span>|`int`|<span data-ttu-id="bd7a1-256">Identificador de la sesión en la que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-256">ID of the session on which the event occurred.</span></span>|<span data-ttu-id="bd7a1-257">12</span><span class="sxs-lookup"><span data-stu-id="bd7a1-257">12</span></span>|<span data-ttu-id="bd7a1-258">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-258">Yes</span></span>|  
|<span data-ttu-id="bd7a1-259">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-259">**StartTime**</span></span>|`datetime`|<span data-ttu-id="bd7a1-260">Hora a la que se inició el evento, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-260">Time at which the event started, if available.</span></span>|<span data-ttu-id="bd7a1-261">14</span><span class="sxs-lookup"><span data-stu-id="bd7a1-261">14</span></span>|<span data-ttu-id="bd7a1-262">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-262">Yes</span></span>|  
|<span data-ttu-id="bd7a1-263">**TextData**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-263">**TextData**</span></span>|`ntext`|<span data-ttu-id="bd7a1-264">Texto de la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] que produjo la ampliación del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-264">Text of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that caused lock escalation.</span></span>|<span data-ttu-id="bd7a1-265">1</span><span class="sxs-lookup"><span data-stu-id="bd7a1-265">1</span></span>|<span data-ttu-id="bd7a1-266">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-266">Yes</span></span>|  
|<span data-ttu-id="bd7a1-267">**TransactionID**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-267">**TransactionID**</span></span>|`bigint`|<span data-ttu-id="bd7a1-268">Id. de la transacción asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-268">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="bd7a1-269">4</span><span class="sxs-lookup"><span data-stu-id="bd7a1-269">4</span></span>|<span data-ttu-id="bd7a1-270">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-270">Yes</span></span>|  
|<span data-ttu-id="bd7a1-271">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bd7a1-271">**Type**</span></span>|`int`|<span data-ttu-id="bd7a1-272">Granularidad de la ampliación del bloqueo:</span><span class="sxs-lookup"><span data-stu-id="bd7a1-272">Lock escalation granularity:</span></span><br /><br /> <span data-ttu-id="bd7a1-273">1=NULL_RESOURCE</span><span class="sxs-lookup"><span data-stu-id="bd7a1-273">1=NULL_RESOURCE</span></span><br /><br /> <span data-ttu-id="bd7a1-274">2=DATABASE</span><span class="sxs-lookup"><span data-stu-id="bd7a1-274">2=DATABASE</span></span><br /><br /> <span data-ttu-id="bd7a1-275">3=FILE</span><span class="sxs-lookup"><span data-stu-id="bd7a1-275">3=FILE</span></span><br /><br /> <span data-ttu-id="bd7a1-276">5=OBJECT (nivel de tabla)</span><span class="sxs-lookup"><span data-stu-id="bd7a1-276">5=OBJECT (table level)</span></span><br /><br /> <span data-ttu-id="bd7a1-277">6=PAGE</span><span class="sxs-lookup"><span data-stu-id="bd7a1-277">6=PAGE</span></span><br /><br /> <span data-ttu-id="bd7a1-278">7=KEY</span><span class="sxs-lookup"><span data-stu-id="bd7a1-278">7=KEY</span></span><br /><br /> <span data-ttu-id="bd7a1-279">8=EXTENT</span><span class="sxs-lookup"><span data-stu-id="bd7a1-279">8=EXTENT</span></span><br /><br /> <span data-ttu-id="bd7a1-280">9=RID</span><span class="sxs-lookup"><span data-stu-id="bd7a1-280">9=RID</span></span><br /><br /> <span data-ttu-id="bd7a1-281">10=APPLICATION</span><span class="sxs-lookup"><span data-stu-id="bd7a1-281">10=APPLICATION</span></span><br /><br /> <span data-ttu-id="bd7a1-282">11=METADATA</span><span class="sxs-lookup"><span data-stu-id="bd7a1-282">11=METADATA</span></span><br /><br /> <span data-ttu-id="bd7a1-283">12=HOBT</span><span class="sxs-lookup"><span data-stu-id="bd7a1-283">12=HOBT</span></span><br /><br /> <span data-ttu-id="bd7a1-284">13=ALLOCATION_UNIT</span><span class="sxs-lookup"><span data-stu-id="bd7a1-284">13=ALLOCATION_UNIT</span></span>|<span data-ttu-id="bd7a1-285">57</span><span class="sxs-lookup"><span data-stu-id="bd7a1-285">57</span></span>|<span data-ttu-id="bd7a1-286">Sí</span><span class="sxs-lookup"><span data-stu-id="bd7a1-286">Yes</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="bd7a1-287">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="bd7a1-287">Examples</span></span>  
 <span data-ttu-id="bd7a1-288">El ejemplo siguiente utiliza el procedimiento `sp_trace_create` para crear un seguimiento, utiliza `sp_trace_setevent` para agregar las columnas de ampliación del bloqueo al seguimiento y, a continuación, utiliza `sp_trace_setstatus` para iniciar dicho seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-288">The following example uses the `sp_trace_create` procedure to create a trace, uses `sp_trace_setevent` to add lock escalation columns to the trace, and then uses `sp_trace_setstatus` to start the trace.</span></span> <span data-ttu-id="bd7a1-289">En instrucciones como `EXEC sp_trace_setevent @TraceID, 60, 22, 1`, el número `60` indica la clase de eventos de ampliación, `22` indica la columna **ObjectID** y `1` establece el evento de seguimiento en ON.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-289">In statements such as `EXEC sp_trace_setevent @TraceID, 60, 22, 1`, the number `60` indicates the escalation event class, `22` indicates the **ObjectID** column, and `1` sets the trace event to ON.</span></span>  
  
```  
DECLARE @RC int, @TraceID int;  
EXEC @rc = sp_trace_create @TraceID output, 0, N'C:\TraceResults';  
-- Set the events and data columns you need to capture.  
EXEC sp_trace_setevent @TraceID, 60,  1, 1; --  1 = TextData  
EXEC sp_trace_setevent @TraceID, 60, 12, 1; -- 12 = SPID  
EXEC sp_trace_setevent @TraceID, 60, 21, 1; -- 21 = EventSubClass  
EXEC sp_trace_setevent @TraceID, 60, 22, 1; -- 22 = ObjectID  
EXEC sp_trace_setevent @TraceID, 60, 25, 1; -- 25 = IntegerData  
EXEC sp_trace_setevent @TraceID, 60, 55, 1; -- 25 = IntegerData2  
EXEC sp_trace_setevent @TraceID, 60, 57, 1; -- 57 = Type  
-- Set any filter  by using sp_trace_setfilter.  
-- Start the trace.  
EXEC sp_trace_setstatus @TraceID, 1;  
GO  
```  
  
 <span data-ttu-id="bd7a1-290">Ahora que el seguimiento se está ejecutando, ejecute las instrucciones que desea supervisar.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-290">Now that the trace is running, execute the statements that you want to trace.</span></span> <span data-ttu-id="bd7a1-291">Cuando finalicen, ejecute el código siguiente para detener y después cerrar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bd7a1-291">When they finish, execute the following code to stop and then close the trace.</span></span> <span data-ttu-id="bd7a1-292">Este ejemplo utiliza la función `fn_trace_getinfo` para obtener el `traceid` que se utilizará en las instrucciones `sp_trace_setstatus` .</span><span class="sxs-lookup"><span data-stu-id="bd7a1-292">This example uses the `fn_trace_getinfo` function to get the `traceid` to be used in the `sp_trace_setstatus` statements.</span></span>  
  
```  
-- After the trace is complete.  
DECLARE @TraceID int;  
-- Find the traceid of the current trace.  
SELECT @TraceID = traceid   
FROM ::fn_trace_getinfo(default)   
WHERE value = N'C:\TraceResults.trc';  
  
-- First stop the trace.   
EXEC sp_trace_setstatus @TraceID, 0;  
  
-- Close and then delete its definition from SQL Server.   
EXEC sp_trace_setstatus @TraceID, 2;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd7a1-293">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd7a1-293">See Also</span></span>  
 <span data-ttu-id="bd7a1-294">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bd7a1-294">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="bd7a1-295">sys.dm_tran_locks &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bd7a1-295">sys.dm_tran_locks &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-dynamic-management-views/sys-dm-tran-locks-transact-sql)  
  
  