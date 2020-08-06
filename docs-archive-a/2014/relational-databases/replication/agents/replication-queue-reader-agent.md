---
title: Agente de lectura de cola de replicación | Microsoft Docs
ms.custom: ''
ms.date: 10/29/2018
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- agents [SQL Server replication], Queue Reader Agent
- command prompt [SQL Server replication]
- Queue Reader Agent, parameter reference
- Queue Reader Agent, executables
ms.assetid: 8e227793-11f6-47c6-99dc-ffc282f5d4bf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 854c425db3fbaa346dab5eb2c41bd58cf03f65c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663420"
---
# <a name="replication-queue-reader-agent"></a><span data-ttu-id="42667-102">Agente de lectura de cola de replicación</span><span class="sxs-lookup"><span data-stu-id="42667-102">Replication Queue Reader Agent</span></span>
  <span data-ttu-id="42667-103">El Agente de lectura de cola de replicación es un ejecutable que lee los mensajes almacenados en una cola de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o una cola de mensajes [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue y luego aplica esos mensajes al publicador.</span><span class="sxs-lookup"><span data-stu-id="42667-103">The Replication Queue Reader Agent is an executable that reads messages stored in a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue or a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Message Queue and then applies those messages to the Publisher.</span></span> <span data-ttu-id="42667-104">El Agente de lectura de cola se utiliza con la instantánea y las publicaciones transaccionales que permiten la actualización en cola.</span><span class="sxs-lookup"><span data-stu-id="42667-104">Queue Reader Agent is used with snapshot and transactional publications that allow queued updating.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42667-105">Los parámetros se pueden especificar en cualquier orden.</span><span class="sxs-lookup"><span data-stu-id="42667-105">Parameters can be specified in any order.</span></span> <span data-ttu-id="42667-106">Cuando no se especifican parámetros opcionales, se utilizan valores predefinidos basados en el perfil de agente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="42667-106">When optional parameters are not specified, predefined values based on the default agent profile are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42667-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42667-107">Syntax</span></span>  
  
```  
  
      qrdrsvc [-?]  
[-Continuous]  
[-DefinitionFiledefinition_file]  
[-Distributorserver_name[\instance_name]]  
[-DistributionDBdistribution_database]  
[-DistributorLogindistributor_login]  
[-DistributorPassworddistributor_password]  
[-DistributorSecurityMode [0|1]]  
[-EncryptionLevel [0|1|2]]  
[-HistoryVerboseLevel [0|1|2|3]]  
[-LoginTimeOutlogin_time_out_seconds]  
[-Outputoutput_path_and_file_name]  
[-OutputVerboseLevel [0|1|2]]  
[-PollingIntervalpolling_interval]  
[-PublisherFailoverPartnerserver_name[\instance_name] ]  
[-ProfileNameagent_profile_name]  
[-QueryTimeOutquery_time_out_seconds]  
[-ResolverState [1|2|3]]  
```  
  
## <a name="arguments"></a><span data-ttu-id="42667-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="42667-108">Arguments</span></span>  
 <span data-ttu-id="42667-109">**-?**</span><span class="sxs-lookup"><span data-stu-id="42667-109">**-?**</span></span>  
 <span data-ttu-id="42667-110">Muestra información de uso.</span><span class="sxs-lookup"><span data-stu-id="42667-110">Displays usage information.</span></span>  
  
 <span data-ttu-id="42667-111">**-Continuous**</span><span class="sxs-lookup"><span data-stu-id="42667-111">**-Continuous**</span></span>  
 <span data-ttu-id="42667-112">Especifica si el agente intenta procesar continuamente las transacciones en cola.</span><span class="sxs-lookup"><span data-stu-id="42667-112">Specifies whether the agent attempts to process queued transactions continuously.</span></span> <span data-ttu-id="42667-113">Si se especifica, el agente continúa la ejecución incluso si no hay transacciones en cola pendientes de cualquiera de los suscriptores.</span><span class="sxs-lookup"><span data-stu-id="42667-113">If specified, the agent continues execution even if there are no queued transactions pending from any of the subscribers.</span></span>  
  
 <span data-ttu-id="42667-114">**-DefinitionFile** _def_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="42667-114">**-DefinitionFile** _def_path_and_file_name_</span></span>  
 <span data-ttu-id="42667-115">Es la ruta de acceso del archivo de definición de agente.</span><span class="sxs-lookup"><span data-stu-id="42667-115">Is the path of the agent definition file.</span></span> <span data-ttu-id="42667-116">Un archivo de definición de agente contiene los argumentos de línea de comandos para el agente.</span><span class="sxs-lookup"><span data-stu-id="42667-116">An agent definition file contains command-line arguments for the agent.</span></span> <span data-ttu-id="42667-117">El contenido del archivo se analiza como un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="42667-117">The content of the file is parsed as an executable file.</span></span> <span data-ttu-id="42667-118">Utilice las comillas tipográficas (") para especificar valores de argumento que contienen caracteres arbitrarios.</span><span class="sxs-lookup"><span data-stu-id="42667-118">Use double quotation marks (") to specify argument values containing arbitrary characters.</span></span>  
  
 <span data-ttu-id="42667-119">**-Distributor** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="42667-119">**-Distributor** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="42667-120">Es el nombre del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="42667-120">Is the Distributor name.</span></span> <span data-ttu-id="42667-121">Especifique *server_name* para conectarse a la instancia predeterminada del [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="42667-121">Specify *server_name* for the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="42667-122">Especifique *server_name*\\*instance_name* para una instancia con nombre de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="42667-122">Specify *server_name*\\*instance_name* for a named instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on that server.</span></span> <span data-ttu-id="42667-123">Si no se especifica, el nombre tiene como valor predeterminado el nombre de la instancia predeterminada de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="42667-123">If not specified, the name defaults to the name of the default instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="42667-124">**-DistributionDB** _distribution_database_</span><span class="sxs-lookup"><span data-stu-id="42667-124">**-DistributionDB** _distribution_database_</span></span>  
 <span data-ttu-id="42667-125">Es la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="42667-125">Is the distribution database.</span></span>  
  
 <span data-ttu-id="42667-126">**-DistributorLogin** _distributor_login_</span><span class="sxs-lookup"><span data-stu-id="42667-126">**-DistributorLogin** _distributor_login_</span></span>  
 <span data-ttu-id="42667-127">Es el nombre de inicio de sesión del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="42667-127">Is the Distributor login name.</span></span>  
  
 <span data-ttu-id="42667-128">**-DistributorPassword** _distributor_password_</span><span class="sxs-lookup"><span data-stu-id="42667-128">**-DistributorPassword** _distributor_password_</span></span>  
 <span data-ttu-id="42667-129">Es la contraseña del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="42667-129">Is the Distributor password.</span></span>  
  
 <span data-ttu-id="42667-130">**-DistributorSecurityMode** [ **0**| **1**]</span><span class="sxs-lookup"><span data-stu-id="42667-130">**-DistributorSecurityMode** [ **0**| **1**]</span></span>  
 <span data-ttu-id="42667-131">Especifica el modo de seguridad del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="42667-131">Specifies the security mode of the Distributor.</span></span> <span data-ttu-id="42667-132">Un valor de **0** hace referencia a la autenticación de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (valor predeterminado) y un valor de **1** hace referencia al modo de autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="42667-132">A value of **0** indicates [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication Mode (default), and a value of **1** indicates Windows Authentication Mode.</span></span>  
  
 <span data-ttu-id="42667-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span><span class="sxs-lookup"><span data-stu-id="42667-133">**-EncryptionLevel** [ **0** | **1** | **2** ]</span></span>  
 <span data-ttu-id="42667-134">Es el nivel de cifrado de Capa de sockets seguros (SSL) utilizado por el Agente de lectura de cola cuando realiza conexiones.</span><span class="sxs-lookup"><span data-stu-id="42667-134">Is the level of Secure Sockets Layer (SSL) encryption used by the Queue Reader Agent when making connections.</span></span>  
  
|<span data-ttu-id="42667-135">Valor de EncryptionLevel</span><span class="sxs-lookup"><span data-stu-id="42667-135">EncryptionLevel value</span></span>|<span data-ttu-id="42667-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="42667-136">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="42667-137">**0**</span><span class="sxs-lookup"><span data-stu-id="42667-137">**0**</span></span>|<span data-ttu-id="42667-138">Especifica que no se utiliza SSL.</span><span class="sxs-lookup"><span data-stu-id="42667-138">Specifies that SSL is not used.</span></span>|  
|<span data-ttu-id="42667-139">**1**</span><span class="sxs-lookup"><span data-stu-id="42667-139">**1**</span></span>|<span data-ttu-id="42667-140">Especifica que se utiliza SSL, pero el agente no comprueba que un emisor confiable haya firmado el certificado del servidor SSL.</span><span class="sxs-lookup"><span data-stu-id="42667-140">Specifies that SSL is used, but the agent does not verify that the SSL server certificate is signed by a trusted issuer.</span></span>|  
|<span data-ttu-id="42667-141">**2**</span><span class="sxs-lookup"><span data-stu-id="42667-141">**2**</span></span>|<span data-ttu-id="42667-142">Especifica que se usa SSL y que se ha comprobado el certificado.</span><span class="sxs-lookup"><span data-stu-id="42667-142">Specifies that SSL is used, and that the certificate is verified.</span></span>|  

 > [!NOTE]  
 >  <span data-ttu-id="42667-143">Un certificado SSL válido se define con un nombre de dominio completo de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42667-143">A valid SSL certificate is defined with a fully qualified domain name of the SQL Server.</span></span> <span data-ttu-id="42667-144">Para que el agente se conecte correctamente al establecer -EncryptionLevel en 2, cree un alias en la instancia local de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42667-144">In order for the agent to connect successfully when setting -EncryptionLevel to 2, create an alias on the local SQL Server.</span></span> <span data-ttu-id="42667-145">El parámetro "Alias Name" debe ser el nombre del servidor, mientras que el parámetro "Server" se debe establecer en el nombre completo de la instancia de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="42667-145">The 'Alias Name' parameter should be the server name and the 'Server' parameter should be set to the fully qualified name of the SQL Server.</span></span>
  
 <span data-ttu-id="42667-146">Para obtener más información, consulte [replicación de SQL Server Security](../security/view-and-modify-replication-security-settings.md).</span><span class="sxs-lookup"><span data-stu-id="42667-146">For more information, see [SQL Server Replication Security](../security/view-and-modify-replication-security-settings.md).</span></span>  
  
 <span data-ttu-id="42667-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="42667-147">**-HistoryVerboseLevel** [ **0**| **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="42667-148">Especifica la cantidad de historial registrado durante una operación del lector de cola.</span><span class="sxs-lookup"><span data-stu-id="42667-148">Specifies the amount of history logged during a queue reader operation.</span></span> <span data-ttu-id="42667-149">Puede minimizar el efecto sobre el rendimiento del registro del historial seleccionando **1**.</span><span class="sxs-lookup"><span data-stu-id="42667-149">You can minimize the effect of history logging on performance by selecting **1**.</span></span>  
  
|<span data-ttu-id="42667-150">Valor HistoryVerboseLevel</span><span class="sxs-lookup"><span data-stu-id="42667-150">HistoryVerboseLevel value</span></span>|<span data-ttu-id="42667-151">Descripción</span><span class="sxs-lookup"><span data-stu-id="42667-151">Description</span></span>|  
|-------------------------------|-----------------|  
|<span data-ttu-id="42667-152">**0**</span><span class="sxs-lookup"><span data-stu-id="42667-152">**0**</span></span>|<span data-ttu-id="42667-153">Ningún registro del historial (no se recomienda).</span><span class="sxs-lookup"><span data-stu-id="42667-153">No history logging (not recommended).</span></span>|  
|<span data-ttu-id="42667-154">**1**</span><span class="sxs-lookup"><span data-stu-id="42667-154">**1**</span></span>|<span data-ttu-id="42667-155">Predeterminada.</span><span class="sxs-lookup"><span data-stu-id="42667-155">Default.</span></span> <span data-ttu-id="42667-156">Siempre actualiza un mensaje del historial anterior del mismo estado (inicio, progreso, éxito, etc.).</span><span class="sxs-lookup"><span data-stu-id="42667-156">Always update a previous history message of the same status (startup, progress, success, and so on).</span></span> <span data-ttu-id="42667-157">Si no existe ningún registro anterior con el mismo estado, inserta un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="42667-157">If no previous record with the same status exists, insert a new record.</span></span>|  
|<span data-ttu-id="42667-158">**2**</span><span class="sxs-lookup"><span data-stu-id="42667-158">**2**</span></span>|<span data-ttu-id="42667-159">Inserte nuevos registros del historial, incluso mensajes inactivos o mensajes del trabajo de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="42667-159">Insert new history records, including idle messages or long-running job messages.</span></span>|  
|<span data-ttu-id="42667-160">**3**</span><span class="sxs-lookup"><span data-stu-id="42667-160">**3**</span></span>|<span data-ttu-id="42667-161">Inserte nuevos registros de historial que incluyen detalles adicionales que pueden ser útiles para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="42667-161">Insert new history records that include additional details that may be useful for troubleshooting.</span></span>|  
  
 <span data-ttu-id="42667-162">**-LoginTimeOut** _login_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="42667-162">**-LoginTimeOut** _login_time_out_seconds_</span></span>  
 <span data-ttu-id="42667-163">Es el número de segundos antes de que el inicio de sesión exceda el tiempo de espera. El valor predeterminado es 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="42667-163">Is the number of seconds before the login times out. The default is 15 seconds.</span></span>  
  
 <span data-ttu-id="42667-164">**-Output** _output_path_and_file_name_</span><span class="sxs-lookup"><span data-stu-id="42667-164">**-Output** _output_path_and_file_name_</span></span>  
 <span data-ttu-id="42667-165">Es la ruta de acceso del archivo de salida del agente.</span><span class="sxs-lookup"><span data-stu-id="42667-165">Is the path of the agent output file.</span></span> <span data-ttu-id="42667-166">Si no se proporciona un nombre de archivo, el resultado se envía a la consola.</span><span class="sxs-lookup"><span data-stu-id="42667-166">If the file name is not provided, the output is sent to the console.</span></span> <span data-ttu-id="42667-167">Si el nombre de archivo especificado existe, el resultado se anexa al archivo.</span><span class="sxs-lookup"><span data-stu-id="42667-167">If the specified file name exists, the output is appended to the file.</span></span>  
  
 <span data-ttu-id="42667-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span><span class="sxs-lookup"><span data-stu-id="42667-168">**-OutputVerboseLevel** [ **0**| **1**| **2**]</span></span>  
 <span data-ttu-id="42667-169">Especifica si el resultado debería ser detallado.</span><span class="sxs-lookup"><span data-stu-id="42667-169">Specifies whether the output should be verbose.</span></span> <span data-ttu-id="42667-170">Si el nivel detallado es **0**, solo se imprimen los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="42667-170">If the verbose level is **0**, only error messages are printed.</span></span> <span data-ttu-id="42667-171">Si el nivel detallado es **1**, se imprimen todos los mensajes del informe de progreso.</span><span class="sxs-lookup"><span data-stu-id="42667-171">If the verbose level is **1**, all the progress report messages are printed.</span></span> <span data-ttu-id="42667-172">Si el nivel detallado es **2** (valor predeterminado), se imprimen todos los mensajes de error y mensajes del informe de progreso, lo que es útil para la depuración.</span><span class="sxs-lookup"><span data-stu-id="42667-172">If the verbose level is **2** (default), all error messages and progress report messages are printed, which is useful for debugging.</span></span>  
  
 <span data-ttu-id="42667-173">**-PollingInterval** _polling_interval_</span><span class="sxs-lookup"><span data-stu-id="42667-173">**-PollingInterval** _polling_interval_</span></span>  
 <span data-ttu-id="42667-174">Solo es pertinente para actualizar las suscripciones que utilizan colas basadas en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="42667-174">Is relevant only for updating subscriptions that use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] based queues.</span></span> <span data-ttu-id="42667-175">Especifica la frecuencia, en segundos, con la que se sondea la cola [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] las transacciones en cola pendientes.</span><span class="sxs-lookup"><span data-stu-id="42667-175">Specifies how often, in seconds, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] queue is polled for pending queued transactions.</span></span> <span data-ttu-id="42667-176">El valor puede estar comprendido entre 0 y 240 segundos.</span><span class="sxs-lookup"><span data-stu-id="42667-176">The value can be between 0 and 240 seconds.</span></span> <span data-ttu-id="42667-177">El valor predeterminado es 5 segundos.</span><span class="sxs-lookup"><span data-stu-id="42667-177">The default is 5 seconds.</span></span>  
  
 <span data-ttu-id="42667-178">**-PublisherFailoverPartner** _server_name_[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="42667-178">**-PublisherFailoverPartner** _server_name_[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="42667-179">Especifica la instancia del asociado de conmutación por error de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que participa en una sesión de creación de reflejo de la base de datos con la base de datos de publicación.</span><span class="sxs-lookup"><span data-stu-id="42667-179">Specifies the failover partner instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] participating in a database mirroring session with the publication database.</span></span> <span data-ttu-id="42667-180">Para obtener más información, vea [Replicación y creación de reflejo de la base de datos &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="42667-180">For more information, see [Database Mirroring and Replication &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md).</span></span>  
  
 <span data-ttu-id="42667-181">**-ProfileName** _agent_profile_name_</span><span class="sxs-lookup"><span data-stu-id="42667-181">**-ProfileName** _agent_profile_name_</span></span>  
 <span data-ttu-id="42667-182">Es el nombre de un perfil de agente utilizado para proporcionar un conjunto de valores predeterminados al agente.</span><span class="sxs-lookup"><span data-stu-id="42667-182">Is the name of an agent profile used to supply a set of default values to the agent.</span></span> <span data-ttu-id="42667-183">Para obtener información, vea [Perfiles del Agente de replicación](replication-agent-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="42667-183">For information, see [Replication Agent Profiles](replication-agent-profiles.md).</span></span>  
  
 <span data-ttu-id="42667-184">**-QueryTimeOut** _query_time_out_seconds_</span><span class="sxs-lookup"><span data-stu-id="42667-184">**-QueryTimeOut** _query_time_out_seconds_</span></span>  
 <span data-ttu-id="42667-185">Es el número de segundos antes de que la consulta exceda el tiempo de espera. El valor predeterminado es 1800 segundos.</span><span class="sxs-lookup"><span data-stu-id="42667-185">Is the number of seconds before the query times out. The default is 1800 seconds.</span></span>  
  
 <span data-ttu-id="42667-186">**-ResolverState** [ **1**| **2**| **3**]</span><span class="sxs-lookup"><span data-stu-id="42667-186">**-ResolverState** [ **1**| **2**| **3**]</span></span>  
 <span data-ttu-id="42667-187">Especifica cómo se resuelven los conflictos de actualización en cola.</span><span class="sxs-lookup"><span data-stu-id="42667-187">Specifies how queued updating conflicts are resolved.</span></span> <span data-ttu-id="42667-188">Un valor de **1** indica que el Publicador gana el conflicto, y la transacción en cola actual que está en conflicto se revertirá en el Publicador y el Suscriptor que originó la actualización; el procesamiento de las transacciones en cola posteriores continuará.</span><span class="sxs-lookup"><span data-stu-id="42667-188">A value of **1** indicates the Publisher wins the conflict, and the current conflicting queued transaction will be rolled back on the Publisher and the originating updating Subscriber; the processing of subsequent queued transactions will continue.</span></span> <span data-ttu-id="42667-189">Un valor de **2** indica que el Suscriptor gana el conflicto, y la transacción en cola invalidará los valores en el Publicador.</span><span class="sxs-lookup"><span data-stu-id="42667-189">A value of **2** indicates the Subscriber wins the conflict, and the queued transaction will override the values on the Publisher.</span></span> <span data-ttu-id="42667-190">Un valor de **3** indica que cualquier conflicto provocará la reinicialización del Suscriptor; el Publicador gana el conflicto, se finalizará el proceso de las transacciones en cola subsiguientes y se reinicializará la suscripción.</span><span class="sxs-lookup"><span data-stu-id="42667-190">A value of **3** indicates that any conflict will result in Subscriber re-initialization; the Publisher wins the conflict, processing of subsequent queued transactions will be terminated, and the subscription will be reinitialized.</span></span> <span data-ttu-id="42667-191">La configuración predeterminada es **1** para las publicaciones transaccionales y **3** para las publicaciones de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="42667-191">The default setting is **1** for transactional publications and **3** for snapshot publications.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42667-192">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42667-192">Remarks</span></span>  
 <span data-ttu-id="42667-193">Para iniciar el Agente de lectura de cola, ejecute **qrdrsvc.exe** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="42667-193">To start the Queue Reader Agent, execute **qrdrsvc.exe** from the command prompt.</span></span> <span data-ttu-id="42667-194">Para obtener información, vea [Aplicaciones ejecutables del Agente de replicación](../concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="42667-194">For information, see [Replication Agent Executables](../concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42667-195">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42667-195">See Also</span></span>  
 [<span data-ttu-id="42667-196">Administración del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="42667-196">Replication Agent Administration</span></span>](replication-agent-administration.md)  
  
  
