---
title: Clase de eventos Broker:Forwarded Message Dropped | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- Broker:Forwarded Message Dropped event class
ms.assetid: ec242d0b-77b0-45f5-8b12-186a14b173a8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 66d6914c902a882794d3fa598ecb5d0afd7484dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745754"
---
# <a name="brokerforwarded-message-dropped-event-class"></a><span data-ttu-id="c2932-102">Broker:Forwarded Message Dropped, clase de eventos</span><span class="sxs-lookup"><span data-stu-id="c2932-102">Broker:Forwarded Message Dropped Event Class</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c2932-103">genera un evento Broker:Forwarded Message Dropped cuando Service Broker quita un mensaje que estaba destinado a reenviarse.</span><span class="sxs-lookup"><span data-stu-id="c2932-103">generates a Broker:Forwarded Message Dropped event when Service Broker drops a message that was intended to be forwarded.</span></span>  
  
## <a name="brokerforwarded-message-dropped-event-class-data-columns"></a><span data-ttu-id="c2932-104">Columnas de datos de la clase de eventos Broker:Forwarded Message Dropped</span><span class="sxs-lookup"><span data-stu-id="c2932-104">Broker:Forwarded Message Dropped Event Class Data Columns</span></span>  
  
|<span data-ttu-id="c2932-105">Columna de datos</span><span class="sxs-lookup"><span data-stu-id="c2932-105">Data column</span></span>|<span data-ttu-id="c2932-106">Tipo</span><span class="sxs-lookup"><span data-stu-id="c2932-106">Type</span></span>|<span data-ttu-id="c2932-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2932-107">Description</span></span>|<span data-ttu-id="c2932-108">Número de columna</span><span class="sxs-lookup"><span data-stu-id="c2932-108">Column number</span></span>|<span data-ttu-id="c2932-109">Filtrable</span><span class="sxs-lookup"><span data-stu-id="c2932-109">Filterable</span></span>|  
|-----------------|----------|-----------------|-------------------|----------------|  
|<span data-ttu-id="c2932-110">ApplicationName</span><span class="sxs-lookup"><span data-stu-id="c2932-110">ApplicationName</span></span>|`nvarchar`|<span data-ttu-id="c2932-111">Nombre de la aplicación cliente que ha creado la conexión a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2932-111">The name of the client application that created the connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c2932-112">Esta columna se rellena con los valores que pasa la aplicación, en lugar de con el nombre que se muestra para el programa.</span><span class="sxs-lookup"><span data-stu-id="c2932-112">This column is populated with the values passed by the application rather than the displayed name of the program.</span></span>|<span data-ttu-id="c2932-113">10</span><span class="sxs-lookup"><span data-stu-id="c2932-113">10</span></span>|<span data-ttu-id="c2932-114">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-114">Yes</span></span>|  
|<span data-ttu-id="c2932-115">BigintData1</span><span class="sxs-lookup"><span data-stu-id="c2932-115">BigintData1</span></span>|`bigint`|<span data-ttu-id="c2932-116">Número de secuencia de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c2932-116">Message sequence number.</span></span>|<span data-ttu-id="c2932-117">52</span><span class="sxs-lookup"><span data-stu-id="c2932-117">52</span></span>|<span data-ttu-id="c2932-118">No</span><span class="sxs-lookup"><span data-stu-id="c2932-118">No</span></span>|  
|<span data-ttu-id="c2932-119">ClientProcessID</span><span class="sxs-lookup"><span data-stu-id="c2932-119">ClientProcessID</span></span>|`int`|<span data-ttu-id="c2932-120">Id. que el equipo host asigna al proceso en el que se ejecuta la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="c2932-120">The ID assigned by the host computer to the process where the client application is running.</span></span> <span data-ttu-id="c2932-121">Esta columna de datos se rellena si el cliente proporciona su identificador de proceso.</span><span class="sxs-lookup"><span data-stu-id="c2932-121">This data column is populated if the client process ID is provided by the client.</span></span>|<span data-ttu-id="c2932-122">9</span><span class="sxs-lookup"><span data-stu-id="c2932-122">9</span></span>|<span data-ttu-id="c2932-123">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-123">Yes</span></span>|  
|<span data-ttu-id="c2932-124">DatabaseID</span><span class="sxs-lookup"><span data-stu-id="c2932-124">DatabaseID</span></span>|`int`|<span data-ttu-id="c2932-125">Identificador de la base de datos especificada mediante la instrucción USE *database* o identificador de la base de datos predeterminada si no se ha emitido la instrucción USE *database*para una instancia determinada.</span><span class="sxs-lookup"><span data-stu-id="c2932-125">The ID of the database specified by the USE *database* statement, or the ID of the default database if no USE *database*statement has been issued for a given instance.</span></span> [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] <span data-ttu-id="c2932-126">muestra el nombre de la base de datos si se captura la columna de datos Server Name en el seguimiento y el servidor está disponible.</span><span class="sxs-lookup"><span data-stu-id="c2932-126">displays the name of the database if the Server Name data column is captured in the trace and the server is available.</span></span> <span data-ttu-id="c2932-127">Determina el valor de una base de datos mediante la función DB_ID.</span><span class="sxs-lookup"><span data-stu-id="c2932-127">Determine the value for a database by using the DB_ID function.</span></span>|<span data-ttu-id="c2932-128">3</span><span class="sxs-lookup"><span data-stu-id="c2932-128">3</span></span>|<span data-ttu-id="c2932-129">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-129">Yes</span></span>|  
|<span data-ttu-id="c2932-130">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="c2932-130">DatabaseName</span></span>|`nvarchar`|<span data-ttu-id="c2932-131">Nombre de la base de datos en que se ejecuta la instrucción del usuario.</span><span class="sxs-lookup"><span data-stu-id="c2932-131">The name of the database in which the user statement is running.</span></span>|<span data-ttu-id="c2932-132">35</span><span class="sxs-lookup"><span data-stu-id="c2932-132">35</span></span>|<span data-ttu-id="c2932-133">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-133">Yes</span></span>|  
|<span data-ttu-id="c2932-134">DBUserName</span><span class="sxs-lookup"><span data-stu-id="c2932-134">DBUserName</span></span>|`nvarchar`|<span data-ttu-id="c2932-135">Identificador de la instancia del agente de donde procede este mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2932-135">The broker instance identifier that this message is from.</span></span>|<span data-ttu-id="c2932-136">40</span><span class="sxs-lookup"><span data-stu-id="c2932-136">40</span></span>|<span data-ttu-id="c2932-137">No</span><span class="sxs-lookup"><span data-stu-id="c2932-137">No</span></span>|  
|<span data-ttu-id="c2932-138">Error</span><span class="sxs-lookup"><span data-stu-id="c2932-138">Error</span></span>|`int`|<span data-ttu-id="c2932-139">Número de identificación del mensaje en sys.messages para el texto del evento.</span><span class="sxs-lookup"><span data-stu-id="c2932-139">The message id number in sys.messages for the text in the event.</span></span>|<span data-ttu-id="c2932-140">31</span><span class="sxs-lookup"><span data-stu-id="c2932-140">31</span></span>|<span data-ttu-id="c2932-141">No</span><span class="sxs-lookup"><span data-stu-id="c2932-141">No</span></span>|  
|<span data-ttu-id="c2932-142">EventClass</span><span class="sxs-lookup"><span data-stu-id="c2932-142">EventClass</span></span>|`int`|<span data-ttu-id="c2932-143">Tipo de clase de eventos capturado.</span><span class="sxs-lookup"><span data-stu-id="c2932-143">The type of event class captured.</span></span> <span data-ttu-id="c2932-144">Es siempre 191 para Broker:Forwarded Message Dropped.</span><span class="sxs-lookup"><span data-stu-id="c2932-144">Always 191 for Broker:Forwarded Message Dropped.</span></span>|<span data-ttu-id="c2932-145">27</span><span class="sxs-lookup"><span data-stu-id="c2932-145">27</span></span>|<span data-ttu-id="c2932-146">No</span><span class="sxs-lookup"><span data-stu-id="c2932-146">No</span></span>|  
|<span data-ttu-id="c2932-147">EventSequence</span><span class="sxs-lookup"><span data-stu-id="c2932-147">EventSequence</span></span>|`int`|<span data-ttu-id="c2932-148">Número de secuencia de este evento.</span><span class="sxs-lookup"><span data-stu-id="c2932-148">Sequence number for this event.</span></span>|<span data-ttu-id="c2932-149">51</span><span class="sxs-lookup"><span data-stu-id="c2932-149">51</span></span>|<span data-ttu-id="c2932-150">No</span><span class="sxs-lookup"><span data-stu-id="c2932-150">No</span></span>|  
|<span data-ttu-id="c2932-151">FileName</span><span class="sxs-lookup"><span data-stu-id="c2932-151">FileName</span></span>|`nvarchar`|<span data-ttu-id="c2932-152">Nombre del servicio al que se destina el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2932-152">The name of the service that the message is to.</span></span>|<span data-ttu-id="c2932-153">36</span><span class="sxs-lookup"><span data-stu-id="c2932-153">36</span></span>|<span data-ttu-id="c2932-154">No</span><span class="sxs-lookup"><span data-stu-id="c2932-154">No</span></span>|  
|<span data-ttu-id="c2932-155">GUID</span><span class="sxs-lookup"><span data-stu-id="c2932-155">GUID</span></span>|`uniqueidentifier`|<span data-ttu-id="c2932-156">Id. de conversación del diálogo.</span><span class="sxs-lookup"><span data-stu-id="c2932-156">The conversation id of the dialog.</span></span> <span data-ttu-id="c2932-157">Este identificador se transmite como parte del mensaje y lo comparten ambas partes de la conversación.</span><span class="sxs-lookup"><span data-stu-id="c2932-157">This identifier is transmitted as part of the message, and is shared between both sides of the conversation.</span></span>|<span data-ttu-id="c2932-158">54</span><span class="sxs-lookup"><span data-stu-id="c2932-158">54</span></span>|<span data-ttu-id="c2932-159">No</span><span class="sxs-lookup"><span data-stu-id="c2932-159">No</span></span>|  
|<span data-ttu-id="c2932-160">HostName</span><span class="sxs-lookup"><span data-stu-id="c2932-160">HostName</span></span>|`nvarchar`|<span data-ttu-id="c2932-161">Nombre del equipo en el que se está ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="c2932-161">The name of the computer on which the client is running.</span></span> <span data-ttu-id="c2932-162">Esta columna de datos se rellena si el cliente proporciona el nombre del host.</span><span class="sxs-lookup"><span data-stu-id="c2932-162">This data column is populated if the host name is provided by the client.</span></span> <span data-ttu-id="c2932-163">Para determinar el nombre del host, utilice la función HOST_NAME.</span><span class="sxs-lookup"><span data-stu-id="c2932-163">To determine the host name, use the HOST_NAME function.</span></span>|<span data-ttu-id="c2932-164">8</span><span class="sxs-lookup"><span data-stu-id="c2932-164">8</span></span>|<span data-ttu-id="c2932-165">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-165">Yes</span></span>|  
|<span data-ttu-id="c2932-166">IndexID</span><span class="sxs-lookup"><span data-stu-id="c2932-166">IndexID</span></span>|`int`|<span data-ttu-id="c2932-167">Número de saltos que quedan para el mensaje reenviado.</span><span class="sxs-lookup"><span data-stu-id="c2932-167">The number of hops remaining for the forwarded message.</span></span>|<span data-ttu-id="c2932-168">24</span><span class="sxs-lookup"><span data-stu-id="c2932-168">24</span></span>|<span data-ttu-id="c2932-169">No</span><span class="sxs-lookup"><span data-stu-id="c2932-169">No</span></span>|  
|<span data-ttu-id="c2932-170">IntegerData</span><span class="sxs-lookup"><span data-stu-id="c2932-170">IntegerData</span></span>|`int`|<span data-ttu-id="c2932-171">Número de fragmento del mensaje reenviado.</span><span class="sxs-lookup"><span data-stu-id="c2932-171">The fragment number of the forwarded message.</span></span>|<span data-ttu-id="c2932-172">25</span><span class="sxs-lookup"><span data-stu-id="c2932-172">25</span></span>|<span data-ttu-id="c2932-173">No</span><span class="sxs-lookup"><span data-stu-id="c2932-173">No</span></span>|  
|<span data-ttu-id="c2932-174">LoginSid</span><span class="sxs-lookup"><span data-stu-id="c2932-174">LoginSid</span></span>|`image`|<span data-ttu-id="c2932-175">SID (número de identificación de seguridad) del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2932-175">The security identification number (SID) of the logged-in user.</span></span> <span data-ttu-id="c2932-176">Cada SID es único para cada inicio de sesión en el servidor.</span><span class="sxs-lookup"><span data-stu-id="c2932-176">Each SID is unique for each login in the server.</span></span>|<span data-ttu-id="c2932-177">41</span><span class="sxs-lookup"><span data-stu-id="c2932-177">41</span></span>|<span data-ttu-id="c2932-178">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-178">Yes</span></span>|  
|<span data-ttu-id="c2932-179">NTDomainName</span><span class="sxs-lookup"><span data-stu-id="c2932-179">NTDomainName</span></span>|`nvarchar`|<span data-ttu-id="c2932-180">Dominio de Windows al que pertenece el usuario.</span><span class="sxs-lookup"><span data-stu-id="c2932-180">The Windows domain to which the user belongs.</span></span>|<span data-ttu-id="c2932-181">7</span><span class="sxs-lookup"><span data-stu-id="c2932-181">7</span></span>|<span data-ttu-id="c2932-182">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-182">Yes</span></span>|  
|<span data-ttu-id="c2932-183">NTUserName</span><span class="sxs-lookup"><span data-stu-id="c2932-183">NTUserName</span></span>|`nvarchar`|<span data-ttu-id="c2932-184">Nombre del usuario al que pertenece la conexión que generó este evento.</span><span class="sxs-lookup"><span data-stu-id="c2932-184">The name of the user that owns the connection that generated this event.</span></span>|<span data-ttu-id="c2932-185">6</span><span class="sxs-lookup"><span data-stu-id="c2932-185">6</span></span>|<span data-ttu-id="c2932-186">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-186">Yes</span></span>|  
|<span data-ttu-id="c2932-187">ObjectId</span><span class="sxs-lookup"><span data-stu-id="c2932-187">ObjectId</span></span>|`int`|<span data-ttu-id="c2932-188">Tiempo de vida del mensaje reenviado.</span><span class="sxs-lookup"><span data-stu-id="c2932-188">The time to live value of the forwarded message.</span></span>|<span data-ttu-id="c2932-189">22</span><span class="sxs-lookup"><span data-stu-id="c2932-189">22</span></span>|<span data-ttu-id="c2932-190">No</span><span class="sxs-lookup"><span data-stu-id="c2932-190">No</span></span>|  
|<span data-ttu-id="c2932-191">ObjectName</span><span class="sxs-lookup"><span data-stu-id="c2932-191">ObjectName</span></span>|`nvarchar`|<span data-ttu-id="c2932-192">Identificador del mensaje reenviado.</span><span class="sxs-lookup"><span data-stu-id="c2932-192">Message ID of the forwarded message.</span></span>|<span data-ttu-id="c2932-193">34</span><span class="sxs-lookup"><span data-stu-id="c2932-193">34</span></span>|<span data-ttu-id="c2932-194">No</span><span class="sxs-lookup"><span data-stu-id="c2932-194">No</span></span>|  
|<span data-ttu-id="c2932-195">OwnerName</span><span class="sxs-lookup"><span data-stu-id="c2932-195">OwnerName</span></span>|`nvarchar`|<span data-ttu-id="c2932-196">Identificador de la instancia del agente del destino del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2932-196">The broker instance identifier for the destination of the message.</span></span>|<span data-ttu-id="c2932-197">37</span><span class="sxs-lookup"><span data-stu-id="c2932-197">37</span></span>|<span data-ttu-id="c2932-198">No</span><span class="sxs-lookup"><span data-stu-id="c2932-198">No</span></span>|  
|<span data-ttu-id="c2932-199">RoleName</span><span class="sxs-lookup"><span data-stu-id="c2932-199">RoleName</span></span>|`nvarchar`|<span data-ttu-id="c2932-200">Rol del identificador de conversación.</span><span class="sxs-lookup"><span data-stu-id="c2932-200">The role of the conversation handle.</span></span> <span data-ttu-id="c2932-201">Uno de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2932-201">One of:</span></span><br /><br /> <span data-ttu-id="c2932-202">Initiator.</span><span class="sxs-lookup"><span data-stu-id="c2932-202">Initiator.</span></span> <span data-ttu-id="c2932-203">Este agente inició la conversación.</span><span class="sxs-lookup"><span data-stu-id="c2932-203">This broker initiated the conversation.</span></span><br /><br /> <span data-ttu-id="c2932-204">Target.</span><span class="sxs-lookup"><span data-stu-id="c2932-204">Target.</span></span> <span data-ttu-id="c2932-205">Este agente es el destino de la conversación.</span><span class="sxs-lookup"><span data-stu-id="c2932-205">This broker is the target of the conversation.</span></span>|<span data-ttu-id="c2932-206">38</span><span class="sxs-lookup"><span data-stu-id="c2932-206">38</span></span>|<span data-ttu-id="c2932-207">No</span><span class="sxs-lookup"><span data-stu-id="c2932-207">No</span></span>|  
|<span data-ttu-id="c2932-208">nombreDeServidor</span><span class="sxs-lookup"><span data-stu-id="c2932-208">ServerName</span></span>|`nvarchar`|<span data-ttu-id="c2932-209">Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c2932-209">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] being traced.</span></span>|<span data-ttu-id="c2932-210">26</span><span class="sxs-lookup"><span data-stu-id="c2932-210">26</span></span>|<span data-ttu-id="c2932-211">No</span><span class="sxs-lookup"><span data-stu-id="c2932-211">No</span></span>|  
|<span data-ttu-id="c2932-212">severity</span><span class="sxs-lookup"><span data-stu-id="c2932-212">Severity</span></span>|`int`|<span data-ttu-id="c2932-213">Número de nivel de gravedad para el texto del evento.</span><span class="sxs-lookup"><span data-stu-id="c2932-213">Severity number for the text in the event.</span></span>|<span data-ttu-id="c2932-214">29</span><span class="sxs-lookup"><span data-stu-id="c2932-214">29</span></span>|<span data-ttu-id="c2932-215">No</span><span class="sxs-lookup"><span data-stu-id="c2932-215">No</span></span>|  
|<span data-ttu-id="c2932-216">SPID</span><span class="sxs-lookup"><span data-stu-id="c2932-216">SPID</span></span>|`int`|<span data-ttu-id="c2932-217">Identificador de proceso del servidor que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asigna al proceso asociado al cliente.</span><span class="sxs-lookup"><span data-stu-id="c2932-217">The server process ID assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to the process associated with the client.</span></span>|<span data-ttu-id="c2932-218">12</span><span class="sxs-lookup"><span data-stu-id="c2932-218">12</span></span>|<span data-ttu-id="c2932-219">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-219">Yes</span></span>|  
|<span data-ttu-id="c2932-220">StartTime</span><span class="sxs-lookup"><span data-stu-id="c2932-220">StartTime</span></span>|`datetime`|<span data-ttu-id="c2932-221">Hora a la que se inició el evento, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="c2932-221">The time at which the event started, when available.</span></span>|<span data-ttu-id="c2932-222">14</span><span class="sxs-lookup"><span data-stu-id="c2932-222">14</span></span>|<span data-ttu-id="c2932-223">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-223">Yes</span></span>|  
|<span data-ttu-id="c2932-224">State</span><span class="sxs-lookup"><span data-stu-id="c2932-224">State</span></span>|`int`|<span data-ttu-id="c2932-225">Indica la ubicación en el código fuente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="c2932-225">Indicates the location within the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source code that produced the event.</span></span> <span data-ttu-id="c2932-226">Cada lugar en el que se puede producir este evento tiene un código de estado diferente.</span><span class="sxs-lookup"><span data-stu-id="c2932-226">Each location that may produce this event has a different state code.</span></span> <span data-ttu-id="c2932-227">Un ingeniero de soporte técnico de Microsoft puede utilizar este código de estado para buscar el lugar en que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="c2932-227">A Microsoft support engineer can use this state code to find where the event was produced.</span></span>|<span data-ttu-id="c2932-228">30</span><span class="sxs-lookup"><span data-stu-id="c2932-228">30</span></span>|<span data-ttu-id="c2932-229">No</span><span class="sxs-lookup"><span data-stu-id="c2932-229">No</span></span>|  
|<span data-ttu-id="c2932-230">Correcto</span><span class="sxs-lookup"><span data-stu-id="c2932-230">Success</span></span>|`int`|<span data-ttu-id="c2932-231">Tiempo de duración del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2932-231">The amount of time that the message has been alive.</span></span> <span data-ttu-id="c2932-232">Cuando este valor es mayor o igual que el tiempo de vida, el mensaje se quita.</span><span class="sxs-lookup"><span data-stu-id="c2932-232">When this value is greater than or equal to the time to live, the message is dropped.</span></span>|<span data-ttu-id="c2932-233">23</span><span class="sxs-lookup"><span data-stu-id="c2932-233">23</span></span>|<span data-ttu-id="c2932-234">No</span><span class="sxs-lookup"><span data-stu-id="c2932-234">No</span></span>|  
|<span data-ttu-id="c2932-235">TargetLoginName</span><span class="sxs-lookup"><span data-stu-id="c2932-235">TargetLoginName</span></span>|`nvarchar`|<span data-ttu-id="c2932-236">Dirección de red a la que se habría reenviado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2932-236">The network address that the message would have been forwarded to.</span></span>|<span data-ttu-id="c2932-237">42</span><span class="sxs-lookup"><span data-stu-id="c2932-237">42</span></span>|<span data-ttu-id="c2932-238">No</span><span class="sxs-lookup"><span data-stu-id="c2932-238">No</span></span>|  
|<span data-ttu-id="c2932-239">TargetUserName</span><span class="sxs-lookup"><span data-stu-id="c2932-239">TargetUserName</span></span>|`nvarchar`|<span data-ttu-id="c2932-240">Nombre del servicio que ha iniciado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2932-240">The name of the initiating service for the message.</span></span>|<span data-ttu-id="c2932-241">39</span><span class="sxs-lookup"><span data-stu-id="c2932-241">39</span></span>|<span data-ttu-id="c2932-242">No</span><span class="sxs-lookup"><span data-stu-id="c2932-242">No</span></span>|  
|<span data-ttu-id="c2932-243">TextData</span><span class="sxs-lookup"><span data-stu-id="c2932-243">TextData</span></span>|`ntext`|<span data-ttu-id="c2932-244">Descripción del motivo por el que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quitó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2932-244">Description of the reason that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dropped the message.</span></span>|<span data-ttu-id="c2932-245">1</span><span class="sxs-lookup"><span data-stu-id="c2932-245">1</span></span>|<span data-ttu-id="c2932-246">Sí</span><span class="sxs-lookup"><span data-stu-id="c2932-246">Yes</span></span>|  
|<span data-ttu-id="c2932-247">Transaction ID</span><span class="sxs-lookup"><span data-stu-id="c2932-247">Transaction ID</span></span>|`bigint`|<span data-ttu-id="c2932-248">Identificador de la transacción asignado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="c2932-248">The system-assigned ID of the transaction.</span></span>|<span data-ttu-id="c2932-249">4</span><span class="sxs-lookup"><span data-stu-id="c2932-249">4</span></span>|<span data-ttu-id="c2932-250">No</span><span class="sxs-lookup"><span data-stu-id="c2932-250">No</span></span>|  
  
 <span data-ttu-id="c2932-251">La columna TextData de este evento contiene una descripción del motivo por el que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] quitó el mensaje.</span><span class="sxs-lookup"><span data-stu-id="c2932-251">The TextData column of this event contains a description of the reason that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dropped the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2932-252">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2932-252">See Also</span></span>  
 [<span data-ttu-id="c2932-253">SQL Server Service Broker</span><span class="sxs-lookup"><span data-stu-id="c2932-253">SQL Server Service Broker</span></span>](../../database-engine/configure-windows/sql-server-service-broker.md)  
  
  