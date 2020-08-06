---
title: Clase de eventos Umbral de la CPU superado | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- CPU Threshold Exceeded Event Class
ms.assetid: eb106f7d-baa3-4a2b-96b2-f9fe0844057d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07b51e1a6f08f48c601b00d2dcb67bc6d09006f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663518"
---
# <a name="cpu-threshold-exceeded-event-class"></a><span data-ttu-id="9d272-102">Clase de eventos Umbral de la CPU superado</span><span class="sxs-lookup"><span data-stu-id="9d272-102">CPU Threshold Exceeded Event Class</span></span>
  <span data-ttu-id="9d272-103">Esta clase de eventos indica que el regulador de recursos ha detectado una consulta que supera el umbral de la CPU especificado para REQUEST_MAX_CPU_TIME_SEC.</span><span class="sxs-lookup"><span data-stu-id="9d272-103">The CPU Threshold Exceeded event class indicates that Resource Governor detects a query that exceeds the CPU threshold specified for REQUEST_MAX_CPU_TIME_SEC.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9d272-104">El intervalo para la detección de este evento es de cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="9d272-104">The detection interval for this event is five seconds.</span></span> <span data-ttu-id="9d272-105">Está garantizado que se generará un evento si una consulta supera el límite especificado por lo menos en cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="9d272-105">It is guaranteed that an event will be generated if a query exceeds the specified limit by at least five seconds.</span></span> <span data-ttu-id="9d272-106">Sin embargo, si una consulta supera el umbral especificado en menos de cinco segundos, es posible que se omita su detección dependiendo del tiempo de ejecución de la consulta y del momento en el que se llevó a cabo el último barrido para la detección.</span><span class="sxs-lookup"><span data-stu-id="9d272-106">However, if a query exceeds the specified threshold by less than five seconds, its detection might be missed depending on the timing of the query and the time of last detection sweep.</span></span>  
  
## <a name="cpu-threshold-exceeded-data-columns"></a><span data-ttu-id="9d272-107">Columnas de datos del Umbral de la CPU superado</span><span class="sxs-lookup"><span data-stu-id="9d272-107">CPU Threshold Exceeded Data Columns</span></span>  
  
|<span data-ttu-id="9d272-108">Nombre de columna de datos</span><span class="sxs-lookup"><span data-stu-id="9d272-108">Data column name</span></span>|<span data-ttu-id="9d272-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="9d272-109">Data type</span></span>|<span data-ttu-id="9d272-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d272-110">Description</span></span>|<span data-ttu-id="9d272-111">Identificador de columna</span><span class="sxs-lookup"><span data-stu-id="9d272-111">Column ID</span></span>|<span data-ttu-id="9d272-112">Filtrable</span><span class="sxs-lookup"><span data-stu-id="9d272-112">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="9d272-113">CPU</span><span class="sxs-lookup"><span data-stu-id="9d272-113">CPU</span></span>|`int`|<span data-ttu-id="9d272-114">Uso de la CPU en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="9d272-114">CPU usage in milliseconds.</span></span>|<span data-ttu-id="9d272-115">18</span><span class="sxs-lookup"><span data-stu-id="9d272-115">18</span></span>|<span data-ttu-id="9d272-116">Sí</span><span class="sxs-lookup"><span data-stu-id="9d272-116">Yes</span></span>|  
|<span data-ttu-id="9d272-117">EventClass</span><span class="sxs-lookup"><span data-stu-id="9d272-117">EventClass</span></span>|`int`|<span data-ttu-id="9d272-118">214</span><span class="sxs-lookup"><span data-stu-id="9d272-118">214</span></span>|<span data-ttu-id="9d272-119">27</span><span class="sxs-lookup"><span data-stu-id="9d272-119">27</span></span>|<span data-ttu-id="9d272-120">No</span><span class="sxs-lookup"><span data-stu-id="9d272-120">No</span></span>|  
|<span data-ttu-id="9d272-121">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="9d272-121">EventSubClass</span></span>|`int`|<span data-ttu-id="9d272-122">Infracción del límite de la CPU.</span><span class="sxs-lookup"><span data-stu-id="9d272-122">CPU limit violation.</span></span>|<span data-ttu-id="9d272-123">21</span><span class="sxs-lookup"><span data-stu-id="9d272-123">21</span></span>|<span data-ttu-id="9d272-124">Sí</span><span class="sxs-lookup"><span data-stu-id="9d272-124">Yes</span></span>|  
|<span data-ttu-id="9d272-125">GroupID</span><span class="sxs-lookup"><span data-stu-id="9d272-125">GroupID</span></span>|`int`|<span data-ttu-id="9d272-126">Id. del grupo donde se produjo la infracción.</span><span class="sxs-lookup"><span data-stu-id="9d272-126">Group ID where the violation occurred.</span></span>|<span data-ttu-id="9d272-127">66</span><span class="sxs-lookup"><span data-stu-id="9d272-127">66</span></span>|<span data-ttu-id="9d272-128">Sí</span><span class="sxs-lookup"><span data-stu-id="9d272-128">Yes</span></span>|  
|<span data-ttu-id="9d272-129">OwnerID</span><span class="sxs-lookup"><span data-stu-id="9d272-129">OwnerID</span></span>|`int`|<span data-ttu-id="9d272-130">SPID del proceso que produjo la infracción.</span><span class="sxs-lookup"><span data-stu-id="9d272-130">SPID of the process that caused the violation.</span></span>|<span data-ttu-id="9d272-131">58</span><span class="sxs-lookup"><span data-stu-id="9d272-131">58</span></span>|<span data-ttu-id="9d272-132">Sí</span><span class="sxs-lookup"><span data-stu-id="9d272-132">Yes</span></span>|  
|<span data-ttu-id="9d272-133">SPID</span><span class="sxs-lookup"><span data-stu-id="9d272-133">SPID</span></span>|`int`|<span data-ttu-id="9d272-134">Id. del proceso de servidor que dispara este evento.</span><span class="sxs-lookup"><span data-stu-id="9d272-134">ID of the server process that fires this event.</span></span><br /><br /> <span data-ttu-id="9d272-135">Nota: Este puede ser diferente al SPID del usuario actual si un subproceso del sistema valida el uso de la CPU como una tarea en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="9d272-135">Note: This can differ from the actual user SPID if a system thread validates CPU usage as a background task.</span></span>|<span data-ttu-id="9d272-136">12</span><span class="sxs-lookup"><span data-stu-id="9d272-136">12</span></span>|<span data-ttu-id="9d272-137">Sí</span><span class="sxs-lookup"><span data-stu-id="9d272-137">Yes</span></span>|  
|<span data-ttu-id="9d272-138">StartTime</span><span class="sxs-lookup"><span data-stu-id="9d272-138">StartTime</span></span>|`datetime`|<span data-ttu-id="9d272-139">El momento en el que se desencadenó este evento.</span><span class="sxs-lookup"><span data-stu-id="9d272-139">The time when this event fired.</span></span>|<span data-ttu-id="9d272-140">14</span><span class="sxs-lookup"><span data-stu-id="9d272-140">14</span></span>|<span data-ttu-id="9d272-141">Sí</span><span class="sxs-lookup"><span data-stu-id="9d272-141">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d272-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d272-142">See Also</span></span>  
 [<span data-ttu-id="9d272-143">sp_trace_setevent &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9d272-143">sp_trace_setevent &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-trace-setevent-transact-sql)  
  
  
