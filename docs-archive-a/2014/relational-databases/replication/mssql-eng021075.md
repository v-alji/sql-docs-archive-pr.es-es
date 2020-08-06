---
title: MSSQL_ENG021075 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021075 error
ms.assetid: c8c29543-d1f6-49d5-b6c8-e8c3aa373090
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 20f2428038326681f5f8eb877e5c3017ced30f00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675283"
---
# <a name="mssql_eng021075"></a><span data-ttu-id="74636-102">MSSQL_ENG021075</span><span class="sxs-lookup"><span data-stu-id="74636-102">MSSQL_ENG021075</span></span>
    
## <a name="message-details"></a><span data-ttu-id="74636-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="74636-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74636-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="74636-104">Product Name</span></span>|<span data-ttu-id="74636-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="74636-105">SQL Server</span></span>|  
|<span data-ttu-id="74636-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="74636-106">Event ID</span></span>|<span data-ttu-id="74636-107">21075</span><span class="sxs-lookup"><span data-stu-id="74636-107">21075</span></span>|  
|<span data-ttu-id="74636-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="74636-108">Event Source</span></span>|<span data-ttu-id="74636-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="74636-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="74636-110">Componente</span><span class="sxs-lookup"><span data-stu-id="74636-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="74636-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="74636-111">Symbolic Name</span></span>||  
|<span data-ttu-id="74636-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="74636-112">Message Text</span></span>|<span data-ttu-id="74636-113">La instantánea inicial de la publicación '%1!' aún no está disponible.</span><span class="sxs-lookup"><span data-stu-id="74636-113">The initial snapshot for publication '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="74636-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="74636-114">Explanation</span></span>  
 <span data-ttu-id="74636-115">El error MSSQL_ENG021075 aparece cuando se inicia el Agente de distribución o de mezcla antes de que el Agente de instantáneas termine de generar la instantánea.</span><span class="sxs-lookup"><span data-stu-id="74636-115">Error MSSQL_ENG021075 is raised if the Distribution Agent or Merge Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74636-116">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="74636-116">User Action</span></span>  
 <span data-ttu-id="74636-117">Si no se ha iniciado el Agente de instantáneas para la publicación desde que se creó la suscripción o desde la última vez que eligió reinicializar la suscripción, inícielo y espere a que termine antes de iniciar el Agente de distribución o de mezcla.</span><span class="sxs-lookup"><span data-stu-id="74636-117">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent or Merge Agent.</span></span> <span data-ttu-id="74636-118">Para obtener más información, vea [Crear y aplicar una instantánea](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="74636-118">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="74636-119">Si no finaliza el Agente de instantáneas, revise el historial del Agente de instantáneas para detectar posibles errores y soluciónelos.</span><span class="sxs-lookup"><span data-stu-id="74636-119">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="74636-120">Para obtener información sobre la visualización del estado y los errores en Monitor de replicación, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="74636-120">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="74636-121">Si el error persiste, aumente el registro del agente y especifique un archivo de salida para el registro.</span><span class="sxs-lookup"><span data-stu-id="74636-121">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="74636-122">Dependiendo del contexto del error, esto puede proporcionar los pasos que conducen al error o a mensajes de error adicionales.</span><span class="sxs-lookup"><span data-stu-id="74636-122">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74636-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="74636-123">See Also</span></span>  
 [<span data-ttu-id="74636-124">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="74636-124">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
