---
title: Clase de evento Blocked Process Report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Blocked Process Report event class
ms.assetid: e8acb408-938d-4b36-81dd-04f087410cc5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bd2d0b9c81e99e1e0d1c39fb773b1e6c286ecdd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671075"
---
# <a name="blocked-process-report-event-class"></a><span data-ttu-id="62b0d-102">Blocked Process Report, clase de eventos</span><span class="sxs-lookup"><span data-stu-id="62b0d-102">Blocked Process Report Event Class</span></span>
  <span data-ttu-id="62b0d-103">La clase de evento **Blocked Process Report** indica que una tarea ha estado bloqueada durante más de un período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="62b0d-103">The **Blocked Process Report** event class indicates that a task has been blocked for more than a specified amount of time.</span></span> <span data-ttu-id="62b0d-104">Esta clase de evento no incluye tareas del sistema ni tareas que estén esperando recursos no detectables por interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="62b0d-104">This event class does not include system tasks or tasks that are waiting on non deadlock-detectable resources.</span></span>  
  
 <span data-ttu-id="62b0d-105">Para configurar el umbral y la frecuencia con la que se genera el informe, use el comando **sp_configure** para configurar la opción **blocked process threshold** , que puede establecerse en segundos.</span><span class="sxs-lookup"><span data-stu-id="62b0d-105">To configure the threshold and frequency at which reports are generated, use the **sp_configure** command to configure the **blocked process threshold** option, which can be set in seconds.</span></span> <span data-ttu-id="62b0d-106">De manera predeterminada, se producen informes de procesos no bloqueados.</span><span class="sxs-lookup"><span data-stu-id="62b0d-106">By default, no blocked process reports are produced.</span></span> <span data-ttu-id="62b0d-107">Para obtener más información sobre cómo configurar la opción **blocked process threshold** , vea [blocked process threshold (opción de configuración del servidor)](../../database-engine/configure-windows/blocked-process-threshold-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="62b0d-107">For more information about setting the **blocked process threshold** option, see [blocked process threshold Server Configuration Option](../../database-engine/configure-windows/blocked-process-threshold-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="62b0d-108">Para obtener más información sobre cómo filtrar los datos devueltos por la clase de eventos **Blocked Process Report**, vea [Filtrar eventos en un seguimiento &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md), [Establecer un filtro de seguimiento &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md) o [sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="62b0d-108">For information about filtering the data returned by the **Blocked Process Report** event class, see [Filter Events in a Trace &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/filter-events-in-a-trace-sql-server-profiler.md), [Set a Trace Filter &#40;Transact-SQL&#41;](../../ssms/agent/set-sql-server-alias-for-sql-server-agent-service-ssms.md), or [sp_trace_setfilter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setfilter-transact-sql).</span></span>  
  
## <a name="blocked-process-report-event-class-data-columns"></a><span data-ttu-id="62b0d-109">Columnas de datos de la clase de evento Blocked Process Report</span><span class="sxs-lookup"><span data-stu-id="62b0d-109">Blocked Process Report Event Class Data Columns</span></span>  
  
|<span data-ttu-id="62b0d-110">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="62b0d-110">Data column name</span></span>|<span data-ttu-id="62b0d-111">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="62b0d-111">Data type</span></span>|<span data-ttu-id="62b0d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="62b0d-112">Description</span></span>|<span data-ttu-id="62b0d-113">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="62b0d-113">Column ID</span></span>|<span data-ttu-id="62b0d-114">Filtrable</span><span class="sxs-lookup"><span data-stu-id="62b0d-114">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="62b0d-115">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="62b0d-115">**DatabaseID**</span></span>|<span data-ttu-id="62b0d-116">**int**</span><span class="sxs-lookup"><span data-stu-id="62b0d-116">**int**</span></span>|<span data-ttu-id="62b0d-117">Identificador de la base de datos en la que se ha adquirido el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="62b0d-117">ID of the database in which the lock was acquired.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="62b0d-118">muestra el nombre de la base de datos si se captura la columna de datos **ServerName** en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="62b0d-118">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="62b0d-119">Determina el valor de una base de datos mediante la función DB_ID.</span><span class="sxs-lookup"><span data-stu-id="62b0d-119">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="62b0d-120">3</span><span class="sxs-lookup"><span data-stu-id="62b0d-120">3</span></span>|<span data-ttu-id="62b0d-121">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-121">Yes</span></span>|  
|<span data-ttu-id="62b0d-122">**Duration**</span><span class="sxs-lookup"><span data-stu-id="62b0d-122">**Duration**</span></span>|<span data-ttu-id="62b0d-123">**bigint**</span><span class="sxs-lookup"><span data-stu-id="62b0d-123">**bigint**</span></span>|<span data-ttu-id="62b0d-124">Período de tiempo (en milisegundos) que el proceso estuvo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="62b0d-124">The amount of time (in milliseconds) that the process was blocked.</span></span>|<span data-ttu-id="62b0d-125">13</span><span class="sxs-lookup"><span data-stu-id="62b0d-125">13</span></span>|<span data-ttu-id="62b0d-126">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-126">Yes</span></span>|  
|<span data-ttu-id="62b0d-127">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="62b0d-127">**EndTime**</span></span>|<span data-ttu-id="62b0d-128">**datetime**</span><span class="sxs-lookup"><span data-stu-id="62b0d-128">**datetime**</span></span>|<span data-ttu-id="62b0d-129">Hora a la que finalizó el evento.</span><span class="sxs-lookup"><span data-stu-id="62b0d-129">Time at which the event ended.</span></span> <span data-ttu-id="62b0d-130">Esta columna no se llena para las clases de eventos de inicio, como **SQL:BatchStarting** o **SP:Starting**.</span><span class="sxs-lookup"><span data-stu-id="62b0d-130">This column is not populated for starting event classes, such as **SQL:BatchStarting** or **SP:Starting**.</span></span>|<span data-ttu-id="62b0d-131">15</span><span class="sxs-lookup"><span data-stu-id="62b0d-131">15</span></span>|<span data-ttu-id="62b0d-132">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-132">Yes</span></span>|  
|<span data-ttu-id="62b0d-133">**EventClass**</span><span class="sxs-lookup"><span data-stu-id="62b0d-133">**EventClass**</span></span>|<span data-ttu-id="62b0d-134">**int**</span><span class="sxs-lookup"><span data-stu-id="62b0d-134">**int**</span></span>|<span data-ttu-id="62b0d-135">Tipo de evento = 137.</span><span class="sxs-lookup"><span data-stu-id="62b0d-135">Type of event = 137.</span></span>|<span data-ttu-id="62b0d-136">27</span><span class="sxs-lookup"><span data-stu-id="62b0d-136">27</span></span>|<span data-ttu-id="62b0d-137">No</span><span class="sxs-lookup"><span data-stu-id="62b0d-137">No</span></span>|  
|<span data-ttu-id="62b0d-138">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="62b0d-138">**EventSequence**</span></span>|<span data-ttu-id="62b0d-139">**int**</span><span class="sxs-lookup"><span data-stu-id="62b0d-139">**int**</span></span>|<span data-ttu-id="62b0d-140">Secuencia de un evento determinado dentro de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="62b0d-140">The sequence of a given event within the request.</span></span>|<span data-ttu-id="62b0d-141">51</span><span class="sxs-lookup"><span data-stu-id="62b0d-141">51</span></span>|<span data-ttu-id="62b0d-142">No</span><span class="sxs-lookup"><span data-stu-id="62b0d-142">No</span></span>|  
|<span data-ttu-id="62b0d-143">**IndexID**</span><span class="sxs-lookup"><span data-stu-id="62b0d-143">**IndexID**</span></span>|<span data-ttu-id="62b0d-144">**int**</span><span class="sxs-lookup"><span data-stu-id="62b0d-144">**int**</span></span>|<span data-ttu-id="62b0d-145">Id. del índice del objeto afectado por el evento.</span><span class="sxs-lookup"><span data-stu-id="62b0d-145">ID for the index on the object affected by the event.</span></span> <span data-ttu-id="62b0d-146">Para determinar el Id. de índice de un objeto, utilice la columna **indid** de la tabla del sistema **sysindexes** .</span><span class="sxs-lookup"><span data-stu-id="62b0d-146">To determine the index ID for an object, use the **indid** column of the **sysindexes** system table.</span></span>|<span data-ttu-id="62b0d-147">24</span><span class="sxs-lookup"><span data-stu-id="62b0d-147">24</span></span>|<span data-ttu-id="62b0d-148">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-148">Yes</span></span>|  
|<span data-ttu-id="62b0d-149">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="62b0d-149">**IsSystem**</span></span>|<span data-ttu-id="62b0d-150">**int**</span><span class="sxs-lookup"><span data-stu-id="62b0d-150">**int**</span></span>|<span data-ttu-id="62b0d-151">Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="62b0d-151">Indicates whether the event occurred on a system process or a user process.</span></span> <span data-ttu-id="62b0d-152">1 = sistema, 0 = usuario.</span><span class="sxs-lookup"><span data-stu-id="62b0d-152">1 = system, 0 = user.</span></span>|<span data-ttu-id="62b0d-153">60</span><span class="sxs-lookup"><span data-stu-id="62b0d-153">60</span></span>|<span data-ttu-id="62b0d-154">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-154">Yes</span></span>|  
|<span data-ttu-id="62b0d-155">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="62b0d-155">**LoginSid**</span></span>|<span data-ttu-id="62b0d-156">**image**</span><span class="sxs-lookup"><span data-stu-id="62b0d-156">**image**</span></span>|<span data-ttu-id="62b0d-157">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="62b0d-157">Security identifier (SID) of the logged-in user.</span></span> <span data-ttu-id="62b0d-158">Este evento se notifica siempre desde el subproceso del sistema.</span><span class="sxs-lookup"><span data-stu-id="62b0d-158">This event is always reported from the system thread.</span></span> <span data-ttu-id="62b0d-159">IsSystem = 1; SID = sa.</span><span class="sxs-lookup"><span data-stu-id="62b0d-159">IsSystem = 1; SID = sa.</span></span>|<span data-ttu-id="62b0d-160">41</span><span class="sxs-lookup"><span data-stu-id="62b0d-160">41</span></span>|<span data-ttu-id="62b0d-161">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-161">Yes</span></span>|  
|<span data-ttu-id="62b0d-162">**Modo**</span><span class="sxs-lookup"><span data-stu-id="62b0d-162">**Mode**</span></span>|<span data-ttu-id="62b0d-163">**int**</span><span class="sxs-lookup"><span data-stu-id="62b0d-163">**int**</span></span>|<span data-ttu-id="62b0d-164">Estado que el evento ha recibido o ha solicitado.</span><span class="sxs-lookup"><span data-stu-id="62b0d-164">The state the event has received or is requesting.</span></span><br /><br /> <span data-ttu-id="62b0d-165">0=NULL</span><span class="sxs-lookup"><span data-stu-id="62b0d-165">0=NULL</span></span><br /><br /> <span data-ttu-id="62b0d-166">1=Sch-S</span><span class="sxs-lookup"><span data-stu-id="62b0d-166">1=Sch-S</span></span><br /><br /> <span data-ttu-id="62b0d-167">2=Sch-M</span><span class="sxs-lookup"><span data-stu-id="62b0d-167">2=Sch-M</span></span><br /><br /> <span data-ttu-id="62b0d-168">3=S</span><span class="sxs-lookup"><span data-stu-id="62b0d-168">3=S</span></span><br /><br /> <span data-ttu-id="62b0d-169">4=U</span><span class="sxs-lookup"><span data-stu-id="62b0d-169">4=U</span></span><br /><br /> <span data-ttu-id="62b0d-170">5=X</span><span class="sxs-lookup"><span data-stu-id="62b0d-170">5=X</span></span><br /><br /> <span data-ttu-id="62b0d-171">6=IS</span><span class="sxs-lookup"><span data-stu-id="62b0d-171">6=IS</span></span><br /><br /> <span data-ttu-id="62b0d-172">7=IU</span><span class="sxs-lookup"><span data-stu-id="62b0d-172">7=IU</span></span><br /><br /> <span data-ttu-id="62b0d-173">8=IX</span><span class="sxs-lookup"><span data-stu-id="62b0d-173">8=IX</span></span><br /><br /> <span data-ttu-id="62b0d-174">9=SIU</span><span class="sxs-lookup"><span data-stu-id="62b0d-174">9=SIU</span></span><br /><br /> <span data-ttu-id="62b0d-175">10=SIX</span><span class="sxs-lookup"><span data-stu-id="62b0d-175">10=SIX</span></span><br /><br /> <span data-ttu-id="62b0d-176">11=UIX</span><span class="sxs-lookup"><span data-stu-id="62b0d-176">11=UIX</span></span><br /><br /> <span data-ttu-id="62b0d-177">12=BU</span><span class="sxs-lookup"><span data-stu-id="62b0d-177">12=BU</span></span><br /><br /> <span data-ttu-id="62b0d-178">13=RangeS-S</span><span class="sxs-lookup"><span data-stu-id="62b0d-178">13=RangeS-S</span></span><br /><br /> <span data-ttu-id="62b0d-179">14=RangeS-U</span><span class="sxs-lookup"><span data-stu-id="62b0d-179">14=RangeS-U</span></span><br /><br /> <span data-ttu-id="62b0d-180">15=RangeI-N</span><span class="sxs-lookup"><span data-stu-id="62b0d-180">15=RangeI-N</span></span><br /><br /> <span data-ttu-id="62b0d-181">16=RangeI-S</span><span class="sxs-lookup"><span data-stu-id="62b0d-181">16=RangeI-S</span></span><br /><br /> <span data-ttu-id="62b0d-182">17=RangeI-U</span><span class="sxs-lookup"><span data-stu-id="62b0d-182">17=RangeI-U</span></span><br /><br /> <span data-ttu-id="62b0d-183">18=RangeI-X</span><span class="sxs-lookup"><span data-stu-id="62b0d-183">18=RangeI-X</span></span><br /><br /> <span data-ttu-id="62b0d-184">19=RangeX-S</span><span class="sxs-lookup"><span data-stu-id="62b0d-184">19=RangeX-S</span></span><br /><br /> <span data-ttu-id="62b0d-185">20=RangeX-U</span><span class="sxs-lookup"><span data-stu-id="62b0d-185">20=RangeX-U</span></span><br /><br /> <span data-ttu-id="62b0d-186">21=RangeX-X</span><span class="sxs-lookup"><span data-stu-id="62b0d-186">21=RangeX-X</span></span>|<span data-ttu-id="62b0d-187">32</span><span class="sxs-lookup"><span data-stu-id="62b0d-187">32</span></span>|<span data-ttu-id="62b0d-188">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-188">Yes</span></span>|  
|<span data-ttu-id="62b0d-189">**ObjectID**</span><span class="sxs-lookup"><span data-stu-id="62b0d-189">**ObjectID**</span></span>|<span data-ttu-id="62b0d-190">**int**</span><span class="sxs-lookup"><span data-stu-id="62b0d-190">**int**</span></span>|<span data-ttu-id="62b0d-191">Id. asignado por el sistema del objeto en el que se ha adquirido el bloqueo, si está disponible y es aplicable.</span><span class="sxs-lookup"><span data-stu-id="62b0d-191">System-assigned ID of the object on which the lock was acquired, if available and applicable.</span></span>|<span data-ttu-id="62b0d-192">22</span><span class="sxs-lookup"><span data-stu-id="62b0d-192">22</span></span>|<span data-ttu-id="62b0d-193">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-193">Yes</span></span>|  
|<span data-ttu-id="62b0d-194">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="62b0d-194">**ServerName**</span></span>|<span data-ttu-id="62b0d-195">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="62b0d-195">**nvarchar**</span></span>|<span data-ttu-id="62b0d-196">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="62b0d-196">Name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="62b0d-197">26</span><span class="sxs-lookup"><span data-stu-id="62b0d-197">26</span></span>||  
|<span data-ttu-id="62b0d-198">**SessionLoginName**</span><span class="sxs-lookup"><span data-stu-id="62b0d-198">**SessionLoginName**</span></span>|<span data-ttu-id="62b0d-199">**nvarchar**</span><span class="sxs-lookup"><span data-stu-id="62b0d-199">**nvarchar**</span></span>|<span data-ttu-id="62b0d-200">Nombre de inicio de sesión del usuario que originó la sesión.</span><span class="sxs-lookup"><span data-stu-id="62b0d-200">The login name of the user that originated the session.</span></span> <span data-ttu-id="62b0d-201">Por ejemplo, si se conecta a SQL Server mediante inicioDeSesión1 y ejecuta una instrucción como inicioDeSesión2, **SessionLoginName** muestra inicioDeSesión1 y **LoginName** muestra inicioDeSesión2.</span><span class="sxs-lookup"><span data-stu-id="62b0d-201">For example, if you connect to SQL Server using Login1 and execute a statement as Login2, **SessionLoginName** shows Login1; and **LoginName** shows Login2.</span></span> <span data-ttu-id="62b0d-202">En esta columna se muestran los inicios de sesión de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] y de Windows.</span><span class="sxs-lookup"><span data-stu-id="62b0d-202">This column displays both [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and Windows logins.</span></span>|<span data-ttu-id="62b0d-203">64</span><span class="sxs-lookup"><span data-stu-id="62b0d-203">64</span></span>|<span data-ttu-id="62b0d-204">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-204">Yes</span></span>|  
|<span data-ttu-id="62b0d-205">**TextData**</span><span class="sxs-lookup"><span data-stu-id="62b0d-205">**TextData**</span></span>|<span data-ttu-id="62b0d-206">**ntext**</span><span class="sxs-lookup"><span data-stu-id="62b0d-206">**ntext**</span></span>|<span data-ttu-id="62b0d-207">Valor de texto que depende de la clase de eventos capturada en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="62b0d-207">Text value dependent on the event class captured in the trace.</span></span>|<span data-ttu-id="62b0d-208">1</span><span class="sxs-lookup"><span data-stu-id="62b0d-208">1</span></span>|<span data-ttu-id="62b0d-209">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-209">Yes</span></span>|  
|<span data-ttu-id="62b0d-210">**TransactionID**</span><span class="sxs-lookup"><span data-stu-id="62b0d-210">**TransactionID**</span></span>|<span data-ttu-id="62b0d-211">**bigint**</span><span class="sxs-lookup"><span data-stu-id="62b0d-211">**bigint**</span></span>|<span data-ttu-id="62b0d-212">Id. de la transacción asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="62b0d-212">System-assigned ID of the transaction.</span></span>|<span data-ttu-id="62b0d-213">4</span><span class="sxs-lookup"><span data-stu-id="62b0d-213">4</span></span>|<span data-ttu-id="62b0d-214">Sí</span><span class="sxs-lookup"><span data-stu-id="62b0d-214">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62b0d-215">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62b0d-215">See Also</span></span>  
 <span data-ttu-id="62b0d-216">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62b0d-216">[sp_trace_setevent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql) </span></span>  
 [<span data-ttu-id="62b0d-217">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="62b0d-217">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  