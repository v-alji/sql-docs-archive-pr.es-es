---
title: Utilidad ssbdiagnose (Service Broker) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, runtime reports
- Service Broker, command prompt utilities
- troubleshooting [Service Broker], conversations
- troubleshooting [Service Broker], configurations
- command prompt utilities [Service Broker]
- Service Broker, troubleshooting
- Service Broker, configuration reports
- Service Broker, tools
- troubleshooting [Service Broker], runtime
- conversations [Service Broker], troubleshooting
- troubleshooting [Service Broker], ssbdiagnose utility
- tools [Service Broker], ssbdiagnose
- Service Broker, ssbdiagnose utility
- ssbdiagnose
ms.assetid: 0c1636e8-a3db-438e-be4c-1ea40d1f4877
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8efc581eebd7d8fa7fa265abb54168af78b57ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747815"
---
# <a name="ssbdiagnose-utility-service-broker"></a><span data-ttu-id="ed729-102">utilidad ssbdiagnose (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="ed729-102">ssbdiagnose Utility (Service Broker)</span></span>
  <span data-ttu-id="ed729-103">La utilidad **ssbdiagnose** informa de la existencia de problemas en las conversaciones de [!INCLUDE[ssSB](../../includes/sssb-md.md)] o en la configuración de los servicios de [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed729-103">The **ssbdiagnose** utility reports issues in [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversations or the configuration of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services.</span></span> <span data-ttu-id="ed729-104">Las comprobaciones de la configuración se pueden realizar en dos servicios o en un único servicio.</span><span class="sxs-lookup"><span data-stu-id="ed729-104">Configuration checks can be made for either two services or a single service.</span></span> <span data-ttu-id="ed729-105">La existencia de problemas se indica en la ventana del símbolo del sistema en forma de texto legible, o como XML con formato que se puede redirigir a un archivo o a otro programa.</span><span class="sxs-lookup"><span data-stu-id="ed729-105">Issues are reported either in the command prompt window as human-readable text, or as formatted XML that can be redirected to a file or another program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed729-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed729-106">Syntax</span></span>  
  
```  
  
      ssbdiagnose   
[ [ -XML ]  
    [ -LEVEL { ERROR | WARNING | INFO } ]  
  [-IGNOREerror_id ] [ ...n]  
    [ <baseconnectionoptions> ]  
  { <configurationreport> | <runtimereport> }  
]  
| -?  
  
<configurationreport> ::=  
    CONFIGURATION  
  { [ FROM SERVICEservice_name  
      [ <fromconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
    [ TO SERVICEservice_name[, broker_id ]  
      [ <toconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
  }  
    ON CONTRACTcontract_name  
  [ ENCRYPTION { ON | OFF | ANONYMOUS } ]  
  
<runtime_report> ::=  
    RUNTIME  
    [-SHOWEVENTS ]  
        [ -NEW  
         [ -ID { conversation_handle  
                | conversation_group_id  
                 | conversation_id  
                  }  
        ] [ ...n]  
        ]  
    [ -TIMEOUTtimeout_interval ]  
    [ <runtimeconnectionoptions> ]  
  
<baseconnectionoptions> ::=  
  <connectionoptions>  
  
<fromconnectionoptions> ::=  
  <connectionoptions>  
  
<toconnectionoptions> ::=  
  <connectionoptions>  
  
<mirrorconnectionoptions> ::=  
  <connectionoptions>  
  
<runtimeconnectionoptions> ::=  
  [ CONNECT TO <connectionoptions> ] [ ...n]  
  
<connectionoptions> ::=  
    [ -E | { -Ulogin_id [ -Ppassword ] } ]  
  [ -Sserver_name[\instance_name] ]  
  [ -ddatabase_name ]  
  [ -llogin_timeout ]  
  
```  
  
## <a name="command-line-options"></a><span data-ttu-id="ed729-107">Opciones de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="ed729-107">Command Line Options</span></span>  
 <span data-ttu-id="ed729-108">**-XML**</span><span class="sxs-lookup"><span data-stu-id="ed729-108">**-XML**</span></span>  
 <span data-ttu-id="ed729-109">Especifica que la salida de **ssbdiagnose** se debe generar como XML con formato.</span><span class="sxs-lookup"><span data-stu-id="ed729-109">Specifies that the **ssbdiagnose** output be generated as formatted XML.</span></span> <span data-ttu-id="ed729-110">Dicha salida se puede redirigir a un archivo o a otra aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed729-110">This can be redirected to a file or to another application.</span></span> <span data-ttu-id="ed729-111">Si no se especifica **-XML** , la salida de **ssbdiagnose** se muestra como texto legible.</span><span class="sxs-lookup"><span data-stu-id="ed729-111">If **-XML** is not specified, the **ssbdiagnose** output is formatted as human-readable text.</span></span>  
  
 <span data-ttu-id="ed729-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span><span class="sxs-lookup"><span data-stu-id="ed729-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span></span>  
 <span data-ttu-id="ed729-113">Especifica el nivel de los mensajes que se notificarán.</span><span class="sxs-lookup"><span data-stu-id="ed729-113">Specifies the level of messages to report.</span></span>  
  
 <span data-ttu-id="ed729-114">**ERROR**: notifica únicamente los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-114">**ERROR**: report only error messages.</span></span>  
  
 <span data-ttu-id="ed729-115">**WARNING**: notifica los mensajes de advertencia y los de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-115">**WARNING**: report error and warning messages.</span></span>  
  
 <span data-ttu-id="ed729-116">**INFO**: notifica los mensajes de error, los de advertencia y los informativos.</span><span class="sxs-lookup"><span data-stu-id="ed729-116">**INFO**: report error, warning, and informational messages.</span></span>  
  
 <span data-ttu-id="ed729-117">El valor de configuración predeterminado es **WARNING**.</span><span class="sxs-lookup"><span data-stu-id="ed729-117">The default setting is **WARNING**.</span></span>  
  
 <span data-ttu-id="ed729-118">**-IGNORE** *error_id*</span><span class="sxs-lookup"><span data-stu-id="ed729-118">**-IGNORE** *error_id*</span></span>  
 <span data-ttu-id="ed729-119">Especifica que los errores o los mensajes con el *error_id* especificado no se deben incluir en los informes.</span><span class="sxs-lookup"><span data-stu-id="ed729-119">Specifies that errors or messages that have the specified *error_id* not be included in reports.</span></span> <span data-ttu-id="ed729-120">Puede especificar **-IGNORE** varias veces para suprimir varios identificadores de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ed729-120">You can specify **-IGNORE** multiple times to suppress multiple message IDs.</span></span>  
  
 **\<baseconnectionoptions>**  
 <span data-ttu-id="ed729-121">Especifica la información de conexión base que se usa en **ssbdiagnose** cuando no se incluyen opciones de conexión en una cláusula determinada.</span><span class="sxs-lookup"><span data-stu-id="ed729-121">Specifies the base connection information that is used by **ssbdiagnose** when connection options are not included in a specific clause.</span></span> <span data-ttu-id="ed729-122">La información de conexión proporcionada en una cláusula específica invalida la información de **baseconnectionoption** .</span><span class="sxs-lookup"><span data-stu-id="ed729-122">The connection information that is given in a specific clause overrides the **baseconnectionoption** information.</span></span> <span data-ttu-id="ed729-123">Este proceso se realiza para cada parámetro de forma individual.</span><span class="sxs-lookup"><span data-stu-id="ed729-123">This is performed separately for each parameter.</span></span> <span data-ttu-id="ed729-124">Por ejemplo, si tanto **-S** como **-d** se especifican en **baseconnetionoptions**y solo se especifica **-d** en **toconnetionoptions**, **ssbdiagnose** usará -S de **baseconnetionoptions** y -d de **toconnetionoptions**.</span><span class="sxs-lookup"><span data-stu-id="ed729-124">For example, if both **-S** and **-d** are specified in **baseconnetionoptions**, and only **-d** is specified in **toconnetionoptions**, **ssbdiagnose** uses -S from **baseconnetionoptions** and -d from **toconnetionoptions**.</span></span>  
  
 <span data-ttu-id="ed729-125">**CONFIGURATION**</span><span class="sxs-lookup"><span data-stu-id="ed729-125">**CONFIGURATION**</span></span>  
 <span data-ttu-id="ed729-126">Solicita un informe de errores de configuración entre un par de servicios de [!INCLUDE[ssSB](../../includes/sssb-md.md)] o de un único servicio.</span><span class="sxs-lookup"><span data-stu-id="ed729-126">Requests a report of configuration errors between a pair of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, or for a single service.</span></span>  
  
 <span data-ttu-id="ed729-127">**FROM SERVICE** *service_name*</span><span class="sxs-lookup"><span data-stu-id="ed729-127">**FROM SERVICE** *service_name*</span></span>  
 <span data-ttu-id="ed729-128">Especifica el servicio que inicia las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="ed729-128">Specifies the service that initiates conversations.</span></span>  
  
 **\<fromconnectionoptions>**  
 <span data-ttu-id="ed729-129">Especifica la información requerida para conectar con la base de datos que contiene el servicio del iniciador.</span><span class="sxs-lookup"><span data-stu-id="ed729-129">Specifies the information that is required to connect to the database that holds the initiator service.</span></span> <span data-ttu-id="ed729-130">Si no se especifica **fromconnectionoptions** , **ssbdiagnose** usa la información de conexión de **baseconnectionoptions** para conectarse a la base de datos del iniciador.</span><span class="sxs-lookup"><span data-stu-id="ed729-130">If **fromconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the initiator database.</span></span> <span data-ttu-id="ed729-131">Si se especifica **fromconnectionoptions** , se debe incluir la base de datos que contiene el servicio del iniciador.</span><span class="sxs-lookup"><span data-stu-id="ed729-131">If **fromconnectionoptions** is specified it must include the database that contains the initiator service.</span></span> <span data-ttu-id="ed729-132">Si **fromconnectionoptions** no se especifica, **baseconnectionoptions** debe especificar la base de datos del iniciador.</span><span class="sxs-lookup"><span data-stu-id="ed729-132">If **fromconnectionoptions** is not specified, the **baseconnectionoptions** must specify the initiator database.</span></span>  
  
 <span data-ttu-id="ed729-133">**TO SERVICE** *service_name*[, *broker_id* ]</span><span class="sxs-lookup"><span data-stu-id="ed729-133">**TO SERVICE** *service_name*[, *broker_id* ]</span></span>  
 <span data-ttu-id="ed729-134">Especifica el servicio que es el destino de las conversaciones.</span><span class="sxs-lookup"><span data-stu-id="ed729-134">Specifies the service that is the target for the conversations.</span></span>  
  
 <span data-ttu-id="ed729-135">*service_name*: especifica el nombre del servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="ed729-135">*service_name*: specifies the name of the target service.</span></span>  
  
 <span data-ttu-id="ed729-136">*broker_id*: especifica el identificador de [!INCLUDE[ssSB](../../includes/sssb-md.md)] que identifica la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="ed729-136">*broker_id*: specifies the [!INCLUDE[ssSB](../../includes/sssb-md.md)] ID that identifies the target database.</span></span> <span data-ttu-id="ed729-137">*broker_id* es un GUID.</span><span class="sxs-lookup"><span data-stu-id="ed729-137">*broker_id* is a GUID.</span></span> <span data-ttu-id="ed729-138">Puede ejecutar la siguiente consulta en la base de datos de destino para encontrarlo:</span><span class="sxs-lookup"><span data-stu-id="ed729-138">You can run the following query in the target database to find it:</span></span>  
  
```  
SELECT service_broker_guid  
FROM sys.databases  
WHERE database_id = DB_ID();  
```  
  
 **\<toconnectionoptions>**  
 <span data-ttu-id="ed729-139">Especifica la información requerida para conectar con la base de datos que contiene el servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="ed729-139">Specifies the information that is required to connect the database that holds the target service.</span></span> <span data-ttu-id="ed729-140">Si **toconnectionoptions** no se especifica, **ssbdiagnose** usa la información de conexión de **baseconnectionoptions** para conectarse a la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="ed729-140">If **toconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the target database.</span></span>  
  
 <span data-ttu-id="ed729-141">**MIRROR**</span><span class="sxs-lookup"><span data-stu-id="ed729-141">**MIRROR**</span></span>  
 <span data-ttu-id="ed729-142">Especifica que el servicio de [!INCLUDE[ssSB](../../includes/sssb-md.md)] asociado se hospeda en una base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="ed729-142">Specifies that the associated [!INCLUDE[ssSB](../../includes/sssb-md.md)] service is hosted in a mirrored database.</span></span> <span data-ttu-id="ed729-143">**ssbdiagnose** comprueba que la ruta al servicio es una ruta reflejada, donde se ha especificado MIRROR_ADDRESS en CREATE ROUTE.</span><span class="sxs-lookup"><span data-stu-id="ed729-143">**ssbdiagnose** verifies that the route to the service is a mirrored route, where MIRROR_ADDRESS was specified on CREATE ROUTE.</span></span>  
  
 **\<mirrorconnectionoptions>**  
 <span data-ttu-id="ed729-144">Especifica la información requerida para conectar con la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="ed729-144">Specifies the information that is required to connect to the mirror database.</span></span> <span data-ttu-id="ed729-145">Si no se especifica **mirrorconnectionoptions** , **ssbdiagnose** usa la información de conexión de **baseconnectionoptions** para conectarse a la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="ed729-145">If **mirrorconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the mirror database.</span></span>  
  
 <span data-ttu-id="ed729-146">**ON CONTRACT** *contract_name*</span><span class="sxs-lookup"><span data-stu-id="ed729-146">**ON CONTRACT** *contract_name*</span></span>  
 <span data-ttu-id="ed729-147">Indica que **ssbdiagnose** únicamente debe comprobar las configuraciones que usan el contrato especificado.</span><span class="sxs-lookup"><span data-stu-id="ed729-147">Requests that **ssbdiagnose** only check configurations that use the specified contract.</span></span> <span data-ttu-id="ed729-148">Si no se especifica ON CONTRACT, **ssbdiagnose** incluye información sobre el contrato denominado DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="ed729-148">If ON CONTRACT is not specified, **ssbdiagnose** reports on the contract named DEFAULT.</span></span>  
  
 <span data-ttu-id="ed729-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span><span class="sxs-lookup"><span data-stu-id="ed729-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span></span>  
 <span data-ttu-id="ed729-150">Solicita que se compruebe si el diálogo está configurado correctamente para el nivel de cifrado especificado:</span><span class="sxs-lookup"><span data-stu-id="ed729-150">Requests verification that the dialog is correctly configured for the specified level of encryption:</span></span>  
  
 <span data-ttu-id="ed729-151">**ON**: valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ed729-151">**ON**: Default setting.</span></span> <span data-ttu-id="ed729-152">Se ha configurado la seguridad de diálogo completa.</span><span class="sxs-lookup"><span data-stu-id="ed729-152">Full dialog security is configured.</span></span> <span data-ttu-id="ed729-153">Se han implementado los certificados en ambos extremos del diálogo, está presente un enlace de servicio remoto y la instrucción GRANT SEND para el servicio de destino especificó el usuario del iniciador.</span><span class="sxs-lookup"><span data-stu-id="ed729-153">Certificates have been deployed on both sides of the dialog, a remote service binding is present, and the GRANT SEND statement for the target service specified the initiator user.</span></span>  
  
 <span data-ttu-id="ed729-154">**OFF**: no se ha configurado la seguridad de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ed729-154">**OFF**: No dialog security is configured.</span></span> <span data-ttu-id="ed729-155">No se ha implementado ningún certificado, no se ha creado ningún enlace de servicio remoto y la instrucción GRANT SEND para el servicio del iniciador ha especificado el rol **public** .</span><span class="sxs-lookup"><span data-stu-id="ed729-155">No certificates have been deployed, no remote service binding was created, and the GRANT SEND for the initiator service specified the **public** role.</span></span>  
  
 <span data-ttu-id="ed729-156">**ANONYMOUS**: se ha configurado la seguridad de diálogo anónima.</span><span class="sxs-lookup"><span data-stu-id="ed729-156">**ANONYMOUS**: Anonymous dialog security is configured.</span></span> <span data-ttu-id="ed729-157">Se ha implementado un certificado, el enlace de servicio remoto ha especificado la cláusula anónima y la instrucción GRANT SEND del servicio de destino ha especificado el rol **public** .</span><span class="sxs-lookup"><span data-stu-id="ed729-157">One certificate has been deployed, the remote service binding specified the anonymous clause, and the GRANT SEND for the target service specified the **public** role.</span></span>  
  
 <span data-ttu-id="ed729-158">**RUNTIME**</span><span class="sxs-lookup"><span data-stu-id="ed729-158">**RUNTIME**</span></span>  
 <span data-ttu-id="ed729-159">Solicita un informe de los problemas que provocan errores en tiempo de ejecución en una conversación de [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed729-159">Requests a report of issues that cause runtime errors for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation.</span></span> <span data-ttu-id="ed729-160">Si no se especifican **-NEW** ni **-ID** , **ssbdiagnose** supervisa todas las conversaciones en todas las bases de datos especificadas en las opciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="ed729-160">If neither **-NEW** or **-ID** are specified, **ssbdiagnose** monitors all conversations in all databases specified in the connection options.</span></span> <span data-ttu-id="ed729-161">Si se especifican **-NEW** o **-ID** , **ssbdiagnose** genera una lista de los identificadores especificados en los parámetros.</span><span class="sxs-lookup"><span data-stu-id="ed729-161">If **-NEW** or **-ID** are specified, **ssbdiagnose** builds a list of the IDs specified in the parameters.</span></span>  
  
 <span data-ttu-id="ed729-162">Mientras **ssbdiagnose** se está ejecutando, registra todos los eventos de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] que indican errores de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed729-162">While **ssbdiagnose** is running, it records all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events that indicate runtime errors.</span></span> <span data-ttu-id="ed729-163">Registra los eventos que se producen en los identificadores especificados, además de los eventos del nivel de sistema.</span><span class="sxs-lookup"><span data-stu-id="ed729-163">It records the events that occur for the specified IDs, plus system-level events.</span></span> <span data-ttu-id="ed729-164">Si se encuentran errores de tiempo de ejecución, **ssbdiagnose** ejecuta un informe de la configuración asociada.</span><span class="sxs-lookup"><span data-stu-id="ed729-164">If runtime errors are encountered, **ssbdiagnose** runs a configuration report on the associated configuration.</span></span>  
  
 <span data-ttu-id="ed729-165">De forma predeterminada, los errores de tiempo de ejecución no se incluyen en el informe de salida, solo se incluyen los resultados del análisis de la configuración.</span><span class="sxs-lookup"><span data-stu-id="ed729-165">By default, runtime errors are not included in the output report, only the results of the configuration analysis.</span></span> <span data-ttu-id="ed729-166">Use **-SHOWEVENTS** para incluir los errores en tiempo de ejecución en el informe.</span><span class="sxs-lookup"><span data-stu-id="ed729-166">Use **-SHOWEVENTS** to have the runtime errors included in the report.</span></span>  
  
 <span data-ttu-id="ed729-167">**-SHOWEVENTS**</span><span class="sxs-lookup"><span data-stu-id="ed729-167">**-SHOWEVENTS**</span></span>  
 <span data-ttu-id="ed729-168">Indica que **ssbdiagnose** debe notificar los eventos de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] durante un informe RUNTIME.</span><span class="sxs-lookup"><span data-stu-id="ed729-168">Specifies that **ssbdiagnose** report [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events during a RUNTIME report.</span></span> <span data-ttu-id="ed729-169">Solo se informa de los eventos considerados como condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-169">Only events that are considered error conditions are reported.</span></span> <span data-ttu-id="ed729-170">De forma predeterminada, **ssbdiagnose** solamente supervisa los eventos de error; no informa de ellos en la salida.</span><span class="sxs-lookup"><span data-stu-id="ed729-170">By default, **ssbdiagnose** only monitors error events; it does not report them in the output.</span></span>  
  
 <span data-ttu-id="ed729-171">**-NEW**</span><span class="sxs-lookup"><span data-stu-id="ed729-171">**-NEW**</span></span>  
 <span data-ttu-id="ed729-172">Solicita la supervisión en tiempo de ejecución de la primera conversación que comienza después de que **ssbdiagnose** inicie su ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed729-172">Requests runtime monitoring of the first conversation that begins after **ssbdiagnose** starts running.</span></span>  
  
 <span data-ttu-id="ed729-173">**-ID**</span><span class="sxs-lookup"><span data-stu-id="ed729-173">**-ID**</span></span>  
 <span data-ttu-id="ed729-174">Solicita la supervisión en tiempo de ejecución de los elementos de la conversación especificados.</span><span class="sxs-lookup"><span data-stu-id="ed729-174">Requests runtime monitoring of the specified conversation elements.</span></span> <span data-ttu-id="ed729-175">Puede especificar **-ID** varias veces.</span><span class="sxs-lookup"><span data-stu-id="ed729-175">You can specify **-ID** multiple times.</span></span>  
  
 <span data-ttu-id="ed729-176">Si especifica un identificador de conversación, solo se informa de los eventos asociados al extremo de conversación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ed729-176">If you specify a conversation handle, only events associated with the associated conversation endpoint are reported.</span></span> <span data-ttu-id="ed729-177">Si especifica un identificador de conversación, se informa de todos los eventos de la conversación, así como de los de sus extremos de destino e iniciador.</span><span class="sxs-lookup"><span data-stu-id="ed729-177">If you specify a conversation ID, all events for that conversation and its initiator and target endpoints are reported.</span></span> <span data-ttu-id="ed729-178">Si se especifica un identificador de grupo de conversación, se informa de todos los eventos para todas las conversaciones y todos los extremos del grupo de conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-178">If a conversation group ID is specified, all events for all conversations and endpoints in the conversation group are reported.</span></span>  
  
 <span data-ttu-id="ed729-179">*conversation_handle*</span><span class="sxs-lookup"><span data-stu-id="ed729-179">*conversation_handle*</span></span>  
 <span data-ttu-id="ed729-180">Un identificador único que identifica un extremo de conversación en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ed729-180">A unique identifier that identifies a conversation endpoint in an application.</span></span> <span data-ttu-id="ed729-181">Los identificadores de conversación son únicos para cada extremo de la conversación; los extremos de destino e iniciador tienen identificadores de conversación independientes.</span><span class="sxs-lookup"><span data-stu-id="ed729-181">Conversation handles are unique to one endpoint of a conversation, the initiator and target endpoints have separate conversation handles.</span></span>  
  
 <span data-ttu-id="ed729-182">Los identificadores de conversación se devuelven a las aplicaciones mediante el *@dialog_handle* parámetro de la instrucción **Begin Dialog** y la `conversation_handle` columna en el conjunto de resultados de una instrucción **Receive** .</span><span class="sxs-lookup"><span data-stu-id="ed729-182">Conversation handles are returned to applications by the *@dialog_handle* parameter of the **BEGIN DIALOG** statement, and the `conversation_handle` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="ed729-183">Los identificadores de conversación se muestran en la `conversation_handle` columna de las vistas de catálogo **sys. transmission_queue** y **Sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="ed729-183">Conversation handles are reported in the `conversation_handle` column of the **sys.transmission_queue** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="ed729-184">*conversation_group_id*</span><span class="sxs-lookup"><span data-stu-id="ed729-184">*conversation_group_id*</span></span>  
 <span data-ttu-id="ed729-185">El identificador único que identifica un grupo de conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-185">The unique identifier that identifies a conversation group.</span></span>  
  
 <span data-ttu-id="ed729-186">Los identificadores de grupo de conversación se devuelven a las aplicaciones mediante el *@conversation_group_id* parámetro de la instrucción **Get Conversation Group** y la `conversation_group_id` columna en el conjunto de resultados de una instrucción **Receive** .</span><span class="sxs-lookup"><span data-stu-id="ed729-186">Conversation group IDs are returned to applications by the *@conversation_group_id* parameter of the **GET CONVERSATION GROUP** statement and the `conversation_group_id` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="ed729-187">Los identificadores de grupo de conversación se muestran en las `conversation_group_id` columnas de las vistas de catálogo **sys. conversation_groups** y **Sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="ed729-187">Conversation group IDs are reported in the `conversation_group_id` columns of the **sys.conversation_groups** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="ed729-188">*conversation_id*</span><span class="sxs-lookup"><span data-stu-id="ed729-188">*conversation_id*</span></span>  
 <span data-ttu-id="ed729-189">El identificador único que identifica una conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-189">The unique identifier that identifies a conversation.</span></span> <span data-ttu-id="ed729-190">Los identificadores de conversación son los mismos para los extremos de destino e iniciador de una conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-190">Conversation IDs are the same for both the initiator and target endpoints of a conversation.</span></span>  
  
 <span data-ttu-id="ed729-191">Los identificadores de conversación se muestran en la `conversation_id` columna de la vista de catálogo **sys. conversation_endpoints** .</span><span class="sxs-lookup"><span data-stu-id="ed729-191">Conversation IDs are reported in the `conversation_id` column of the **sys.conversation_endpoints** catalog view.</span></span>  
  
 <span data-ttu-id="ed729-192">**-TIMEOUT** *timeout_interval*</span><span class="sxs-lookup"><span data-stu-id="ed729-192">**-TIMEOUT** *timeout_interval*</span></span>  
 <span data-ttu-id="ed729-193">Especifica el número de segundos durante los que se debe ejecutar un informe **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="ed729-193">Specifies the number of seconds for a **RUNTIME** report to run.</span></span> <span data-ttu-id="ed729-194">Si no se especifica **-TIMEOUT** , el informe RUNTIME se ejecuta de forma indefinida.</span><span class="sxs-lookup"><span data-stu-id="ed729-194">If **-TIMEOUT** is not specified the runtime report runs indefinitely.</span></span> <span data-ttu-id="ed729-195">**-TIMEOUT** solo se usa en informes **RUNTIME** , no en informes **CONFIGURATION** .</span><span class="sxs-lookup"><span data-stu-id="ed729-195">**-TIMEOUT** is used only on **RUNTIME** reports, not **CONFIGURATION** reports.</span></span> <span data-ttu-id="ed729-196">Use CTRL+C para salir de **ssbdiagnose** si no se ha especificado **-TIMEOUT** o si quiere finalizar un informe RUNTIME antes de que expire el intervalo de tiempo de espera. **-**</span><span class="sxs-lookup"><span data-stu-id="ed729-196">Use ctrl + C to quit **ssbdiagnose** if **-TIMEOUT** was not specified or to end a runtime report before the time**-** out interval expires.</span></span> <span data-ttu-id="ed729-197">*timeout_interval* debe ser un número comprendido entre 1 y 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="ed729-197">*timeout_interval* must be a number between 1 and 2,147,483,647.</span></span>  
  
 **\<runtimeconnectionoptions>**  
 <span data-ttu-id="ed729-198">Especifica la información de conexión para las bases de datos que contienen los servicios asociados a los elementos de conversación que se están supervisando.</span><span class="sxs-lookup"><span data-stu-id="ed729-198">Specifies the connection information for the databases that contain the services associated with conversation elements being monitored.</span></span> <span data-ttu-id="ed729-199">Si todos los servicios se encuentran en la misma base de datos, solo es necesario especificar una cláusula **CONNECT TO** .</span><span class="sxs-lookup"><span data-stu-id="ed729-199">If all the services are in the same database, you only have to specify one **CONNECT TO** clause.</span></span> <span data-ttu-id="ed729-200">Por el contrario, si los servicios se encuentran en bases de datos independientes, será necesario especificar una cláusula **CONNECT TO** para cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="ed729-200">If the services are in separate databases you must supply a **CONNECT TO** clause for each database.</span></span> <span data-ttu-id="ed729-201">Si **runtimeconnectionoptions** no se especifica, **ssbdiagnose** usa la información de conexión de **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="ed729-201">If **runtimeconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions**.</span></span>  
  
 <span data-ttu-id="ed729-202">**-E**</span><span class="sxs-lookup"><span data-stu-id="ed729-202">**-E**</span></span>  
 <span data-ttu-id="ed729-203">Abre una conexión con autenticación de Windows para una instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] y usa la cuenta de Windows actual como identificador de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ed729-203">Open a Windows Authentication connection to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using your current Windows account as the login ID.</span></span> <span data-ttu-id="ed729-204">El usuario debe ser miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="ed729-204">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="ed729-205">La opción -E omite la configuración de usuario y de contraseña de las variables de entorno SQLCMDUSER y SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="ed729-205">The -E option ignores the user and password settings of the SQLCMDUSER and SQLCMDPASSWORD environment variables.</span></span>  
  
 <span data-ttu-id="ed729-206">Si no se especifican **-E** ni **-U** , **ssbdiagnose** usa el valor de la variable de entorno SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="ed729-206">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="ed729-207">Si tampoco se establece SQLCMDUSER, **ssbdiagnose** usa la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ed729-207">If SQLCMDUSER is not set either, **ssbdiagnose** uses Windows Authentication.</span></span>  
  
 <span data-ttu-id="ed729-208">Si se usa la opción **-E** junto con la opción **-U** o **-P** , se genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-208">If the **-E** option is used together with the **-U** option or the **-P** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="ed729-209">**-U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="ed729-209">**-U** *login_id*</span></span>  
 <span data-ttu-id="ed729-210">Abre una conexión con autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y usa el identificador de inicio de sesión especificado.</span><span class="sxs-lookup"><span data-stu-id="ed729-210">Open a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication connection by using the specified login ID.</span></span> <span data-ttu-id="ed729-211">El usuario debe ser miembro del rol fijo de servidor **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="ed729-211">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="ed729-212">Si no se especifican **-E** ni **-U** , **ssbdiagnose** usa el valor de la variable de entorno SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="ed729-212">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="ed729-213">Si tampoco se establece SQLCMDUSER, **ssbdiagnose** intenta la conexión mediante el modo de autenticación de Windows basado en la cuenta de Windows del usuario que está ejecutando **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="ed729-213">If SQLCMDUSER is not set either, **ssbdiagnose** tries to connect by using Windows Authentication mode based on the Windows account of the user who is running **ssbdiagnose**.</span></span>  
  
 <span data-ttu-id="ed729-214">Si se usa la opción **-U** junto con la opción **-E** , se genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-214">If the **-U** option is used together with the **-E** option, an error message is generated.</span></span> <span data-ttu-id="ed729-215">Si la opción **-U** va seguida de más de un argumento, se genera un mensaje de error y el programa se cierra.</span><span class="sxs-lookup"><span data-stu-id="ed729-215">If the **-U** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="ed729-216">**-P** *password*</span><span class="sxs-lookup"><span data-stu-id="ed729-216">**-P** *password*</span></span>  
 <span data-ttu-id="ed729-217">Especifica la contraseña para el identificador de inicio de sesión **-U** .</span><span class="sxs-lookup"><span data-stu-id="ed729-217">Specifies the password for the **-U** login ID.</span></span> <span data-ttu-id="ed729-218">En las contraseñas se distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ed729-218">Passwords are case sensitive.</span></span> <span data-ttu-id="ed729-219">Si se usa la opción **-U** pero no la opción **-P** , **ssbdiagnose** usa el valor de la variable de entorno SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="ed729-219">If the **-U** option is used and the **-P** option is not used, **ssbdiagnose** uses the value from the SQLCMDPASSWORD environment variable.</span></span> <span data-ttu-id="ed729-220">Si tampoco se establece SQLCMDPASSWORD, **ssbdiagnose** solicita al usuario una contraseña.</span><span class="sxs-lookup"><span data-stu-id="ed729-220">If SQLCMDPASSWORD is not set either, **ssbdiagnose** prompts the user for a password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ed729-221">Cuando escriba un comando SET SQLCMDPASSWORD, la contraseña será visible para cualquiera que pueda ver el monitor.</span><span class="sxs-lookup"><span data-stu-id="ed729-221">When you type a SET SQLCMDPASSWORD command, your password will be visible to anyone who can see your monitor.</span></span>  
  
 <span data-ttu-id="ed729-222">Si se especifica la opción **-P** sin una contraseña, **ssbdiagnose** usa la contraseña predeterminada (NULL).</span><span class="sxs-lookup"><span data-stu-id="ed729-222">If the **-P** option is specified without a password **ssbdiagnose** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteStrongPass](../../includes/ssnotestrongpass-md.md)] <span data-ttu-id="ed729-223">Para obtener más información, consulte [Contraseñas seguras](../../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="ed729-223">For more information, see [Strong Passwords](../../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="ed729-224">El mensaje de contraseña se muestra en la consola de la siguiente manera: `Password:`</span><span class="sxs-lookup"><span data-stu-id="ed729-224">The password prompt is displayed by printing the password prompt to the console, as follows: `Password:`</span></span>  
  
 <span data-ttu-id="ed729-225">La entrada del usuario queda oculta.</span><span class="sxs-lookup"><span data-stu-id="ed729-225">User input is hidden.</span></span> <span data-ttu-id="ed729-226">Esto significa que no se muestra nada y que el cursor permanece en su posición.</span><span class="sxs-lookup"><span data-stu-id="ed729-226">This means that nothing is displayed and the cursor stays in position.</span></span>  
  
 <span data-ttu-id="ed729-227">Si se usa la opción **-P** junto con la opción **-E** , se genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-227">If the **-P** option is used with the **-E** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="ed729-228">Si la opción **-P** va seguida de más de un argumento, se genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-228">If the **-P** option is followed by more than one argument, an error message is generated.</span></span>  
  
 <span data-ttu-id="ed729-229">**-S** *server_name*[\\*instance_name*]</span><span class="sxs-lookup"><span data-stu-id="ed729-229">**-S** *server_name*[\\*instance_name*]</span></span>  
 <span data-ttu-id="ed729-230">Especifica la instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que contiene los servicios de [!INCLUDE[ssSB](../../includes/sssb-md.md)] que se van a analizar.</span><span class="sxs-lookup"><span data-stu-id="ed729-230">Specifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span>  
  
 <span data-ttu-id="ed729-231">Especifique *server_name* para conectar con la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="ed729-231">Specify *server_name* to connect to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="ed729-232">Especifique *server_name ***\\*** instance_name* para conectarse a una instancia con nombre de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en ese servidor.</span><span class="sxs-lookup"><span data-stu-id="ed729-232">Specify *server_name***\\***instance_name* to connect to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="ed729-233">Si no se especifica **-S** , **ssbdiagnose** usa el valor de la variable de entorno SQLCMDSERVER.</span><span class="sxs-lookup"><span data-stu-id="ed729-233">If **-S** is not specified, **ssbdiagnose** uses the value of the SQLCMDSERVER environment variable.</span></span> <span data-ttu-id="ed729-234">Si tampoco se establece SQLCMDSERVER, **ssbdiagnose** se conecta a la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)] en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="ed729-234">If SQLCMDSERVER is not set either, **ssbdiagnose** connects to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="ed729-235">**-d** *database_name*</span><span class="sxs-lookup"><span data-stu-id="ed729-235">**-d** *database_name*</span></span>  
 <span data-ttu-id="ed729-236">Especifica la base de datos que contiene los servicios de [!INCLUDE[ssSB](../../includes/sssb-md.md)] que se van a analizar.</span><span class="sxs-lookup"><span data-stu-id="ed729-236">Specifies the database that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span> <span data-ttu-id="ed729-237">Si la base de datos no existe, se genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-237">If the database does not exist, an error message is generated.</span></span> <span data-ttu-id="ed729-238">Si no se especifica **-d** , el valor predeterminado es la base de datos especificada en la propiedad de base de datos predeterminada del inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="ed729-238">If **-d** is not specified, the default is the database specified in the default-database property for your login.</span></span>  
  
 <span data-ttu-id="ed729-239">**-l** *login_timeout*</span><span class="sxs-lookup"><span data-stu-id="ed729-239">**-l** *login_timeout*</span></span>  
 <span data-ttu-id="ed729-240">Especifica el número de segundos que deben transcurrir antes de que se agote el tiempo de espera de un intento de conexión con un servidor. Si no se especifica **-l** , **ssbdiagnose** usa el valor establecido en la variable de entorno SQLCMDLOGINTIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="ed729-240">Specifies the number of seconds before an attempt to connect to a server times out. If **-l** is not specified, **ssbdiagnose** uses the value set for the SQLCMDLOGINTIMEOUT environment variable.</span></span> <span data-ttu-id="ed729-241">Si tampoco se establece SQLCMDLOGINTIMEOUT, el valor predeterminado del tiempo de espera es de treinta segundos.</span><span class="sxs-lookup"><span data-stu-id="ed729-241">If SQLCMDLOGINTIMEOUT is not set either, the default time-out is thirty seconds.</span></span> <span data-ttu-id="ed729-242">El período de tiempo de espera de inicio de sesión debe ser un número comprendido entre 0 y 65534.</span><span class="sxs-lookup"><span data-stu-id="ed729-242">The login time-out must be a number between 0 and 65534.</span></span> <span data-ttu-id="ed729-243">Si el valor proporcionado no es numérico o no está dentro de este intervalo, **ssbdiagnose** genera un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-243">If the value that is supplied is not numeric or does not fall into that range, **ssbdiagnose** generates an error message.</span></span> <span data-ttu-id="ed729-244">El valor 0 especifica que el tiempo de espera es infinito.</span><span class="sxs-lookup"><span data-stu-id="ed729-244">A value of 0 specifies time-out to be infinite.</span></span>  
  
 <span data-ttu-id="ed729-245">**-?**</span><span class="sxs-lookup"><span data-stu-id="ed729-245">**-?**</span></span>  
 <span data-ttu-id="ed729-246">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed729-246">Displays command line help.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed729-247">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ed729-247">Remarks</span></span>  
 <span data-ttu-id="ed729-248">Use **ssbdiagnose** para lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ed729-248">Use **ssbdiagnose** to do the following:</span></span>  
  
-   <span data-ttu-id="ed729-249">Confirmar que no hay errores de configuración en una aplicación de [!INCLUDE[ssSB](../../includes/sssb-md.md)] que se acaba de configurar.</span><span class="sxs-lookup"><span data-stu-id="ed729-249">Confirm that there are no configuration errors in a newly configured [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="ed729-250">Confirmar que no hay errores de configuración después de cambiar la configuración de una aplicación de [!INCLUDE[ssSB](../../includes/sssb-md.md)] existente.</span><span class="sxs-lookup"><span data-stu-id="ed729-250">Confirm that there are no configuration errors after changing the configuration of an existing [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="ed729-251">Confirmar que no hay errores de configuración después de que una base de datos de [!INCLUDE[ssSB](../../includes/sssb-md.md)] se haya separado y vuelto a adjuntar a una nueva instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed729-251">Confirm that there are no configuration errors after a [!INCLUDE[ssSB](../../includes/sssb-md.md)] database is detached and then reattached to a new instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="ed729-252">Comprobar si hay errores de configuración cuando los mensajes no se transmiten correctamente entre los servicios.</span><span class="sxs-lookup"><span data-stu-id="ed729-252">Research whether there are configuration errors when messages are not successfully transmitted between services.</span></span>  
  
-   <span data-ttu-id="ed729-253">Obtener un informe de los errores que se producen en un conjunto de elementos de conversación de [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed729-253">Get a report of any errors that occur in a set of [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation elements.</span></span>  
  
## <a name="configuration-reporting"></a><span data-ttu-id="ed729-254">Creación de informes de configuración</span><span class="sxs-lookup"><span data-stu-id="ed729-254">Configuration Reporting</span></span>  
 <span data-ttu-id="ed729-255">Para analizar correctamente la configuración que se usa en una conversación, ejecute un informe de configuración de **ssbdiagnose** que use las mismas opciones que la conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-255">To correctly analyze the configuration used by a conversation, run a **ssbdiagnose** configuration report that uses the same options that are used by the conversation.</span></span> <span data-ttu-id="ed729-256">Si especifica para **ssbdiagnose** un nivel de opciones inferior al que usa la conversación, es posible que **ssbdiagnose** no informe de las condiciones requeridas por la conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-256">If you specify a lower level of options for **ssbdiagnose** than are used by the conversation, **ssbdiagnose** might not report conditions that are required by the conversation.</span></span> <span data-ttu-id="ed729-257">Si especifica un nivel de opciones superior para **ssbdiagnose**, es posible que se informe de elementos no requeridos por la conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-257">If you specify a higher level of options for **ssbdiagnose**, it might report items that are not required by the conversation.</span></span> <span data-ttu-id="ed729-258">Por ejemplo, una conversación entre dos servicios de la misma base de datos se puede ejecutar con ENCPRYPTION OFF.</span><span class="sxs-lookup"><span data-stu-id="ed729-258">For example, a conversation between two services in the same database can be run with ENCPRYPTION OFF.</span></span> <span data-ttu-id="ed729-259">Si ejecuta **ssbdiagnose** para validar la configuración entre ambos servicios, pero usa la opción ENCRYPTION ON predeterminada, **ssbdiagnose** informa de que falta una clave maestra en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ed729-259">If you run **ssbdiagnose** to validate the configuration between the two services, but use the default ENCRYPTION ON setting, **ssbdiagnose** reports that the database is missing a master key.</span></span> <span data-ttu-id="ed729-260">No se requiere una clave maestra en la conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-260">A master key is not required for the conversation.</span></span>  
  
 <span data-ttu-id="ed729-261">Cada vez que se ejecuta, el informe de configuración de **ssbdiagnose** solamente analiza un servicio de [!INCLUDE[ssSB](../../includes/sssb-md.md)] o un único par de servicios.</span><span class="sxs-lookup"><span data-stu-id="ed729-261">The **ssbdiagnose** configuration report analyzes only one [!INCLUDE[ssSB](../../includes/sssb-md.md)] service or a single pair of services every time it is run.</span></span> <span data-ttu-id="ed729-262">Si desea crear informes sobre varios pares de servicios de [!INCLUDE[ssSB](../../includes/sssb-md.md)] , cree un archivo de comandos .cmd que llame varias veces a **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="ed729-262">To report on multiple pairs of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, build a .cmd command file that calls **ssbdiagnose** multiple times.</span></span>  
  
## <a name="runtime-reporting"></a><span data-ttu-id="ed729-263">Creación de informes en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ed729-263">Runtime Reporting</span></span>  
 <span data-ttu-id="ed729-264">Cuando se especifica -RUNTIME, **ssbdiagnose** busca en todas las bases de datos indicadas en **runtimeconnectionoptions** y **baseconnectionoptions** para generar una lista de identificadores de [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed729-264">When -RUNTIME is specified, **ssbdiagnose** searches all databases specified in **runtimeconnectionoptions** and **baseconnectionoptions** to build a list of [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs.</span></span> <span data-ttu-id="ed729-265">La lista completa de identificadores generada depende de lo que se especifique para -NEW e -ID:</span><span class="sxs-lookup"><span data-stu-id="ed729-265">The full list of IDs built depends on what is specified for -NEW and -ID:</span></span>  
  
-   <span data-ttu-id="ed729-266">Si no se especifican **-NEW** ni **-ID** , la lista incluye todas las conversaciones para todas las bases de datos especificadas en las opciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="ed729-266">If neither **-NEW** or **-ID** are specified, the list includes all conversations for all databases specified in the connection options.</span></span>  
  
-   <span data-ttu-id="ed729-267">Si se especifica **-NEW** , **ssbdiagnose** incluye los elementos para la primera conversación que se inicia después de ejecutar **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="ed729-267">If **-NEW** is specified, **ssbdiagnose** includes the elements for the first conversation that starts after **ssbdiagnose** is run.</span></span> <span data-ttu-id="ed729-268">Esto incluye el identificador de conversación y los identificadores de conversación tanto para el extremo iniciador de la conversación como para el de destino.</span><span class="sxs-lookup"><span data-stu-id="ed729-268">This includes the conversation ID and the conversation handles for both the target and initiator conversation endpoints.</span></span>  
  
-   <span data-ttu-id="ed729-269">Si se especifica **-ID** con un identificador de conversación (de tipo handle), solo se incluirá este identificador en la lista.</span><span class="sxs-lookup"><span data-stu-id="ed729-269">If **-ID** is specified with a conversation handle, only that handle is included in the list.</span></span>  
  
-   <span data-ttu-id="ed729-270">Si se especifica **-ID** con un identificador de conversación (de tipo ID), se agregarán a la lista este identificador y los identificadores de tipo handle para ambos puntos de conexión de la conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-270">If **-ID** is specified with a conversation ID, the conversation ID and the handles for both of its conversation endpoints are added to the list.</span></span>  
  
-   <span data-ttu-id="ed729-271">Si se especifica **-ID** con un identificador de grupo de conversación, se agregarán a la lista todos los identificadores de conversación de tipo ID y de tipo handle de dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="ed729-271">If **-ID** is specified with a conversation group ID, all the conversation IDs and conversation handles in that group are added to the list.</span></span>  
  
 <span data-ttu-id="ed729-272">La lista no incluye los elementos de las bases de datos que no están cubiertas por las opciones de conexión.</span><span class="sxs-lookup"><span data-stu-id="ed729-272">The list does not include elements from databases that are not covered by the connection options.</span></span> <span data-ttu-id="ed729-273">Por ejemplo, supongamos que se usa **-ID** para especificar un identificador de conversación de tipo ID, pero que solo se proporciona una cláusula **runtimeconnectionoptions** para la base de datos del iniciador, no para la base de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="ed729-273">For example, assume that you use **-ID** to specify a conversation ID, but only provide a **runtimeconnectionoptions** clause for the initiator database and not the target database.</span></span> <span data-ttu-id="ed729-274">**ssbdiagnose** no incluirá el identificador de tipo handle de la conversación de destino en su lista de identificadores; solo incluirá el identificador de conversación de tipo ID y el identificador de tipo handle de conversación del iniciador.</span><span class="sxs-lookup"><span data-stu-id="ed729-274">**ssbdiagnose** will not include the target conversation handle in its list of IDs, only the conversation ID and the initiator conversation handle.</span></span>  
  
 <span data-ttu-id="ed729-275">**ssbdiagnose** supervisa los eventos de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] de las bases de datos cubiertas por **runtimeconnectionoptions** y **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="ed729-275">**ssbdiagnose** monitors the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events from the databases covered by **runtimeconnectionoptions** and **baseconnectionoptions**.</span></span> <span data-ttu-id="ed729-276">La utilidad busca eventos de [!INCLUDE[ssSB](../../includes/sssb-md.md)] que indican un error encontrado por parte de uno o varios de los identificadores de [!INCLUDE[ssSB](../../includes/sssb-md.md)] en la lista de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed729-276">It searches for [!INCLUDE[ssSB](../../includes/sssb-md.md)] events that indicate an error was encountered by one or more of the [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs in the runtime list.</span></span> <span data-ttu-id="ed729-277">**ssbdiagnose** también busca eventos de error de [!INCLUDE[ssSB](../../includes/sssb-md.md)] en el nivel de sistema que no están asociados específicamente a ningún grupo de conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-277">**ssbdiagnose** also searches for system-level [!INCLUDE[ssSB](../../includes/sssb-md.md)] error events not specifically associated with any conversation group.</span></span>  
  
 <span data-ttu-id="ed729-278">Si **ssbdiagnose** encuentra errores de conversación, la utilidad intentará notificar la causa raíz de los eventos mediante la ejecución de un informe de configuración.</span><span class="sxs-lookup"><span data-stu-id="ed729-278">If **ssbdiagnose** finds conversation errors, the utility will attempt to report on the root cause of the events by also running a configuration report.</span></span> <span data-ttu-id="ed729-279">**ssbdiagnose** usa los metadatos de las bases de datos para intentar determinar las instancias, los identificadores de [!INCLUDE[ssSB](../../includes/sssb-md.md)] , las bases de datos, los servicios y los contratos usados por la conversación.</span><span class="sxs-lookup"><span data-stu-id="ed729-279">**ssbdiagnose** uses the metadata in the databases to try to determine the instances, [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs, databases, services, and contracts used by the conversation.</span></span> <span data-ttu-id="ed729-280">A continuación, ejecuta un informe de configuración mediante toda la información disponible.</span><span class="sxs-lookup"><span data-stu-id="ed729-280">It then runs a configuration report using all available information.</span></span>  
  
 <span data-ttu-id="ed729-281">De forma predeterminada, **ssbdiagnose** no informa de los eventos de error.</span><span class="sxs-lookup"><span data-stu-id="ed729-281">By default, **ssbdiagnose** does not report error events.</span></span> <span data-ttu-id="ed729-282">Solo informa de los problemas subyacentes encontrados durante la comprobación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="ed729-282">It only reports the underlying issues found during the configuration check.</span></span> <span data-ttu-id="ed729-283">Esto minimiza la cantidad de información proporcionada y ayuda a concentrarse en los problemas de configuración subyacentes.</span><span class="sxs-lookup"><span data-stu-id="ed729-283">This minimizes the amount of information reported and helps you focus on the underlying configuration issues.</span></span> <span data-ttu-id="ed729-284">Puede especificar **-SHOWEVENTS** para ver los eventos de error que encuentra **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="ed729-284">You can specify **-SHOWEVENTS** to see the error events encountered by **ssbdiagnose**.</span></span>  
  
## <a name="issues-reported-by-ssbdiagnose"></a><span data-ttu-id="ed729-285">Problemas encontrados por ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="ed729-285">Issues Reported by ssbdiagnose</span></span>  
 <span data-ttu-id="ed729-286">**ssbdiagnose** informa de tres clases de problemas.</span><span class="sxs-lookup"><span data-stu-id="ed729-286">**ssbdiagnose** reports three classes of issues.</span></span> <span data-ttu-id="ed729-287">En el archivo de salida XML, cada clase de problema aparece como un tipo independiente de elemento Issue.</span><span class="sxs-lookup"><span data-stu-id="ed729-287">In the XML output file, each class of issue is reported as a separate type of the Issue element.</span></span> <span data-ttu-id="ed729-288">Los tres tipos de problemas notificados por **ssbdiagnose** son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed729-288">The three types of issues reported by **ssbdiagnose** are as follows:</span></span>  
  
 <span data-ttu-id="ed729-289">**Diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="ed729-289">**Diagnosis**</span></span>  
 <span data-ttu-id="ed729-290">Informa de un problema de configuración.</span><span class="sxs-lookup"><span data-stu-id="ed729-290">Reports a configuration issue.</span></span> <span data-ttu-id="ed729-291">Esto incluye los problemas encontrados durante la ejecución de un informe **CONFIGURATION** o durante la fase de configuración de un informe **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="ed729-291">This includes issues found either a **CONFIGURATION** report is running, or during the configuration phase of a **RUNTIME** report.</span></span> <span data-ttu-id="ed729-292">**ssbdiagnose** notifica una vez cada problema de configuración.</span><span class="sxs-lookup"><span data-stu-id="ed729-292">**ssbdiagnose** reports each configuration issue one time.</span></span>  
  
 <span data-ttu-id="ed729-293">**Evento**</span><span class="sxs-lookup"><span data-stu-id="ed729-293">**Event**</span></span>  
 <span data-ttu-id="ed729-294">Notifica un evento de [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] que indica que una conversación que se estaba supervisando ha encontrado un problema durante un informe **RUNTIME** .</span><span class="sxs-lookup"><span data-stu-id="ed729-294">Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event that indicates a problem was encountered by a conversation being monitored during a **RUNTIME** report.</span></span> <span data-ttu-id="ed729-295">**ssbdiagnose** notifica los eventos cada vez que se generan.</span><span class="sxs-lookup"><span data-stu-id="ed729-295">**ssbdiagnose** reports events every time they are generated.</span></span> <span data-ttu-id="ed729-296">Es posible que se informe más de una vez de los eventos si varias conversaciones encuentran el problema.</span><span class="sxs-lookup"><span data-stu-id="ed729-296">Events can be reported multiple times if several conversations encounter the problem.</span></span>  
  
 <span data-ttu-id="ed729-297">**Problema**</span><span class="sxs-lookup"><span data-stu-id="ed729-297">**Problem**</span></span>  
 <span data-ttu-id="ed729-298">Notifica un problema que impide que **ssbdiagnose** complete un análisis de configuración o supervise conversaciones.</span><span class="sxs-lookup"><span data-stu-id="ed729-298">Reports an issue that is preventing **ssbdiagnose** from completing a configuration analysis or from monitoring conversations.</span></span>  
  
## <a name="sqlcmd-environment-variables"></a><span data-ttu-id="ed729-299">Variables de entorno de sqlcmd</span><span class="sxs-lookup"><span data-stu-id="ed729-299">sqlcmd Environment Variables</span></span>  
 <span data-ttu-id="ed729-300">La utilidad **ssbdiagnose** admite las variables de entorno SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD y SQLCMDLOGINTIMOUT que también emplea la utilidad **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="ed729-300">The **ssbdiagnose** utility supports the SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD, and SQLCMDLOGINTIMOUT environment variables that are also used by the **sqlcmd** utility.</span></span> <span data-ttu-id="ed729-301">Puede establecer las variables de entorno mediante el comando SET del símbolo del sistema o el comando **setvar** en los scripts de [!INCLUDE[tsql](../../includes/tsql-md.md)] que ejecute con **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="ed729-301">You can set the environment variables either by using the command prompt SET command, or by using the **setvar** command in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that you run by using **sqlcmd**.</span></span> <span data-ttu-id="ed729-302">Para obtener más información sobre cómo usar **setvar** en **sqlcmd**, vea [Usar sqlcmd con variables de script](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="ed729-302">For more information about how to use **setvar** in **sqlcmd**, see [Use sqlcmd with Scripting Variables](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="ed729-303">Permisos</span><span class="sxs-lookup"><span data-stu-id="ed729-303">Permissions</span></span>  
 <span data-ttu-id="ed729-304">En cada cláusula **connectionoptions** , el inicio de sesión especificado con los parámetros **-E** o **-U** debe ser miembro del rol fijo de servidor **sysadmin** en la instancia especificada en **-S**.</span><span class="sxs-lookup"><span data-stu-id="ed729-304">In each **connectionoptions** clause, the login specified with either **-E** or **-U** must be a member of the **sysadmin** fixed-server role in the instance specified in **-S**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ed729-305">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ed729-305">Examples</span></span>  
 <span data-ttu-id="ed729-306">Esta sección contiene ejemplos de uso de **ssbdiagnose** en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="ed729-306">This section contains examples of using **ssbdiagnose** at a command prompt.</span></span>  
  
### <a name="a-checking-the-configuration-of-two-services-in-the-same-database"></a><span data-ttu-id="ed729-307">A.</span><span class="sxs-lookup"><span data-stu-id="ed729-307">A.</span></span> <span data-ttu-id="ed729-308">Comprobar la configuración de dos servicios en la misma base de datos</span><span class="sxs-lookup"><span data-stu-id="ed729-308">Checking the Configuration of Two Services in the Same Database</span></span>  
 <span data-ttu-id="ed729-309">En el ejemplo siguiente se muestra cómo solicitar un informe de configuración cuando se cumplen las siguientes condiciones;</span><span class="sxs-lookup"><span data-stu-id="ed729-309">The following example shows how to request a configuration report when the following are true;</span></span>  
  
-   <span data-ttu-id="ed729-310">El servicio iniciador y el servicio de destino están en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="ed729-310">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="ed729-311">La base de datos está en la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed729-311">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="ed729-312">La instancia se encuentra en el mismo equipo en el que se ejecuta **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="ed729-312">The instances is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="ed729-313">La utilidad **ssbdiagnose** notifica la configuración que usa el contrato DEFAULT porque no se ha especificado ON CONTRACT.</span><span class="sxs-lookup"><span data-stu-id="ed729-313">The **ssbdiagnose** utility reports the configuration that uses the DEFAULT contract because ON CONTRACT is not specified.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target  
```  
  
### <a name="b-checking-the-configuration-of-two-services-on-separate-computers-that-use-one-login"></a><span data-ttu-id="ed729-314">B.</span><span class="sxs-lookup"><span data-stu-id="ed729-314">B.</span></span> <span data-ttu-id="ed729-315">Comprobar la configuración de dos servicios en equipos independientes que usan un mismo inicio de sesión</span><span class="sxs-lookup"><span data-stu-id="ed729-315">Checking the Configuration of Two Services on Separate Computers That Use One Login</span></span>  
 <span data-ttu-id="ed729-316">En el ejemplo siguiente se muestra cómo solicitar un informe de configuración cuando el servicio iniciador y el servicio de destino están en equipos distintos, pero se puede obtener acceso a ellos usando el mismo inicio de sesión con autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ed729-316">The following example shows how to request a configuration report when the initiator and target service are on separate computers, but can be accessed by using the same Windows Authentication login.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator -S InitiatorComputer -d InitiatorDatabase TO SERVICE /test/target -S TargetComputer -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="c-checking-the-configuration-of-two-services-on-separate-computers-that-use-separate-logins"></a><span data-ttu-id="ed729-317">C.</span><span class="sxs-lookup"><span data-stu-id="ed729-317">C.</span></span> <span data-ttu-id="ed729-318">Comprobar la configuración de dos servicios en equipos independientes que usan inicios de sesión distintos</span><span class="sxs-lookup"><span data-stu-id="ed729-318">Checking the Configuration of Two Services on Separate Computers That Use Separate Logins</span></span>  
 <span data-ttu-id="ed729-319">En el ejemplo siguiente se muestra cómo solicitar un informe de configuración cuando el servicio iniciador y el servicio de destino están en equipos independientes, y se requieren inicios de sesión con autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] distintos para cada instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed729-319">The following example shows how to request a configuration report when the initiator and target service are on separate computers, and separate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication logins are required for each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```  
ssbdiagnose CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -U InitiatorLogin -p !wEx23Dvb   
-d InitiatorDatabase TO SERVICE /test/target -S TargetComputer   
-U TargetLogin -p ER!49jiy -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="d-checking-mirrored-service-configurations-on-separate-computers-with-anonymous-encryption"></a><span data-ttu-id="ed729-320">D.</span><span class="sxs-lookup"><span data-stu-id="ed729-320">D.</span></span> <span data-ttu-id="ed729-321">Comprobar las configuraciones de servicio reflejado en equipos independientes con cifrado anónimo</span><span class="sxs-lookup"><span data-stu-id="ed729-321">Checking Mirrored Service Configurations on Separate Computers With Anonymous Encryption</span></span>  
 <span data-ttu-id="ed729-322">En el ejemplo siguiente se muestra cómo solicitar un informe de configuración cuando el servicio iniciador y el servicio de destino están en equipos independientes, y el iniciador está reflejado en una instancia con nombre.</span><span class="sxs-lookup"><span data-stu-id="ed729-322">The following example shows how to request a configuration report when the initiator and target service are on separate computers and the initiator is mirrored to a named instance.</span></span> <span data-ttu-id="ed729-323">El informe también comprueba que los servicios están configurados para usar el cifrado anónimo.</span><span class="sxs-lookup"><span data-stu-id="ed729-323">The report also verifies that the services are configured to use anonymous encryption.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -d InitiatorDatabase MIRROR   
-S MirrorComputer/MirrorInstance TO SERVICE /test/target   
-S TargetComputer -d TargetDatabase ON CONTRACT TestContract ENCRYPTION ANONYMOUS  
```  
  
### <a name="e-checking-the-configuration-of-two-contracts"></a><span data-ttu-id="ed729-324">E.</span><span class="sxs-lookup"><span data-stu-id="ed729-324">E.</span></span> <span data-ttu-id="ed729-325">Comprobar la configuración de dos contratos</span><span class="sxs-lookup"><span data-stu-id="ed729-325">Checking the Configuration of Two Contracts</span></span>  
 <span data-ttu-id="ed729-326">En el ejemplo siguiente se muestra cómo crear un archivo de comandos que solicite informes de configuración cuando se cumplan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed729-326">The following example shows how to build a command file that requests configuration reports when the following are true:</span></span>  
  
-   <span data-ttu-id="ed729-327">El servicio iniciador y el servicio de destino están en la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="ed729-327">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="ed729-328">La base de datos está en la instancia predeterminada de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed729-328">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="ed729-329">La instancia se encuentra en el mismo equipo en el que se ejecuta **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="ed729-329">The instance is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="ed729-330">Cada vez que se ejecuta **ssbdiagnose** , notifica la configuración de un contrato distinto entre los mismos servicios.</span><span class="sxs-lookup"><span data-stu-id="ed729-330">Each time **ssbdiagnose** is run it reports the configuration for a different contract between the same services.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target ON CONTRACT PayRaiseContract  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator   
TO SERVICE /test/target ON CONTRACT PromotionContract  
```  
  
### <a name="f-monitor-the-status-of-a-specific-conversation-on-the-local-computer-with-a-time-out"></a><span data-ttu-id="ed729-331">F.</span><span class="sxs-lookup"><span data-stu-id="ed729-331">F.</span></span> <span data-ttu-id="ed729-332">Supervisar el estado de una conversación concreta en el equipo local con un tiempo de espera</span><span class="sxs-lookup"><span data-stu-id="ed729-332">Monitor the status of a specific conversation on the local computer with a time out</span></span>  
 <span data-ttu-id="ed729-333">En el ejemplo siguiente se muestra cómo supervisar una conversación concreta en la que los servicios de iniciador y destino están en la misma base de datos de la instancia predeterminada del mismo equipo que está ejecutando **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="ed729-333">The following example shows how to monitor a specific conversation where the initiator and target services are in the same database in the default instance of the same computer that is running **ssbdiagnose**.</span></span> <span data-ttu-id="ed729-334">El intervalo de tiempo de espera se establece en 20 segundos.</span><span class="sxs-lookup"><span data-stu-id="ed729-334">The time-out interval is set to 20 seconds.</span></span>  
  
```  
ssbdiagnose -E -d TestDatabase RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D -TIMEOUT 20  
```  
  
### <a name="g-monitor-the-status-of-a-conversation-that-spans-two-computers"></a><span data-ttu-id="ed729-335">G.</span><span class="sxs-lookup"><span data-stu-id="ed729-335">G.</span></span> <span data-ttu-id="ed729-336">Supervisar el estado de una conversación que abarca dos equipos</span><span class="sxs-lookup"><span data-stu-id="ed729-336">Monitor the status of a conversation that spans two computers</span></span>  
 <span data-ttu-id="ed729-337">En el ejemplo siguiente se muestra cómo supervisar una conversación concreta en la que los servicios iniciador y de destino están en equipos independientes.</span><span class="sxs-lookup"><span data-stu-id="ed729-337">The following example shows how to monitor a specific conversation where the initiator and target services are on separate computers.</span></span>  
  
```  
ssbdiagnose RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D   
-TIMEOUT 10 CONNECT TO -E -S InitiatorComputer/InitiatorInstance   
-d InitiatorDatabase CONNECT TO -E -S TargetComputer/TargetInstance   
-d TargetDatabase  
```  
  
### <a name="h-monitor-the-status-of-a-conversation-in-two-databases-in-the-same-instance"></a><span data-ttu-id="ed729-338">H.</span><span class="sxs-lookup"><span data-stu-id="ed729-338">H.</span></span> <span data-ttu-id="ed729-339">Supervisar el estado de una conversación en dos bases de datos de la misma instancia</span><span class="sxs-lookup"><span data-stu-id="ed729-339">Monitor the status of a conversation in two databases in the same instance</span></span>  
 <span data-ttu-id="ed729-340">En el ejemplo siguiente se muestra cómo supervisar una conversación concreta en la que los servicios de iniciador y destino están en bases de datos independientes de la misma instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed729-340">The following example shows how to monitor a specific conversation where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="ed729-341">En el ejemplo se usa **baseconnectionoptions** para especificar la instancia y la información de inicio de sesión, y dos cláusulas CONNECT TO para especificar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ed729-341">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span> <span data-ttu-id="ed729-342">Se especifica -SHOWEVENTS para que todos los eventos en tiempo de ejecución estén incluidos en los resultados del informe.</span><span class="sxs-lookup"><span data-stu-id="ed729-342">-SHOWEVENTS is specified so that all runtime events are included in the report output.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME -SHOWEVENTS   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="i-monitor-the-status-of-two-conversations-between-two-databases"></a><span data-ttu-id="ed729-343">I.</span><span class="sxs-lookup"><span data-stu-id="ed729-343">I.</span></span> <span data-ttu-id="ed729-344">Supervisar el estado de dos conversaciones entre dos bases de datos</span><span class="sxs-lookup"><span data-stu-id="ed729-344">Monitor the status of two conversations between two databases</span></span>  
 <span data-ttu-id="ed729-345">En el ejemplo siguiente se muestra cómo supervisar dos conversaciones en las que los servicios de iniciador y destino están en bases de datos independientes de la misma instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed729-345">The following example shows how to monitor two conversations where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="ed729-346">En el ejemplo se usa **baseconnectionoptions** para especificar la instancia y la información de inicio de sesión, y dos cláusulas CONNECT TO para especificar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ed729-346">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455   
-ID 9b293be9-226b-4e22-e169-1d2c2c15be86 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="j-monitor-the-status-of-all-conversations-between-two-databases"></a><span data-ttu-id="ed729-347">J.</span><span class="sxs-lookup"><span data-stu-id="ed729-347">J.</span></span> <span data-ttu-id="ed729-348">Supervisar el estado de todas las conversaciones entre dos bases de datos</span><span class="sxs-lookup"><span data-stu-id="ed729-348">Monitor the status of all conversations between two databases</span></span>  
 <span data-ttu-id="ed729-349">En el ejemplo siguiente se muestra cómo supervisar todas las conversaciones entre dos bases de datos de la misma instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed729-349">The following example shows how to monitor all the conversation between two databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="ed729-350">En el ejemplo se usa **baseconnectionoptions** para especificar la instancia y la información de inicio de sesión, y dos cláusulas CONNECT TO para especificar las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ed729-350">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-TIMEOUT 10 CONNECT TO -d InitiatorDatabase CONNECT TO   
-d TargetDatabase  
```  
  
### <a name="k-ignore-specific-errors"></a><span data-ttu-id="ed729-351">K.</span><span class="sxs-lookup"><span data-stu-id="ed729-351">K.</span></span> <span data-ttu-id="ed729-352">Omitir errores concretos</span><span class="sxs-lookup"><span data-stu-id="ed729-352">Ignore Specific Errors</span></span>  
 <span data-ttu-id="ed729-353">En el ejemplo siguiente se muestra cómo omitir errores conocidos (303 y 304) y cómo está configurada la activación en un sistema de prueba.</span><span class="sxs-lookup"><span data-stu-id="ed729-353">The following example shows how to ignore known errors (303 and 304) in how activation is currently configured in a test system.</span></span>  
  
```  
ssbdiagnose -IGNORE 303 -IGNORE 304 -E -d TestDatabase   
CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target   
ON CONTRACT TextContract  
```  
  
### <a name="l-redirecting-ssbdiagnose-xml-output"></a><span data-ttu-id="ed729-354">L.</span><span class="sxs-lookup"><span data-stu-id="ed729-354">L.</span></span> <span data-ttu-id="ed729-355">Redirigir la salida XML de ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="ed729-355">Redirecting ssbdiagnose XML Output</span></span>  
 <span data-ttu-id="ed729-356">En el ejemplo siguiente se muestra cómo solicitar que **ssbdiagnose** genere la salida en forma de archivo XML que se redirige a un archivo.</span><span class="sxs-lookup"><span data-stu-id="ed729-356">The following example shows how to request that **ssbdiagnose** generate its output as an XML file that is redirected to a file.</span></span> <span data-ttu-id="ed729-357">A continuación, el archivo TestDiag.xml puede abrirse en una aplicación diseñada para analizar o informar sobre los archivos XML de **ssbdiagnose** .</span><span class="sxs-lookup"><span data-stu-id="ed729-357">The TestDiag.xml file can then be opened by an application to analyze or report **ssbdiagnose** XML files.</span></span> <span data-ttu-id="ed729-358">O bien, se puede ver en un editor XML estándar, como XML Notepad.</span><span class="sxs-lookup"><span data-stu-id="ed729-358">Or, you can view it from a general XML editor such as XML Notepad.</span></span>  
  
```  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target > c:\MyDiagnostics\TestDiag.xml  
```  
  
### <a name="m-using-an-environment-variable"></a><span data-ttu-id="ed729-359">M.</span><span class="sxs-lookup"><span data-stu-id="ed729-359">M.</span></span> <span data-ttu-id="ed729-360">Usar una variable de entorno</span><span class="sxs-lookup"><span data-stu-id="ed729-360">Using an Environment Variable</span></span>  
 <span data-ttu-id="ed729-361">En el ejemplo siguiente se establece primero la variable de entorno SQLCMDSERVER para que contenga el nombre del servidor y, después, se ejecuta **ssbdiagnose** sin especificar **-S**.</span><span class="sxs-lookup"><span data-stu-id="ed729-361">The following example first sets the SQLCMDSERVER environment variable to hold the server name, and then runs **ssbdiagnose** without specifying **-S**.</span></span>  
  
```  
SET SQLCMDSERVER=MyComputer  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed729-362">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ed729-362">See Also</span></span>  
 <span data-ttu-id="ed729-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="ed729-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="ed729-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span></span>  
 <span data-ttu-id="ed729-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span></span>  
 <span data-ttu-id="ed729-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span></span>  
 <span data-ttu-id="ed729-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span></span>  
 <span data-ttu-id="ed729-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="ed729-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="ed729-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span></span>  
 <span data-ttu-id="ed729-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span></span>  
 <span data-ttu-id="ed729-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span></span>  
 <span data-ttu-id="ed729-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span></span>  
 <span data-ttu-id="ed729-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span></span>  
 <span data-ttu-id="ed729-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span></span>  
 <span data-ttu-id="ed729-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span></span>  
 <span data-ttu-id="ed729-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ed729-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="ed729-378">sys.conversation_groups &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ed729-378">sys.conversation_groups &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-conversation-groups-transact-sql)  
  
  
