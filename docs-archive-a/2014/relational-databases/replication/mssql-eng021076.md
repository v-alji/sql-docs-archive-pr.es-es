---
title: MSSQL_ENG021076 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021076 error
ms.assetid: 612e5c59-ba3e-49c3-a3df-56bac3d850a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4161428767ce78726436c0cf794f5250140d35b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745210"
---
# <a name="mssql_eng021076"></a><span data-ttu-id="ec7d9-102">MSSQL_ENG021076</span><span class="sxs-lookup"><span data-stu-id="ec7d9-102">MSSQL_ENG021076</span></span>
    
## <a name="message-details"></a><span data-ttu-id="ec7d9-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="ec7d9-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec7d9-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="ec7d9-104">Product Name</span></span>|<span data-ttu-id="ec7d9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec7d9-105">SQL Server</span></span>|  
|<span data-ttu-id="ec7d9-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="ec7d9-106">Event ID</span></span>|<span data-ttu-id="ec7d9-107">21076</span><span class="sxs-lookup"><span data-stu-id="ec7d9-107">21076</span></span>|  
|<span data-ttu-id="ec7d9-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="ec7d9-108">Event Source</span></span>|<span data-ttu-id="ec7d9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ec7d9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ec7d9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ec7d9-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="ec7d9-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="ec7d9-111">Symbolic Name</span></span>||  
|<span data-ttu-id="ec7d9-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="ec7d9-112">Message Text</span></span>|<span data-ttu-id="ec7d9-113">La instantánea inicial del artículo '%1!' aún no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ec7d9-113">The initial snapshot for article '%s' is not yet available.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ec7d9-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="ec7d9-114">Explanation</span></span>  
 <span data-ttu-id="ec7d9-115">El error MSSQL_ENG021076 puede producirse si el Agente de distribución se inicia antes de que el Agente de instantáneas haya terminado de generar la instantánea.</span><span class="sxs-lookup"><span data-stu-id="ec7d9-115">Error MSSQL_ENG021076 can be raised if the Distribution Agent is started before the Snapshot Agent has finished generating the snapshot.</span></span> <span data-ttu-id="ec7d9-116">El error se produce solo si la publicación contiene un único artículo.</span><span class="sxs-lookup"><span data-stu-id="ec7d9-116">This error is raised only if the publication contains a single article.</span></span> <span data-ttu-id="ec7d9-117">Si la publicación contiene más de un artículo, en su lugar se produce el error MSSQL_ENG021075.</span><span class="sxs-lookup"><span data-stu-id="ec7d9-117">If the publication contains more than one article, MSSQL_ENG021075 is raised instead.</span></span> <span data-ttu-id="ec7d9-118">Para más información, consulte [MSSQL_ENG021075](mssql-eng021075.md).</span><span class="sxs-lookup"><span data-stu-id="ec7d9-118">For more information, see [MSSQL_ENG021075](mssql-eng021075.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ec7d9-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="ec7d9-119">User Action</span></span>  
 <span data-ttu-id="ec7d9-120">Si el Agente de instantáneas para la publicación no se ha iniciado desde que se creó la suscripción, o si no se ha iniciado desde la última vez que decidió reinicializar la suscripción, inicie el Agente de instantáneas y deje que se complete antes de iniciar el Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="ec7d9-120">If the Snapshot Agent for the publication has not been started since the subscription was created, or if it has not been started since the last time you chose to reinitialize the subscription, start the Snapshot Agent and let it complete before starting the Distribution Agent.</span></span> <span data-ttu-id="ec7d9-121">Para obtener más información, vea [Crear y aplicar una instantánea](create-and-apply-the-snapshot.md).</span><span class="sxs-lookup"><span data-stu-id="ec7d9-121">For more information, see [Create and Apply the Snapshot](create-and-apply-the-snapshot.md).</span></span>  
  
 <span data-ttu-id="ec7d9-122">Si no finaliza el Agente de instantáneas, revise el historial del Agente de instantáneas para detectar posibles errores y soluciónelos.</span><span class="sxs-lookup"><span data-stu-id="ec7d9-122">If the Snapshot Agent does not complete, check the Snapshot Agent history for errors and address them.</span></span> <span data-ttu-id="ec7d9-123">Para obtener información sobre la visualización del estado y los errores en Monitor de replicación, vea [Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="ec7d9-123">For information about viewing agent status and error details in Replication Monitor, see [View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="ec7d9-124">Si el error persiste, aumente el registro del agente y especifique un archivo de salida para el registro.</span><span class="sxs-lookup"><span data-stu-id="ec7d9-124">If the error continues to occur, increase the logging of the agent and specify an output file for the log.</span></span> <span data-ttu-id="ec7d9-125">Dependiendo del contexto del error, esto puede proporcionar los pasos que conducen al error o a mensajes de error adicionales.</span><span class="sxs-lookup"><span data-stu-id="ec7d9-125">Depending on the context of the error, this could provide the steps leading up to the error and/or additional error messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec7d9-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec7d9-126">See Also</span></span>  
 [<span data-ttu-id="ec7d9-127">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="ec7d9-127">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
