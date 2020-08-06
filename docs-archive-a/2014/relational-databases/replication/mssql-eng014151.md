---
title: MSSQL_ENG014151 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014151 error
ms.assetid: 54b45e70-46b3-4c7a-a5bf-06f6dd028ceb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2796451f6f681cfb0ce529ed44a946c34135649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662822"
---
# <a name="mssql_eng014151"></a><span data-ttu-id="26888-102">MSSQL_ENG014151</span><span class="sxs-lookup"><span data-stu-id="26888-102">MSSQL_ENG014151</span></span>
    
## <a name="message-details"></a><span data-ttu-id="26888-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="26888-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26888-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="26888-104">Product Name</span></span>|<span data-ttu-id="26888-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="26888-105">SQL Server</span></span>|  
|<span data-ttu-id="26888-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="26888-106">Event ID</span></span>|<span data-ttu-id="26888-107">14151</span><span class="sxs-lookup"><span data-stu-id="26888-107">14151</span></span>|  
|<span data-ttu-id="26888-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="26888-108">Event Source</span></span>|<span data-ttu-id="26888-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="26888-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="26888-110">Componente</span><span class="sxs-lookup"><span data-stu-id="26888-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="26888-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="26888-111">Symbolic Name</span></span>||  
|<span data-ttu-id="26888-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="26888-112">Message Text</span></span>|<span data-ttu-id="26888-113">Replicación-%s: error en el agente %s.</span><span class="sxs-lookup"><span data-stu-id="26888-113">Replication-%s: agent %s failed.</span></span> <span data-ttu-id="26888-114">%s</span><span class="sxs-lookup"><span data-stu-id="26888-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="26888-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="26888-115">Explanation</span></span>  
 <span data-ttu-id="26888-116">Este error se produce en caso de fallo del agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="26888-116">This error is raised for any replication agent failure.</span></span> <span data-ttu-id="26888-117">El texto al final del mensaje depende del contexto del error.</span><span class="sxs-lookup"><span data-stu-id="26888-117">The text at the end of the message depends on the context of the failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="26888-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="26888-118">User Action</span></span>  
 <span data-ttu-id="26888-119">Este error se puede producir en una serie de situaciones; aplique las siguientes soluciones según corresponda:</span><span class="sxs-lookup"><span data-stu-id="26888-119">This error can occur in a number of situations; use the following approaches as necessary:</span></span>  
  
-   <span data-ttu-id="26888-120">Reinicie el agente en el que se ha producido el error para ver si se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="26888-120">Restart the failed agent to see if it will now run without failures.</span></span> <span data-ttu-id="26888-121">Para obtener más información, vea [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) y [Conceptos de los ejecutables del Agente de replicación](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="26888-121">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="26888-122">Compruebe el historial del agente y el historial de trabajos para ver otros errores que se hayan producido aproximadamente a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="26888-122">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="26888-123">Para obtener información sobre la visualización del estado y los errores en Monitor de replicación, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="26888-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
-   <span data-ttu-id="26888-124">Compruebe que la conectividad básica funciona entre los equipos a los que el agente tiene acceso y, a continuación, conecte a cada equipo con una herramienta como [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span><span class="sxs-lookup"><span data-stu-id="26888-124">Verify that basic connectivity is working between the computers accessed by the agent, and then connect to each computer with a utility like the [sqlcmd Utility](../../tools/sqlcmd-utility.md).</span></span> <span data-ttu-id="26888-125">Para conectar, utilice la misma cuenta con la que el agente realiza las conexiones.</span><span class="sxs-lookup"><span data-stu-id="26888-125">When connecting, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="26888-126">Para obtener más información acerca de los permisos que necesita cada cuenta de agente, vea [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="26888-126">For more information about the permissions required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="26888-127">Si se producen errores al crear o aplicar una instantánea, compruebe los archivos del directorio de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="26888-127">If the error occurs while creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="26888-128">Si el error persiste, aumente el registro del agente y especifique un archivo de salida para el registro.</span><span class="sxs-lookup"><span data-stu-id="26888-128">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="26888-129">Dependiendo del contexto del error, esto puede proporcionar los pasos que conducen al error o a mensajes de error adicionales.</span><span class="sxs-lookup"><span data-stu-id="26888-129">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26888-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="26888-130">See Also</span></span>  
 <span data-ttu-id="26888-131">[Administración del Agente de replicación](agents/replication-agent-administration.md) </span><span class="sxs-lookup"><span data-stu-id="26888-131">[Replication Agent Administration](agents/replication-agent-administration.md) </span></span>  
 <span data-ttu-id="26888-132">[Referencia de errores y eventos &#40;replicación&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="26888-132">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 <span data-ttu-id="26888-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="26888-133">[Replication Distribution Agent](agents/replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="26888-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="26888-134">[Replication Log Reader Agent](agents/replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="26888-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="26888-135">[Replication Merge Agent](agents/replication-merge-agent.md) </span></span>  
 <span data-ttu-id="26888-136">[Agente de lectura de cola de replicación](agents/replication-queue-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="26888-136">[Replication Queue Reader Agent](agents/replication-queue-reader-agent.md) </span></span>  
 [<span data-ttu-id="26888-137">Replication Snapshot Agent</span><span class="sxs-lookup"><span data-stu-id="26888-137">Replication Snapshot Agent</span></span>](agents/replication-snapshot-agent.md)  
  
  
