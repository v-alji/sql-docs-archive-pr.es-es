---
title: MSSQL_ENG014164 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014164 error
ms.assetid: cd81b601-2ec3-4358-ad58-c2655496e6a1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ddf88cbdfd25d77ca3f2eadf4176309d02a084e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87669616"
---
# <a name="mssql_eng014164"></a><span data-ttu-id="f833b-102">MSSQL_ENG014164</span><span class="sxs-lookup"><span data-stu-id="f833b-102">MSSQL_ENG014164</span></span>
    
## <a name="message-details"></a><span data-ttu-id="f833b-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="f833b-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f833b-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="f833b-104">Product Name</span></span>|<span data-ttu-id="f833b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f833b-105">SQL Server</span></span>|  
|<span data-ttu-id="f833b-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="f833b-106">Event ID</span></span>|<span data-ttu-id="f833b-107">14164</span><span class="sxs-lookup"><span data-stu-id="f833b-107">14164</span></span>|  
|<span data-ttu-id="f833b-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="f833b-108">Event Source</span></span>|<span data-ttu-id="f833b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f833b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f833b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f833b-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="f833b-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f833b-111">Symbolic Name</span></span>||  
|<span data-ttu-id="f833b-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f833b-112">Message Text</span></span>|<span data-ttu-id="f833b-113">Se ha establecido el umbral [%s:%s] para la publicación [%s].</span><span class="sxs-lookup"><span data-stu-id="f833b-113">The threshold [%s:%s] for the publication [%s] has been set.</span></span> <span data-ttu-id="f833b-114">Asegúrese de que el agente de mezcla se está ejecutando y cumple con el requisito esperado.</span><span class="sxs-lookup"><span data-stu-id="f833b-114">Please make sure that the merge agent is running and can match the expected requirement.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f833b-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f833b-115">Explanation</span></span>  
 <span data-ttu-id="f833b-116">La replicación le permite habilitar advertencias para varias condiciones.</span><span class="sxs-lookup"><span data-stu-id="f833b-116">Replication lets you enable warnings for several conditions.</span></span> <span data-ttu-id="f833b-117">Incluye el error al procesar un número suficiente de filas al sincronizar cambios entre un suscriptor y un publicador de mezcla.</span><span class="sxs-lookup"><span data-stu-id="f833b-117">This includes failure to process a sufficient number of rows when synchronizing changes between a merge Publisher and Subscriber.</span></span> <span data-ttu-id="f833b-118">Se pueden especificar diferentes horas para las conexiones LAN y las de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="f833b-118">Different times can be specified for LAN connections and dial-up connections.</span></span>  
  
 <span data-ttu-id="f833b-119">Al habilitar una advertencia mediante el Monitor de replicación o [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), especifica un umbral que determina cuándo se desencadena una advertencia.</span><span class="sxs-lookup"><span data-stu-id="f833b-119">When you enable a warning by using Replication Monitor or [sp_replmonitorchangepublicationthreshold](/sql/relational-databases/system-stored-procedures/sp-replmonitorchangepublicationthreshold-transact-sql), you specify a threshold that determines when a warning is triggered.</span></span> <span data-ttu-id="f833b-120">Cuando se alcanza o se supera un umbral, aparece una advertencia en el Monitor de replicación y se escribe un evento en el registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="f833b-120">When that threshold is met or exceeded, a warning is displayed in Replication Monitor, and an event is written to the Windows event log.</span></span> <span data-ttu-id="f833b-121">Alcanzar un umbral también puede desencadenar una alerta del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f833b-121">Reaching a threshold can also trigger a SQL Server Agent alert.</span></span> <span data-ttu-id="f833b-122">Para obtener más información, vea [Establecer umbrales y advertencias en el Monitor de replicación](monitor/set-thresholds-and-warnings-in-replication-monitor.md) y [Cómo supervisar la replicación mediante programación (programación con RMO)](monitoring-replication.md).</span><span class="sxs-lookup"><span data-stu-id="f833b-122">For more information, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md) and [Programmatically Monitor Replication](monitoring-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f833b-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f833b-123">User Action</span></span>  
 <span data-ttu-id="f833b-124">Si una suscripción no cumple un umbral de procesamiento de filas, debe determinar si hay algún problema de rendimiento en el sistema o si debe ajustarse el umbral.</span><span class="sxs-lookup"><span data-stu-id="f833b-124">If a subscription is not meeting a row processing threshold, you must determine whether there is a performance issue with the system or whether the threshold should be adjusted.</span></span> <span data-ttu-id="f833b-125">Una vez configurada la replicación, desarrolle una línea base de rendimiento que le permitirá determinar el comportamiento de la replicación con la carga de trabajo habitual de las aplicaciones y la topología.</span><span class="sxs-lookup"><span data-stu-id="f833b-125">After you configure replication, develop a performance baseline that will let you determine how replication behaves with a workload that is typical for your applications and topology.</span></span> <span data-ttu-id="f833b-126">Incluya el número de filas procesadas en esta línea base para poder establecer un valor adecuado para el umbral.</span><span class="sxs-lookup"><span data-stu-id="f833b-126">Include number of rows processed in this baseline so that you can set an appropriate value for the threshold.</span></span>  
  
 <span data-ttu-id="f833b-127">Si el valor del umbral es adecuado, pero está siendo superado, debe determinar dónde se encuentra el cuello de botella en el sistema.</span><span class="sxs-lookup"><span data-stu-id="f833b-127">If the threshold value is appropriate, but it is being exceeded, you must determine where the performance bottleneck is in the system.</span></span> <span data-ttu-id="f833b-128">Para obtener más información acerca de cómo supervisar y solucionar problemas relacionados con el rendimiento de replicación, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f833b-128">For more information about how to monitor and troubleshoot replication performance, see the following topics:</span></span>  
  
-   <span data-ttu-id="f833b-129">[Supervisar el rendimiento con el Monitor de replicación](monitor/monitor-performance-with-replication-monitor.md), especialmente la sección "Ver detalles del rendimiento de la sincronización en la replicación de mezcla"</span><span class="sxs-lookup"><span data-stu-id="f833b-129">[Monitor Performance with Replication Monitor](monitor/monitor-performance-with-replication-monitor.md) (especially the section "Viewing Detailed Synchronization Performance for Merge Replication")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f833b-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f833b-130">See Also</span></span>  
 [<span data-ttu-id="f833b-131">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="f833b-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
