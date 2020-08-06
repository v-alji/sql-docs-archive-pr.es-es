---
title: Cursores XTP | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 84bf4654-3ef7-4d7f-a269-c8bb4ed4acad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 217a1196717492cb92adb24eaf7c06c8867abc2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747565"
---
# <a name="xtp-cursors"></a><span data-ttu-id="15dc4-102">Cursores XTP</span><span class="sxs-lookup"><span data-stu-id="15dc4-102">XTP Cursors</span></span>
  <span data-ttu-id="15dc4-103">El objeto de rendimiento Cursores XTP contiene contadores relacionados con los cursores internos del motor de XTP.</span><span class="sxs-lookup"><span data-stu-id="15dc4-103">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="15dc4-104">Los cursores son los bloques de creación de bajo nivel que el motor de XTP utiliza para procesar consultas de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15dc4-104">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="15dc4-105">Por tanto, el usuario no tiene normalmente control directo sobre ellos.</span><span class="sxs-lookup"><span data-stu-id="15dc4-105">As such, you do not typically have direct control over them.</span></span>  
  
 <span data-ttu-id="15dc4-106">En esta tabla se describen los contadores de **cursores XTP** .</span><span class="sxs-lookup"><span data-stu-id="15dc4-106">This table describes the **XTP Cursors** counters.</span></span>  
  
|<span data-ttu-id="15dc4-107">Contador</span><span class="sxs-lookup"><span data-stu-id="15dc4-107">Counter</span></span>|<span data-ttu-id="15dc4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="15dc4-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15dc4-109">**Eliminaciones de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-109">**Cursor deletes/sec**</span></span>|<span data-ttu-id="15dc4-110">Número de eliminaciones de cursor (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-110">The number of cursor deletes (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-111">**Inserciones de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-111">**Cursor inserts/sec**</span></span>|<span data-ttu-id="15dc4-112">Número de inserciones de cursor (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-112">The number of cursor inserts (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-113">**Recorridos de cursor iniciados/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-113">**Cursor scans started /sec**</span></span>|<span data-ttu-id="15dc4-114">Número de recorridos de cursor iniciados (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-114">The number of cursor scans started (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-115">**Infracciones de restricciones UNIQUE de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-115">**Cursor unique violations/sec**</span></span>|<span data-ttu-id="15dc4-116">Número de infracciones de restricciones UNIQUE (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-116">The number of unique-constraint violations (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-117">**Actualizaciones de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-117">**Cursor updates/sec**</span></span>|<span data-ttu-id="15dc4-118">Número de actualizaciones de cursor (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-118">The number of cursor updates (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-119">**Conflictos de escritura de cursor/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-119">**Cursor write   conflicts/sec**</span></span>|<span data-ttu-id="15dc4-120">Número de conflictos de escritura contra escritura en la misma versión de fila (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-120">The number of write-write conflicts to the same row version (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-121">**Reintentos de recorrido de esquinas sucias/s (emitidos por el usuario)**</span><span class="sxs-lookup"><span data-stu-id="15dc4-121">**Dusty corner scan retries/sec (user-issued)**</span></span>|<span data-ttu-id="15dc4-122">Número de reintentos de recorrido debido a conflictos de escritura durante los rastreos de esquinas sucias emitidos por un recorrido de tabla completo del usuario (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-122">The number of scan retries due to write conflicts during dusty corner sweeps issued by a user's full-table scan (on average), per second.</span></span> <span data-ttu-id="15dc4-123">Es un contador de nivel muy bajo, no está pensado para uso de los clientes.</span><span class="sxs-lookup"><span data-stu-id="15dc4-123">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="15dc4-124">**Filas expiradas quitadas/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-124">**Expired rows removed/sec**</span></span>|<span data-ttu-id="15dc4-125">Número de filas expiradas quitadas mediante cursores (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-125">The number of expired rows removed by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-126">**Filas expiradas tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-126">**Expired rows touched/sec**</span></span>|<span data-ttu-id="15dc4-127">Número de filas expiradas tocadas mediante cursores (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-127">The number of expired rows touched by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-128">**Filas devueltas/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-128">**Rows returned/sec**</span></span>|<span data-ttu-id="15dc4-129">Número de filas devueltas mediante cursores (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-129">The number of rows returned by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-130">**Filas tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-130">**Rows touched/sec**</span></span>|<span data-ttu-id="15dc4-131">Número de filas tocadas mediante cursores (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-131">The number of rows touched by cursors (on average), per second.</span></span>|  
|<span data-ttu-id="15dc4-132">**Filas tocadas eliminadas provisionalmente/s**</span><span class="sxs-lookup"><span data-stu-id="15dc4-132">**Tentatively-deleted rows touched/sec**</span></span>|<span data-ttu-id="15dc4-133">Número de filas que van a expirar tocadas mediante cursores (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="15dc4-133">The number of expiring rows touched by cursors (on average), per second.</span></span> <span data-ttu-id="15dc4-134">Una fila va a expirar si la transacción que la eliminó permanece activa (es decir, no se confirma o anula).</span><span class="sxs-lookup"><span data-stu-id="15dc4-134">A row is expiring if the transaction that deleted it is still active (i.e. has not yet committed or aborted.)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15dc4-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15dc4-135">See Also</span></span>  
 [<span data-ttu-id="15dc4-136">Contadores de rendimiento de OLTP &#40;en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="15dc4-136">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
