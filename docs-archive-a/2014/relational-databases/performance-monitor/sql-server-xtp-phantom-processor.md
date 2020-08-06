---
title: Procesador fantasma de XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 0f691b3d-a8fd-4459-ad21-2cfc8574a8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14158b7097427b6704cf5e747fa998a11217ecd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745242"
---
# <a name="xtp-phantom-processor"></a><span data-ttu-id="44cd4-102">Procesador fantasma de XTP</span><span class="sxs-lookup"><span data-stu-id="44cd4-102">XTP Phantom Processor</span></span>
  <span data-ttu-id="44cd4-103">El objeto de rendimiento Procesador fantasma de XTP contiene contadores relacionados con el subsistema de procesamiento fantasma del motor de XTP.</span><span class="sxs-lookup"><span data-stu-id="44cd4-103">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="44cd4-104">Este componente es responsable de detectar filas fantasma en transacciones que se ejecutan en el nivel de aislamiento SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="44cd4-104">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>  
  
 <span data-ttu-id="44cd4-105">En esta tabla se describen los contadores de **Procesador fantasma de XTP** .</span><span class="sxs-lookup"><span data-stu-id="44cd4-105">This table describes the **XTP Phantom Processor** counters.</span></span>  
  
|<span data-ttu-id="44cd4-106">Contador</span><span class="sxs-lookup"><span data-stu-id="44cd4-106">Counter</span></span>|<span data-ttu-id="44cd4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="44cd4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="44cd4-108">**Reintentos de recorrido de esquinas sucias/s (emitidos por el fantasma)**</span><span class="sxs-lookup"><span data-stu-id="44cd4-108">**Dusty corner scan retries/sec (Phantom-issued)**</span></span>|<span data-ttu-id="44cd4-109">Número de reintentos de recorrido debido a conflictos de escritura durante los rastreos de esquinas sucias emitidos por el procesador fantasma (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="44cd4-109">The number of scan retries due to write conflicts during dusty corner sweeps issued by the phantom processor (on average), per second.</span></span> <span data-ttu-id="44cd4-110">Es un contador de nivel muy bajo, no está pensado para uso de los clientes.</span><span class="sxs-lookup"><span data-stu-id="44cd4-110">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="44cd4-111">**Filas fantasma expiradas quitadas/s**</span><span class="sxs-lookup"><span data-stu-id="44cd4-111">**Phantom expired rows removed/sec**</span></span>|<span data-ttu-id="44cd4-112">Número de filas expiradas quitadas mediante recorridos fantasma (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="44cd4-112">The number of expired rows removed by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="44cd4-113">**Filas fantasma expiradas tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="44cd4-113">**Phantom expired rows touched/sec**</span></span>|<span data-ttu-id="44cd4-114">Número de filas expiradas tocadas por recorridos fantasma (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="44cd4-114">The number of expired rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="44cd4-115">**Filas fantasma que van a expirar tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="44cd4-115">**Phantom expiring rows touched/sec**</span></span>|<span data-ttu-id="44cd4-116">Número de filas que van a expirar tocadas por recorridos fantasma (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="44cd4-116">The number of expiring rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="44cd4-117">**Filas fantasma tocadas/s**</span><span class="sxs-lookup"><span data-stu-id="44cd4-117">**Phantom rows touched/sec**</span></span>|<span data-ttu-id="44cd4-118">Número de filas tocadas por recorridos fantasma (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="44cd4-118">The number of rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="44cd4-119">**Recorridos fantasma iniciados/s**</span><span class="sxs-lookup"><span data-stu-id="44cd4-119">**Phantom scans started/sec**</span></span>|<span data-ttu-id="44cd4-120">Número de recorridos fantasma iniciados (en promedio), por segundo.</span><span class="sxs-lookup"><span data-stu-id="44cd4-120">The number of phantom scans started (on average), per second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44cd4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44cd4-121">See Also</span></span>  
 [<span data-ttu-id="44cd4-122">Contadores de rendimiento de OLTP &#40;en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="44cd4-122">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
