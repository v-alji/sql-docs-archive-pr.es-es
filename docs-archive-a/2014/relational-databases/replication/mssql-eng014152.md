---
title: MSSQL_ENG014152 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014152 error
ms.assetid: 4215e2b1-cd30-441f-9671-9afc742adf6e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 615b9cf2996653d86c44d6e43a83e01e8287b110
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671494"
---
# <a name="mssql_eng014152"></a><span data-ttu-id="b4ac9-102">MSSQL_ENG014152</span><span class="sxs-lookup"><span data-stu-id="b4ac9-102">MSSQL_ENG014152</span></span>
    
## <a name="message-details"></a><span data-ttu-id="b4ac9-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="b4ac9-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4ac9-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b4ac9-104">Product Name</span></span>|<span data-ttu-id="b4ac9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b4ac9-105">SQL Server</span></span>|  
|<span data-ttu-id="b4ac9-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b4ac9-106">Event ID</span></span>|<span data-ttu-id="b4ac9-107">14152</span><span class="sxs-lookup"><span data-stu-id="b4ac9-107">14152</span></span>|  
|<span data-ttu-id="b4ac9-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b4ac9-108">Event Source</span></span>|<span data-ttu-id="b4ac9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b4ac9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b4ac9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b4ac9-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="b4ac9-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b4ac9-111">Symbolic Name</span></span>||  
|<span data-ttu-id="b4ac9-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b4ac9-112">Message Text</span></span>|<span data-ttu-id="b4ac9-113">Replicación-%s: el agente %s está programado para reintentar.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-113">Replication-%s: agent %s scheduled for retry.</span></span> <span data-ttu-id="b4ac9-114">%s</span><span class="sxs-lookup"><span data-stu-id="b4ac9-114">%s</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b4ac9-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="b4ac9-115">Explanation</span></span>  
 <span data-ttu-id="b4ac9-116">Se ha programado el agente de replicación especificado para volver a intentar la operación solicitada.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-116">The specified replication agent has been scheduled to retry the requested operation.</span></span> <span data-ttu-id="b4ac9-117">El proceso continúa intentándolo hasta que se alcanza la cantidad máxima configurada de reintentos del paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-117">The process continues to retry until it reaches the configured maximum number of retry attempts for the job step.</span></span>  
  
 <span data-ttu-id="b4ac9-118">Normalmente, un reintento tiene lugar debido a uno de los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="b4ac9-118">A retry typically occurs because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="b4ac9-119">Se supera el valor **QueryTimeout** .</span><span class="sxs-lookup"><span data-stu-id="b4ac9-119">The **QueryTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="b4ac9-120">Se supera el valor **LoginTimeout** .</span><span class="sxs-lookup"><span data-stu-id="b4ac9-120">The **LoginTimeout** value is exceeded.</span></span>  
  
-   <span data-ttu-id="b4ac9-121">El proceso de replicación fue objeto del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-121">The replication process was chosen as a deadlock victim.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b4ac9-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b4ac9-122">User Action</span></span>  
 <span data-ttu-id="b4ac9-123">Si el mensaje de reintento no es frecuente, no es necesaria ninguna acción por parte del usuario.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-123">If the retry message is infrequent, no user action is required.</span></span>  
  
 <span data-ttu-id="b4ac9-124">Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) para ver la configuración actual de la cantidad máxima de reintentos del paso **Ejecutar agente** en el agente de replicación especificado.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-124">Use [sp_help_jobstep](/sql/relational-databases/system-stored-procedures/sp-help-jobstep-transact-sql) to view the current setting for the maximum number of times the **Run agent** step for the specified replication agent will retry.</span></span> <span data-ttu-id="b4ac9-125">Puede usar el **@retry_attempts** parámetro de la [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) procedimiento almacenado para ajustar el número de veces que se reintenta un paso de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-125">You can use the **@retry_attempts** parameter of the [sp_update_jobstep](/sql/relational-databases/system-stored-procedures/sp-update-jobstep-transact-sql) stored procedure to adjust the number of times a job step retries.</span></span>  
  
 <span data-ttu-id="b4ac9-126">Si el mensaje de reintento se repite con frecuencia, solucione el problema al que se refiere el mensaje que está causando el reintento.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-126">If the retry message recurs frequently, troubleshoot the issue based on the message that is causing the retry.</span></span> <span data-ttu-id="b4ac9-127">Busque en el historial del agente los mensajes que indiquen los motivos por los que se tuvo que programar el reintento.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-127">Check the agent's history for messages that indicate why the retry had to be scheduled.</span></span> <span data-ttu-id="b4ac9-128">En algunos casos tendrá que habilitar un registro más detallado para el agente de replicación.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-128">In some cases you may have to enable more detailed logging for your replication agent.</span></span> <span data-ttu-id="b4ac9-129">Para obtener más información acerca de la configuración del registro para replicación, vea el artículo [312292](https://support.microsoft.com/kb/312292)de Microsoft Knowledge Base.</span><span class="sxs-lookup"><span data-stu-id="b4ac9-129">For more information about how to configure logging for replication, see the Microsoft Knowledge Base article [312292](https://support.microsoft.com/kb/312292).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ac9-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4ac9-130">See Also</span></span>  
 [<span data-ttu-id="b4ac9-131">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="b4ac9-131">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
