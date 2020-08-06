---
title: MSSQLSERVER_844 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 844 (Database Engine error)
ms.assetid: 2060c886-1226-4066-bc0c-de90a1cfb82b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4870d6e43ec12b49033ea3b5f88fa0d0cdd597a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671567"
---
# <a name="mssqlserver_844"></a><span data-ttu-id="daa8f-102">MSSQLSERVER_844</span><span class="sxs-lookup"><span data-stu-id="daa8f-102">MSSQLSERVER_844</span></span>
    
## <a name="details"></a><span data-ttu-id="daa8f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="daa8f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="daa8f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="daa8f-104">Product Name</span></span>|<span data-ttu-id="daa8f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="daa8f-105">SQL Server</span></span>|  
|<span data-ttu-id="daa8f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="daa8f-106">Event ID</span></span>|<span data-ttu-id="daa8f-107">844</span><span class="sxs-lookup"><span data-stu-id="daa8f-107">844</span></span>|  
|<span data-ttu-id="daa8f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="daa8f-108">Event Source</span></span>|<span data-ttu-id="daa8f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="daa8f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="daa8f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="daa8f-110">Component</span></span>|<span data-ttu-id="daa8f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="daa8f-111">SQLEngine</span></span>|  
|<span data-ttu-id="daa8f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="daa8f-112">Symbolic Name</span></span>|<span data-ttu-id="daa8f-113">BUFLATCH_TIMEOUT_CONTINUE</span><span class="sxs-lookup"><span data-stu-id="daa8f-113">BUFLATCH_TIMEOUT_CONTINUE</span></span>|  
|<span data-ttu-id="daa8f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="daa8f-114">Message Text</span></span>|<span data-ttu-id="daa8f-115">Tiempo de espera agotado mientras se esperaba el bloqueo temporal del búfer -- tipo %d, bp %p, página %d:%d, stat %#x, id. de base de datos: %d, id. de unidad de asignación: %I64d%ls, tarea 0x%p : %d, tiempo de espera %d, marcas 0x%I64x, tarea propietaria 0x%p.</span><span class="sxs-lookup"><span data-stu-id="daa8f-115">Time-out occurred while waiting for buffer latch -- type %d, bp %p, page %d:%d, stat %#x, database id: %d, allocation unit id: %I64d%ls, task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span>  <span data-ttu-id="daa8f-116">Esperando.</span><span class="sxs-lookup"><span data-stu-id="daa8f-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="daa8f-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="daa8f-117">Explanation</span></span>  
 <span data-ttu-id="daa8f-118">Un proceso está esperando para adquirir un bloqueo temporal.</span><span class="sxs-lookup"><span data-stu-id="daa8f-118">A process is waiting to acquire a latch.</span></span> <span data-ttu-id="daa8f-119">Este problema puede estar causado por una operación de E/S que está tardando mucho en llevarse a cabo.</span><span class="sxs-lookup"><span data-stu-id="daa8f-119">This problem can be caused by an I/O operation taking too long to complete.</span></span> <span data-ttu-id="daa8f-120">Normalmente, este tipo de error es el resultado de que otras tareas estén bloqueando los procesos del sistema.</span><span class="sxs-lookup"><span data-stu-id="daa8f-120">Typically this type of error is the result of other tasks blocking system processes.</span></span> <span data-ttu-id="daa8f-121">En algunos casos, este error puede ser el resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="daa8f-121">In some instances, this error may be the result of hardware failure.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="daa8f-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="daa8f-122">User Action</span></span>  
 <span data-ttu-id="daa8f-123">Para evitar que ocurra este error, intente lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="daa8f-123">Try the following to prevent this error from occurring:</span></span>  
  
-   <span data-ttu-id="daa8f-124">Reduzca la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="daa8f-124">Reduce workload.</span></span>  
  
-   <span data-ttu-id="daa8f-125">Busque errores de E/S asociados en el registro de errores o el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="daa8f-125">Check for associated I/O failures in error log or event log.</span></span> <span data-ttu-id="daa8f-126">Normalmente, los errores de E/S indican un funcionamiento incorrecto del disco.</span><span class="sxs-lookup"><span data-stu-id="daa8f-126">I/O failures typically point to a disk malfunction.</span></span>  
  
-   <span data-ttu-id="daa8f-127">Compruebe el registro de errores para ver si hay tareas que no rinden y otros errores críticos.</span><span class="sxs-lookup"><span data-stu-id="daa8f-127">Check the error log for non-yielding tasks and other critical errors.</span></span>  
  
-   <span data-ttu-id="daa8f-128">Si se producen frecuentemente errores críticos, como aserciones, solucione estos problemas.</span><span class="sxs-lookup"><span data-stu-id="daa8f-128">If critical errors such as asserts frequently occur, resolve these problems.</span></span>  
  
 <span data-ttu-id="daa8f-129">Si el error persiste, póngase en contacto con el servicio de Soporte técnico y Atención al cliente de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="daa8f-129">If the error persists, contact Microsoft Customer Service and Support.</span></span>  
  
  
