---
title: MSSQL_REPL027183 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_REPL027183 error
ms.assetid: 52c271ac-1a0e-43d5-85d4-35886d1efd32
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4484318cd6ec6ff4f0b201be69dc9b7544dd2c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750693"
---
# <a name="mssql_repl027183"></a><span data-ttu-id="3b834-102">MSSQL_REPL027183</span><span class="sxs-lookup"><span data-stu-id="3b834-102">MSSQL_REPL027183</span></span>
    
## <a name="message-details"></a><span data-ttu-id="3b834-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="3b834-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b834-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="3b834-104">Product Name</span></span>|<span data-ttu-id="3b834-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3b834-105">SQL Server</span></span>|  
|<span data-ttu-id="3b834-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="3b834-106">Event ID</span></span>|<span data-ttu-id="3b834-107">27183</span><span class="sxs-lookup"><span data-stu-id="3b834-107">27183</span></span>|  
|<span data-ttu-id="3b834-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="3b834-108">Event Source</span></span>|<span data-ttu-id="3b834-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3b834-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3b834-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3b834-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="3b834-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="3b834-111">Symbolic Name</span></span>||  
|<span data-ttu-id="3b834-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="3b834-112">Message Text</span></span>|<span data-ttu-id="3b834-113">El proceso de mezcla no pudo enumerar los cambios en los artículos con filtros de fila con parámetros.</span><span class="sxs-lookup"><span data-stu-id="3b834-113">The merge process failed to enumerate changes in articles with parameterized row filters.</span></span> <span data-ttu-id="3b834-114">Si el error persiste, aumente el tiempo de espera de consulta, reduzca el período de retención de la publicación y mejore los índices en las tablas publicadas.</span><span class="sxs-lookup"><span data-stu-id="3b834-114">If this failure continues, increase the query timeout for this process, reduce the retention period for the publication, and improve indexes on published tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3b834-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="3b834-115">Explanation</span></span>  
 <span data-ttu-id="3b834-116">Este error se genera si se agota el tiempo de espera del Agente de mezcla durante el procesamiento de cambios en una publicación filtrada.</span><span class="sxs-lookup"><span data-stu-id="3b834-116">This error is raised if a Merge Agent timeout occurs while processing changes in a filtered publication.</span></span> <span data-ttu-id="3b834-117">Este tiempo de espera puede estar causado por uno de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="3b834-117">The timeout might be caused by one of the following issues:</span></span>  
  
-   <span data-ttu-id="3b834-118">No utilizar la optimización de particiones precalculadas.</span><span class="sxs-lookup"><span data-stu-id="3b834-118">Not using the precomputed partitions optimization.</span></span>  
  
-   <span data-ttu-id="3b834-119">Fragmentar índices en las columnas empleadas para filtrar.</span><span class="sxs-lookup"><span data-stu-id="3b834-119">Index fragmentation on columns used for filtering.</span></span>  
  
-   <span data-ttu-id="3b834-120">Tablas de metadatos de mezcla de gran tamaño, como **MSmerge_tombstone**, **MSmerge_contents**y **MSmerge_genhistory**.</span><span class="sxs-lookup"><span data-stu-id="3b834-120">Large merge metadata tables, such as **MSmerge_tombstone**, **MSmerge_contents**, and **MSmerge_genhistory**.</span></span>  
  
-   <span data-ttu-id="3b834-121">Tablas filtradas que no están combinadas en una clave única y filtros de combinación que incluyen un gran número de tablas.</span><span class="sxs-lookup"><span data-stu-id="3b834-121">Filtered tables that are not joined on a unique key and join filters that involve a large number of tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3b834-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="3b834-122">User Action</span></span>  
 <span data-ttu-id="3b834-123">Para resolver el problema:</span><span class="sxs-lookup"><span data-stu-id="3b834-123">To resolve the issue:</span></span>  
  
-   <span data-ttu-id="3b834-124">Aumente el valor del parámetro **-QueryTimeOut** para que el agente de mezcla permita que el procesamiento continúe mientras soluciona los problemas causantes del error.</span><span class="sxs-lookup"><span data-stu-id="3b834-124">Increase the value of the **-QueryTimeOut** parameter for the Merge Agent to allow processing to continue while you address the underlying issues causing the error.</span></span> <span data-ttu-id="3b834-125">Los parámetros del agente se pueden especificar en los perfiles del agente y en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="3b834-125">Agent parameters can be specified in agent profiles and on the command line.</span></span> <span data-ttu-id="3b834-126">Para más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="3b834-126">For more information, see:</span></span>  
  
    -   [<span data-ttu-id="3b834-127">Trabajar con perfiles del Agente de replicación</span><span class="sxs-lookup"><span data-stu-id="3b834-127">Work with Replication Agent Profiles</span></span>](agents/replication-agent-profiles.md)  
  
    -   [<span data-ttu-id="3b834-128">Ver y modificar parámetros del símbolo del sistema de los agentes de replicación &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3b834-128">View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;</span></span>](agents/view-and-modify-replication-agent-command-prompt-parameters.md)  
  
    -   <span data-ttu-id="3b834-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="3b834-129">[Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
-   <span data-ttu-id="3b834-130">Si es posible, utilice la optimización de particiones precalculadas.</span><span class="sxs-lookup"><span data-stu-id="3b834-130">Use the precomputed partitions optimization if possible.</span></span> <span data-ttu-id="3b834-131">Esta optimización se utiliza de forma predeterminada si se cumplen una serie de requisitos de publicación.</span><span class="sxs-lookup"><span data-stu-id="3b834-131">This optimization is used by default if a number of publication requirements are met.</span></span> <span data-ttu-id="3b834-132">Para obtener más información sobre estos requisitos, vea [Optimizar el rendimiento de los filtros con parámetros con particiones calculadas previamente](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span><span class="sxs-lookup"><span data-stu-id="3b834-132">For more information about these requirements, see [Optimize Parameterized Filter Performance with Precomputed Partitions](merge/parameterized-filters-optimize-for-precomputed-partitions.md).</span></span> <span data-ttu-id="3b834-133">Si la publicación no reúne dichos requisitos, considere la posibilidad de volver a diseñar la publicación.</span><span class="sxs-lookup"><span data-stu-id="3b834-133">If the publication does not meet these requirements, consider redesigning the publication.</span></span>  
  
-   <span data-ttu-id="3b834-134">Especifique el valor más bajo posible para el período de retención de la publicación, ya que la replicación no puede limpiar los metadatos de las bases de datos de suscripciones y publicaciones hasta que se alcance el período de retención.</span><span class="sxs-lookup"><span data-stu-id="3b834-134">Specify the lowest setting possible for the publication retention period, because replication cannot clean up metadata in the publication and subscription databases until the retention period is reached.</span></span> <span data-ttu-id="3b834-135">Para más información, consulte [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="3b834-135">For more information, see [Subscription Expiration and Deactivation](subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="3b834-136">Como parte del mantenimiento de la replicación de mezcla, compruebe ocasionalmente el crecimiento de las tablas del sistema asociadas con la replicación de mezcla: **MSmerge_contents**, **MSmerge_genhistory**, **MSmerge_tombstone**, **MSmerge_current_partition_mappings**y **MSmerge_past_partition_mappings**.</span><span class="sxs-lookup"><span data-stu-id="3b834-136">As part of maintenance for merge replication, occasionally check the growth of the system tables associated with merge replication: **MSmerge_contents**, **MSmerge_genhistory**, and **MSmerge_tombstone**, **MSmerge_current_partition_mappings**, and **MSmerge_past_partition_mappings**.</span></span> <span data-ttu-id="3b834-137">Vuelva a indizar estas tablas periódicamente.</span><span class="sxs-lookup"><span data-stu-id="3b834-137">Periodically re-index these tables.</span></span> <span data-ttu-id="3b834-138">Para obtener más información, vea [Reorganizar y volver a generar índices](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="3b834-138">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="3b834-139">Asegúrese de que las columnas utilizadas para filtrar están correctamente indizadas y vuelva a generar dichos índices en caso necesario.</span><span class="sxs-lookup"><span data-stu-id="3b834-139">Ensure that columns used for filtering are properly indexed and rebuild such indexes if necessary.</span></span> <span data-ttu-id="3b834-140">Para obtener más información, vea [Reorganizar y volver a generar índices](../indexes/indexes.md).</span><span class="sxs-lookup"><span data-stu-id="3b834-140">For more information, see [Reorganize and Rebuild Indexes](../indexes/indexes.md).</span></span>  
  
-   <span data-ttu-id="3b834-141">Establezca la propiedad **join_unique_key** para los filtros combinados basados en columnas únicas.</span><span class="sxs-lookup"><span data-stu-id="3b834-141">Set the **join_unique_key** property for join filters that are based on unique columns.</span></span> <span data-ttu-id="3b834-142">Para obtener más información, consulte [Join Filters](merge/join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="3b834-142">For more information, see [Join Filters](merge/join-filters.md).</span></span>  
  
-   <span data-ttu-id="3b834-143">Limite el número de tablas de la jerarquía del filtro de combinación.</span><span class="sxs-lookup"><span data-stu-id="3b834-143">Limit the number of tables in the join filter hierarchy.</span></span> <span data-ttu-id="3b834-144">Si va a generar filtros de combinación de cinco tablas o más, considere otras soluciones, como no filtrar tablas pequeñas, que no estén sometidas a cambios o que sean principalmente tablas de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3b834-144">If you are generating join filters of five or more tables, consider other solutions: do not filter tables that are small, not subject to change, or are primarily lookup tables.</span></span> <span data-ttu-id="3b834-145">Utilice filtros combinados solo entre tablas que deben particionarse entre las suscripciones.</span><span class="sxs-lookup"><span data-stu-id="3b834-145">Use join filters only between tables that must be partitioned among subscriptions.</span></span>  
  
-   <span data-ttu-id="3b834-146">Realice un número reducido de cambios en las tablas filtradas entre sincronizaciones o ejecute el Agente de mezcla con mayor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="3b834-146">Make a smaller number of changes on filtered tables between synchronizations, or run the Merge Agent more frequently.</span></span> <span data-ttu-id="3b834-147">Para obtener más información acerca de la configuración de las programaciones de sincronización, vea [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span><span class="sxs-lookup"><span data-stu-id="3b834-147">For more information about setting synchronization schedules, see [Specify Synchronization Schedules](specify-synchronization-schedules.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b834-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b834-148">See Also</span></span>  
 [<span data-ttu-id="3b834-149">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="3b834-149">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
