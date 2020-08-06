---
title: MSSQL_ENG020557 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020557 error
ms.assetid: c43c6952-5b60-4347-b881-11a0004dce24
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 45c24d453eb95abaa967ae65ceb5934b7dee969e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677587"
---
# <a name="mssql_eng020557"></a><span data-ttu-id="54f3c-102">MSSQL_ENG020557</span><span class="sxs-lookup"><span data-stu-id="54f3c-102">MSSQL_ENG020557</span></span>
    
## <a name="message-details"></a><span data-ttu-id="54f3c-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="54f3c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="54f3c-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="54f3c-104">Product Name</span></span>|<span data-ttu-id="54f3c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="54f3c-105">SQL Server</span></span>|  
|<span data-ttu-id="54f3c-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="54f3c-106">Event ID</span></span>|<span data-ttu-id="54f3c-107">20557</span><span class="sxs-lookup"><span data-stu-id="54f3c-107">20557</span></span>|  
|<span data-ttu-id="54f3c-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="54f3c-108">Event Source</span></span>|<span data-ttu-id="54f3c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="54f3c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="54f3c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="54f3c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="54f3c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="54f3c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="54f3c-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="54f3c-112">Message Text</span></span>|<span data-ttu-id="54f3c-113">Cierre del agente.</span><span class="sxs-lookup"><span data-stu-id="54f3c-113">Agent shutdown.</span></span> <span data-ttu-id="54f3c-114">Para obtener más información, vea el trabajo '%s' en el historial de trabajos del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="54f3c-114">For more information, see the SQL Server Agent job history for job '%s'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="54f3c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="54f3c-115">Explanation</span></span>  
 <span data-ttu-id="54f3c-116">El agente de replicación se ha cerrado sin escribir un motivo en la tabla del historial adecuada o el agente se ha cerrado durante un proceso.</span><span class="sxs-lookup"><span data-stu-id="54f3c-116">A replication agent has shut down without writing a reason to the appropriate history table, or the agent was shut down while in the middle of a process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="54f3c-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="54f3c-117">User Action</span></span>  
  
-   <span data-ttu-id="54f3c-118">Reinicie el agente para ver si se ejecuta ahora correctamente.</span><span class="sxs-lookup"><span data-stu-id="54f3c-118">Restart the agent to see whether it will now run without failures.</span></span> <span data-ttu-id="54f3c-119">Para obtener más información, vea [Iniciar y detener un agente de replicación &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) y [Conceptos de los ejecutables del Agente de replicación](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="54f3c-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="54f3c-120">Compruebe el historial del agente y el historial de trabajos para ver otros errores que se hayan producido aproximadamente a la misma hora.</span><span class="sxs-lookup"><span data-stu-id="54f3c-120">Check the agent history and job history for other errors that occurred around the same time.</span></span> <span data-ttu-id="54f3c-121">Para obtener información sobre cómo ver el estado y los errores en Monitor de replicación, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="54f3c-121">For information about how to view agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>
-   <span data-ttu-id="54f3c-122">Compruebe que la conectividad básica funciona entre los equipos a los que el agente tiene acceso y, a continuación, conéctese a cada equipo con una utilidad como **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="54f3c-122">Verify that basic connectivity is working between the computers that are accessed by the agent, and then connect to each computer by using a utility, such as the **sqlcmd** utility.</span></span> <span data-ttu-id="54f3c-123">Para conectar, utilice la misma cuenta con la que el agente realiza las conexiones.</span><span class="sxs-lookup"><span data-stu-id="54f3c-123">When you connect, use the same account under which the agent makes connections.</span></span> <span data-ttu-id="54f3c-124">Para obtener más información acerca de los permisos que necesita cada cuenta de agente, vea [Replication Agent Security Model](security/replication-agent-security-model.md).</span><span class="sxs-lookup"><span data-stu-id="54f3c-124">For more information about the permissions that are required by each agent account, see [Replication Agent Security Model](security/replication-agent-security-model.md).</span></span>  
  
-   <span data-ttu-id="54f3c-125">Si se producen errores al crear o aplicar una instantánea, compruebe los archivos del directorio de la instantánea.</span><span class="sxs-lookup"><span data-stu-id="54f3c-125">If the error occurs while you are creating or applying a snapshot, check the files in the snapshot directory for errors.</span></span>  
  
-   <span data-ttu-id="54f3c-126">Si el error persiste, aumente el registro del agente y especifique un archivo de salida para el registro.</span><span class="sxs-lookup"><span data-stu-id="54f3c-126">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="54f3c-127">Dependiendo del contexto del error, esto puede proporcionar los pasos que conducen al error y a mensajes de error adicionales.</span><span class="sxs-lookup"><span data-stu-id="54f3c-127">Depending on the context of the error, this could provide the steps leading up to the error and additional error messages.</span></span> <span data-ttu-id="54f3c-128">Para obtener más información acerca de la configuración del registro para replicación, vea el artículo [312292](https://support.microsoft.com/kb/312292)de Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="54f3c-128">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f3c-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54f3c-129">See Also</span></span>  
 [<span data-ttu-id="54f3c-130">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="54f3c-130">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
