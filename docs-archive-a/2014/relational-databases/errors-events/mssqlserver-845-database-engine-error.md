---
title: MSSQLSERVER_845 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 845 (Database Engine error)
ms.assetid: 8fff6ad4-234c-44be-b123-e25d5e1cd63e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 24bfb8b3758d0656dad96e4af4ed3b94aa51e07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671563"
---
# <a name="mssqlserver_845"></a><span data-ttu-id="575e2-102">MSSQLSERVER_845</span><span class="sxs-lookup"><span data-stu-id="575e2-102">MSSQLSERVER_845</span></span>
    
## <a name="details"></a><span data-ttu-id="575e2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="575e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="575e2-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="575e2-104">Product Name</span></span>|<span data-ttu-id="575e2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="575e2-105">SQL Server</span></span>|  
|<span data-ttu-id="575e2-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="575e2-106">Event ID</span></span>|<span data-ttu-id="575e2-107">845</span><span class="sxs-lookup"><span data-stu-id="575e2-107">845</span></span>|  
|<span data-ttu-id="575e2-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="575e2-108">Event Source</span></span>|<span data-ttu-id="575e2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="575e2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="575e2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="575e2-110">Component</span></span>|<span data-ttu-id="575e2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="575e2-111">SQLEngine</span></span>|  
|<span data-ttu-id="575e2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="575e2-112">Symbolic Name</span></span>|<span data-ttu-id="575e2-113">BUFLATCH_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="575e2-113">BUFLATCH_TIMEOUT</span></span>|  
|<span data-ttu-id="575e2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="575e2-114">Message Text</span></span>|<span data-ttu-id="575e2-115">Tiempo de espera agotado para el tipo de bloqueo temporal del búfer %d de la página %S_PGID, id. de base de datos %d.</span><span class="sxs-lookup"><span data-stu-id="575e2-115">Time-out occurred while waiting for buffer latch type %d for page %S_PGID, database ID %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="575e2-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="575e2-116">Explanation</span></span>  
 <span data-ttu-id="575e2-117">Un proceso estaba esperando adquirir un bloqueo temporal, pero el proceso ha esperado hasta que el límite de tiempo ha expirado y no se ha podido adquirir.</span><span class="sxs-lookup"><span data-stu-id="575e2-117">A process was waiting to acquire a latch, but the process waited until the time limit expired and failed to acquire one.</span></span> <span data-ttu-id="575e2-118">Esto puede ocurrir si una operación de E/S tarda demasiado en completarse, normalmente debido a otras tareas que bloquean procesos del sistema.</span><span class="sxs-lookup"><span data-stu-id="575e2-118">This can occur if an I/O operation takes too long to complete, usually as a result of other tasks blocking system processes.</span></span> <span data-ttu-id="575e2-119">En algunos casos, este error puede ser el resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="575e2-119">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="575e2-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="575e2-120">User Action</span></span>  
 <span data-ttu-id="575e2-121">Las siguientes tareas pueden impedir este error:</span><span class="sxs-lookup"><span data-stu-id="575e2-121">Performing the following tasks may prevent this error:</span></span>  
  
-   <span data-ttu-id="575e2-122">Reduzca la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="575e2-122">Reduce the workload.</span></span>  
  
-   <span data-ttu-id="575e2-123">Compruebe si hay errores de E/S asociados en el registro de errores o en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="575e2-123">Verify whether there are associated I/O failures in the error log or event log.</span></span> <span data-ttu-id="575e2-124">Normalmente, los errores de E/S se deben a un funcionamiento incorrecto del disco.</span><span class="sxs-lookup"><span data-stu-id="575e2-124">I/O failures are typically caused by disk malfunction.</span></span>  
  
-   <span data-ttu-id="575e2-125">Compruebe el registro de errores para ver si hay tareas que no rinden y otros errores críticos.</span><span class="sxs-lookup"><span data-stu-id="575e2-125">Check error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="575e2-126">Si se producen frecuentemente errores críticos, como aserciones, solucione estos problemas.</span><span class="sxs-lookup"><span data-stu-id="575e2-126">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="575e2-127">Si el error persiste, póngase en contacto con el servicio de Soporte técnico y Atención al cliente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="575e2-127">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
