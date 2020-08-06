---
title: Clase de eventos Broker:Connection | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Broker:Connection event class
ms.assetid: d3e505f2-0a43-486f-aa92-9c8e49b2dfea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 52c0755d7547d85cfa041080518429d20165f251
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672009"
---
# <a name="brokerconnection-event-class"></a><span data-ttu-id="93ed3-102">Broker:Connection, clase de eventos</span><span class="sxs-lookup"><span data-stu-id="93ed3-102">Broker:Connection Event Class</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-103">genera un evento **Broker:Connection** para informar del estado de una conexión de transporte administrada por Service Broker.</span><span class="sxs-lookup"><span data-stu-id="93ed3-103">generates a **Broker:Connection** event to report the status of a transport connection managed by Service Broker.</span></span>  
  
## <a name="brokerconnection-event-class-data-columns"></a><span data-ttu-id="93ed3-104">Columnas de datos de la clase de evento Broker:Connection</span><span class="sxs-lookup"><span data-stu-id="93ed3-104">Broker:Connection Event Class Data Columns</span></span>  
  
|<span data-ttu-id="93ed3-105">Columna de datos</span><span class="sxs-lookup"><span data-stu-id="93ed3-105">Data column</span></span>|<span data-ttu-id="93ed3-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="93ed3-106">Type</span></span>|<span data-ttu-id="93ed3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="93ed3-107">Description</span></span>|<span data-ttu-id="93ed3-108">Número de columna</span><span class="sxs-lookup"><span data-stu-id="93ed3-108">Column number</span></span>|<span data-ttu-id="93ed3-109">Filtrable</span><span class="sxs-lookup"><span data-stu-id="93ed3-109">Filterable</span></span>|  
|-----------------|----------|-----------------|-------------------|----------------|  
|<span data-ttu-id="93ed3-110">**ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="93ed3-110">**ApplicationName**</span></span>|`nvarchar`|<span data-ttu-id="93ed3-111">Nombre de la aplicación cliente que ha creado la conexión a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93ed3-111">The name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="93ed3-112">Esta columna se rellena con los valores que pasa la aplicación, en lugar de con el nombre que se muestra para el programa.</span><span class="sxs-lookup"><span data-stu-id="93ed3-112">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="93ed3-113">10</span><span class="sxs-lookup"><span data-stu-id="93ed3-113">10</span></span>|<span data-ttu-id="93ed3-114">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-114">Yes</span></span>|  
|<span data-ttu-id="93ed3-115">**ClientProcessID**</span><span class="sxs-lookup"><span data-stu-id="93ed3-115">**ClientProcessID**</span></span>|`int`|<span data-ttu-id="93ed3-116">Id. que el equipo host asigna al proceso en el que se ejecuta la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="93ed3-116">The ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="93ed3-117">Esta columna de datos se rellena si el cliente proporciona su identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="93ed3-117">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="93ed3-118">9</span><span class="sxs-lookup"><span data-stu-id="93ed3-118">9</span></span>|<span data-ttu-id="93ed3-119">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-119">Yes</span></span>|  
|<span data-ttu-id="93ed3-120">**DatabaseID**</span><span class="sxs-lookup"><span data-stu-id="93ed3-120">**DatabaseID**</span></span>|`int`|<span data-ttu-id="93ed3-121">Identificador de la base de datos especificada mediante la instrucción USE *database* o identificador de la base de datos predeterminada si no se ha emitido la instrucción USE *database*para una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="93ed3-121">The ID of the database specified by the USE *database* statement, or the ID of the default database if no USE *database*statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="93ed3-122">muestra el nombre de la base de datos si se captura la columna de datos **ServerName** en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="93ed3-122">displays the name of the database if the **ServerName** data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="93ed3-123">Determine el valor de una base de datos mediante la función **DB_ID** .</span><span class="sxs-lookup"><span data-stu-id="93ed3-123">Determine the value for a database by using the **DB_ID** function.</span></span>|<span data-ttu-id="93ed3-124">3</span><span class="sxs-lookup"><span data-stu-id="93ed3-124">3</span></span>|<span data-ttu-id="93ed3-125">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-125">Yes</span></span>|  
|<span data-ttu-id="93ed3-126">**Error**</span><span class="sxs-lookup"><span data-stu-id="93ed3-126">**Error**</span></span>|`int`|<span data-ttu-id="93ed3-127">El número de identificación del mensaje en **Sys.** messages para el texto del evento.</span><span class="sxs-lookup"><span data-stu-id="93ed3-127">The message ID number in **sys.messages** for the text in the event.</span></span> <span data-ttu-id="93ed3-128">Si este evento informa de un error, éste es el número de error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93ed3-128">If this event reports an error, this is the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number.</span></span>|<span data-ttu-id="93ed3-129">31</span><span class="sxs-lookup"><span data-stu-id="93ed3-129">31</span></span>|<span data-ttu-id="93ed3-130">No</span><span class="sxs-lookup"><span data-stu-id="93ed3-130">No</span></span>|  
|<span data-ttu-id="93ed3-131">**EventClass**</span><span class="sxs-lookup"><span data-stu-id="93ed3-131">**EventClass**</span></span>|`int`|<span data-ttu-id="93ed3-132">Tipo de clase de eventos capturado.</span><span class="sxs-lookup"><span data-stu-id="93ed3-132">The type of event class captured.</span></span> <span data-ttu-id="93ed3-133">Siempre **138** para **Broker:Connection**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-133">Always **138** for **Broker:Connection**.</span></span>|<span data-ttu-id="93ed3-134">27</span><span class="sxs-lookup"><span data-stu-id="93ed3-134">27</span></span>|<span data-ttu-id="93ed3-135">No</span><span class="sxs-lookup"><span data-stu-id="93ed3-135">No</span></span>|  
|<span data-ttu-id="93ed3-136">**EventSequence**</span><span class="sxs-lookup"><span data-stu-id="93ed3-136">**EventSequence**</span></span>|`int`|<span data-ttu-id="93ed3-137">Número de secuencia de este evento.</span><span class="sxs-lookup"><span data-stu-id="93ed3-137">Sequence number for this event.</span></span>|<span data-ttu-id="93ed3-138">51</span><span class="sxs-lookup"><span data-stu-id="93ed3-138">51</span></span>|<span data-ttu-id="93ed3-139">No</span><span class="sxs-lookup"><span data-stu-id="93ed3-139">No</span></span>|  
|<span data-ttu-id="93ed3-140">**EventSubClass**</span><span class="sxs-lookup"><span data-stu-id="93ed3-140">**EventSubClass**</span></span>|`nvarchar`|<span data-ttu-id="93ed3-141">Estado de esta conexión.</span><span class="sxs-lookup"><span data-stu-id="93ed3-141">The connection state of this connection.</span></span> <span data-ttu-id="93ed3-142">En el caso de este evento, la subclase es uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="93ed3-142">For this event, the subclass is one the following values:</span></span><br /><br /> <span data-ttu-id="93ed3-143">**Conectando**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-143">**Connecting**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-144">está iniciando una conexión de transporte.</span><span class="sxs-lookup"><span data-stu-id="93ed3-144">is initiating a transport connection.</span></span><br /><br /> <span data-ttu-id="93ed3-145">**Conectado**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-145">**Connected**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-146">ha establecido una conexión de transporte.</span><span class="sxs-lookup"><span data-stu-id="93ed3-146">has established a transport connection.</span></span><br /><br /> <span data-ttu-id="93ed3-147">**Connect Failed**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-147">**Connect Failed**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-148">no ha podido establecer una conexión de transporte.</span><span class="sxs-lookup"><span data-stu-id="93ed3-148">failed to establish a transport connection.</span></span><br /><br /> <span data-ttu-id="93ed3-149">**Cierre**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-149">**Closing**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-150">está cerrando la conexión de transporte.</span><span class="sxs-lookup"><span data-stu-id="93ed3-150">is closing the transport connection.</span></span><br /><br /> <span data-ttu-id="93ed3-151">**Cerrada**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-151">**Closed**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-152">ha cerrado la conexión de transporte.</span><span class="sxs-lookup"><span data-stu-id="93ed3-152">has closed the transport connection.</span></span><br /><br /> <span data-ttu-id="93ed3-153">**Acepte**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-153">**Accept**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-154">ha aceptado una conexión de transporte de otra instancia.</span><span class="sxs-lookup"><span data-stu-id="93ed3-154">has accepted a transport connection from another instance.</span></span><br /><br /> <span data-ttu-id="93ed3-155">**Send IO Error**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-155">**Send IO Error**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-156">detectó un error de transporte al enviar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="93ed3-156">encountered a transport error while sending a message.</span></span><br /><br /> <span data-ttu-id="93ed3-157">**Receive IO Error**.</span><span class="sxs-lookup"><span data-stu-id="93ed3-157">**Receive IO Error**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93ed3-158">detectó un error de transporte al recibir un mensaje.</span><span class="sxs-lookup"><span data-stu-id="93ed3-158">encountered a transport error while receiving a message.</span></span>|<span data-ttu-id="93ed3-159">21</span><span class="sxs-lookup"><span data-stu-id="93ed3-159">21</span></span>|<span data-ttu-id="93ed3-160">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-160">Yes</span></span>|  
|<span data-ttu-id="93ed3-161">**GUID**</span><span class="sxs-lookup"><span data-stu-id="93ed3-161">**GUID**</span></span>|`uniqueidentifier`|<span data-ttu-id="93ed3-162">Id. de extremo de esta conexión.</span><span class="sxs-lookup"><span data-stu-id="93ed3-162">The endpoint ID of this connection.</span></span>|<span data-ttu-id="93ed3-163">54</span><span class="sxs-lookup"><span data-stu-id="93ed3-163">54</span></span>|<span data-ttu-id="93ed3-164">No</span><span class="sxs-lookup"><span data-stu-id="93ed3-164">No</span></span>|  
|<span data-ttu-id="93ed3-165">**HostName**</span><span class="sxs-lookup"><span data-stu-id="93ed3-165">**HostName**</span></span>|`nvarchar`|<span data-ttu-id="93ed3-166">Nombre del equipo en el que se está ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="93ed3-166">The name of the computer on which the client is running.</span></span> <span data-ttu-id="93ed3-167">Esta columna de datos se rellena si el cliente proporciona el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="93ed3-167">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="93ed3-168">Para determinar el nombre de host, utilice la función **host_name** .</span><span class="sxs-lookup"><span data-stu-id="93ed3-168">To determine the host name, use the **HOST_NAME** function.</span></span>|<span data-ttu-id="93ed3-169">8</span><span class="sxs-lookup"><span data-stu-id="93ed3-169">8</span></span>|<span data-ttu-id="93ed3-170">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-170">Yes</span></span>|  
|<span data-ttu-id="93ed3-171">**IntegerData**</span><span class="sxs-lookup"><span data-stu-id="93ed3-171">**IntegerData**</span></span>|`int`|<span data-ttu-id="93ed3-172">Número de veces que se ha cerrado esta conexión.</span><span class="sxs-lookup"><span data-stu-id="93ed3-172">The number of times this connection has been closed.</span></span>|<span data-ttu-id="93ed3-173">25</span><span class="sxs-lookup"><span data-stu-id="93ed3-173">25</span></span>|<span data-ttu-id="93ed3-174">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-174">Yes</span></span>|  
|<span data-ttu-id="93ed3-175">**IsSystem**</span><span class="sxs-lookup"><span data-stu-id="93ed3-175">**IsSystem**</span></span>|`int`|<span data-ttu-id="93ed3-176">Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario.</span><span class="sxs-lookup"><span data-stu-id="93ed3-176">Indicates whether the event occurred on a system process or a user process.</span></span><br /><br /> <span data-ttu-id="93ed3-177">0 = usuario</span><span class="sxs-lookup"><span data-stu-id="93ed3-177">0 = user</span></span><br /><br /> <span data-ttu-id="93ed3-178">1 = sistema</span><span class="sxs-lookup"><span data-stu-id="93ed3-178">1 = system</span></span>|<span data-ttu-id="93ed3-179">60</span><span class="sxs-lookup"><span data-stu-id="93ed3-179">60</span></span>|<span data-ttu-id="93ed3-180">No</span><span class="sxs-lookup"><span data-stu-id="93ed3-180">No</span></span>|  
|<span data-ttu-id="93ed3-181">**LoginSid**</span><span class="sxs-lookup"><span data-stu-id="93ed3-181">**LoginSid**</span></span>|`image`|<span data-ttu-id="93ed3-182">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="93ed3-182">The security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="93ed3-183">Cada SID es único para cada inicio de sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="93ed3-183">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="93ed3-184">41</span><span class="sxs-lookup"><span data-stu-id="93ed3-184">41</span></span>|<span data-ttu-id="93ed3-185">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-185">Yes</span></span>|  
|<span data-ttu-id="93ed3-186">**NTDomainName**</span><span class="sxs-lookup"><span data-stu-id="93ed3-186">**NTDomainName**</span></span>|`nvarchar`|<span data-ttu-id="93ed3-187">Dominio de Windows al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="93ed3-187">The Windows domain to which the user belongs.</span></span>|<span data-ttu-id="93ed3-188">7</span><span class="sxs-lookup"><span data-stu-id="93ed3-188">7</span></span>|<span data-ttu-id="93ed3-189">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-189">Yes</span></span>|  
|<span data-ttu-id="93ed3-190">**NTUserName**</span><span class="sxs-lookup"><span data-stu-id="93ed3-190">**NTUserName**</span></span>|`nvarchar`|<span data-ttu-id="93ed3-191">Nombre del usuario al que pertenece la conexión que generó este evento.</span><span class="sxs-lookup"><span data-stu-id="93ed3-191">The name of the user that owns the connection that generated this event.</span></span>|<span data-ttu-id="93ed3-192">6</span><span class="sxs-lookup"><span data-stu-id="93ed3-192">6</span></span>|<span data-ttu-id="93ed3-193">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-193">Yes</span></span>|  
|<span data-ttu-id="93ed3-194">**ObjectName**</span><span class="sxs-lookup"><span data-stu-id="93ed3-194">**ObjectName**</span></span>|`nvarchar`|<span data-ttu-id="93ed3-195">Identificador de conversación del diálogo.</span><span class="sxs-lookup"><span data-stu-id="93ed3-195">The conversation handle of the dialog.</span></span>|<span data-ttu-id="93ed3-196">34</span><span class="sxs-lookup"><span data-stu-id="93ed3-196">34</span></span>|<span data-ttu-id="93ed3-197">No</span><span class="sxs-lookup"><span data-stu-id="93ed3-197">No</span></span>|  
|<span data-ttu-id="93ed3-198">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="93ed3-198">**ServerName**</span></span>|`nvarchar`|<span data-ttu-id="93ed3-199">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="93ed3-199">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="93ed3-200">26</span><span class="sxs-lookup"><span data-stu-id="93ed3-200">26</span></span>|<span data-ttu-id="93ed3-201">No</span><span class="sxs-lookup"><span data-stu-id="93ed3-201">No</span></span>|  
|<span data-ttu-id="93ed3-202">**SPID**</span><span class="sxs-lookup"><span data-stu-id="93ed3-202">**SPID**</span></span>|`int`|<span data-ttu-id="93ed3-203">Identificador de proceso del servidor que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asigna al proceso asociado al cliente.</span><span class="sxs-lookup"><span data-stu-id="93ed3-203">The server process ID assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to the process associated with the client.</span></span>|<span data-ttu-id="93ed3-204">12</span><span class="sxs-lookup"><span data-stu-id="93ed3-204">12</span></span>|<span data-ttu-id="93ed3-205">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-205">Yes</span></span>|  
|<span data-ttu-id="93ed3-206">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="93ed3-206">**StartTime**</span></span>|`datetime`|<span data-ttu-id="93ed3-207">Hora a la que se inició el evento, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="93ed3-207">The time at which the event started, when available.</span></span>|<span data-ttu-id="93ed3-208">14</span><span class="sxs-lookup"><span data-stu-id="93ed3-208">14</span></span>|<span data-ttu-id="93ed3-209">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-209">Yes</span></span>|  
|<span data-ttu-id="93ed3-210">**TextData**</span><span class="sxs-lookup"><span data-stu-id="93ed3-210">**TextData**</span></span>|`ntext`|<span data-ttu-id="93ed3-211">Texto del mensaje de error relacionado con el evento.</span><span class="sxs-lookup"><span data-stu-id="93ed3-211">The text of the error message related to the event.</span></span> <span data-ttu-id="93ed3-212">En el caso de los eventos que no informan de un error, este campo está vacío.</span><span class="sxs-lookup"><span data-stu-id="93ed3-212">For events that do not report an error, this field is empty.</span></span> <span data-ttu-id="93ed3-213">El mensaje de error puede ser de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o de Windows.</span><span class="sxs-lookup"><span data-stu-id="93ed3-213">The error message may either be a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message or a Windows error message.</span></span>|<span data-ttu-id="93ed3-214">1</span><span class="sxs-lookup"><span data-stu-id="93ed3-214">1</span></span>|<span data-ttu-id="93ed3-215">Sí</span><span class="sxs-lookup"><span data-stu-id="93ed3-215">Yes</span></span>|  
|<span data-ttu-id="93ed3-216">**TransactionID**</span><span class="sxs-lookup"><span data-stu-id="93ed3-216">**TransactionID**</span></span>|`bigint`|<span data-ttu-id="93ed3-217">Identificador de la transacción asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="93ed3-217">The system-assigned ID of the transaction.</span></span>|<span data-ttu-id="93ed3-218">4</span><span class="sxs-lookup"><span data-stu-id="93ed3-218">4</span></span>|<span data-ttu-id="93ed3-219">No</span><span class="sxs-lookup"><span data-stu-id="93ed3-219">No</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93ed3-220">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93ed3-220">See Also</span></span>  
 [<span data-ttu-id="93ed3-221">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="93ed3-221">SQL Server Service Broker</span></span>](../../database-engine/configure-windows/sql-server-service-broker.md)  
  
  