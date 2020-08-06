---
title: MSSQL_REPL027056 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027056 error
ms.assetid: 92d62f3c-b8ae-482e-a348-2e9a8ee9786e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fb130321ec54c39559d52e493cc8f3424172fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748061"
---
# <a name="mssql_repl027056"></a><span data-ttu-id="7d45f-102">MSSQL_REPL027056</span><span class="sxs-lookup"><span data-stu-id="7d45f-102">MSSQL_REPL027056</span></span>
    
## <a name="message-details"></a><span data-ttu-id="7d45f-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="7d45f-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d45f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7d45f-104">Product Name</span></span>|<span data-ttu-id="7d45f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d45f-105">SQL Server</span></span>|  
|<span data-ttu-id="7d45f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7d45f-106">Event ID</span></span>|<span data-ttu-id="7d45f-107">27056</span><span class="sxs-lookup"><span data-stu-id="7d45f-107">27056</span></span>|  
|<span data-ttu-id="7d45f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7d45f-108">Event Source</span></span>|<span data-ttu-id="7d45f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7d45f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7d45f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7d45f-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="7d45f-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7d45f-111">Symbolic Name</span></span>||  
|<span data-ttu-id="7d45f-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7d45f-112">Message Text</span></span>|<span data-ttu-id="7d45f-113">El proceso de mezcla no pudo cambiar el historial de generación en '%1'.</span><span class="sxs-lookup"><span data-stu-id="7d45f-113">The merge process was unable to change generation history at the '%1'.</span></span> <span data-ttu-id="7d45f-114">Para solucionar el problema, reinicie la sincronización con registro de historial detallado y especifique un archivo de salida para escribir en él.</span><span class="sxs-lookup"><span data-stu-id="7d45f-114">When troubleshooting, restart the synchronization with verbose history logging and specify an output file to which to write.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d45f-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="7d45f-115">Explanation</span></span>  
 <span data-ttu-id="7d45f-116">Este error suele ser el resultado de la contención de las tablas del sistema de replicación de mezcla, que han aumentado de tamaño de forma excesiva.</span><span class="sxs-lookup"><span data-stu-id="7d45f-116">This error is typically raised as a result of contention in merge replication system tables that have grown excessively large.</span></span> <span data-ttu-id="7d45f-117">El tamaño excesivo de las tablas del sistema se debe generalmente a un período prolongado de retención de la publicación, ya que los metadatos se deben almacenar en estas tablas hasta que se alcanza el período de retención.</span><span class="sxs-lookup"><span data-stu-id="7d45f-117">Large system tables are typically caused by a long publication retention period, because metadata must be stored in these tables until the retention period is reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d45f-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7d45f-118">User Action</span></span>  
 <span data-ttu-id="7d45f-119">**Para resolver el problema:**</span><span class="sxs-lookup"><span data-stu-id="7d45f-119">**To resolve the issue:**</span></span>  
  
1.  <span data-ttu-id="7d45f-120">Reduzca el valor de los parámetros -**DownloadGenerationsPerBatch** y **-UploadGenerationsPerBatch** del agente de mezcla para permitir que el procesamiento continúe mientras soluciona el problema subyacente que causa el error.</span><span class="sxs-lookup"><span data-stu-id="7d45f-120">Decrease the value of the -**DownloadGenerationsPerBatch** and **-UploadGenerationsPerBatch** parameters for the Merge Agent to allow processing to continue while you address the underlying issue causing the error.</span></span> <span data-ttu-id="7d45f-121">Los parámetros del agente se pueden especificar en los perfiles del agente y en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7d45f-121">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="7d45f-122">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="7d45f-122">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="7d45f-123">Trabajar con perfiles del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="7d45f-123">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="7d45f-124">Ver y modificar parámetros del símbolo del sistema de los agentes de replicación &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7d45f-124">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="7d45f-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="7d45f-125">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
2.  <span data-ttu-id="7d45f-126">Especifique el menor valor posible para el período de retención de la publicación.</span><span class="sxs-lookup"><span data-stu-id="7d45f-126">Specify the lowest setting possible for the publication retention period.</span></span> <span data-ttu-id="7d45f-127">Para más información, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="7d45f-127">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
3.  <span data-ttu-id="7d45f-128">Como parte del mantenimiento de la replicación de mezcla, compruebe ocasionalmente el crecimiento de las tablas del sistema asociadas con la replicación de mezcla: **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**y **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="7d45f-128">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="7d45f-129">Vuelva a indizar estas tablas periódicamente.</span><span class="sxs-lookup"><span data-stu-id="7d45f-129">Periodically re-index these tables.</span></span> <span data-ttu-id="7d45f-130">Para obtener más información, vea [Reorganizar y volver a generar índices](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="7d45f-130">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d45f-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d45f-131">See Also</span></span>  
 [<span data-ttu-id="7d45f-132">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="7d45f-132">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
