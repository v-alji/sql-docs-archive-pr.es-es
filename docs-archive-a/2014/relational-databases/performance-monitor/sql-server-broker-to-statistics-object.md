---
title: Objeto SQL Server, Broker TO Statistics | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Broker Transmission Object object
- 'SQL Server: Broker Transmission Object'
ms.assetid: b5bc5dde-e540-4848-8aa3-5735c51df2fb
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 93d9c24a175dedfee171eccfccb34673501660ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675811"
---
# <a name="sql-server-broker-to-statistics-object"></a><span data-ttu-id="84dfc-102">Objeto SQL Server, Broker TO Statistics</span><span class="sxs-lookup"><span data-stu-id="84dfc-102">SQL Server, Broker TO Statistics Object</span></span>
  <span data-ttu-id="84dfc-103">El objeto de rendimiento SQLServer:Broker To Statistics informa del número de veces que los cuadros de diálogo de [!INCLUDE[ssSB](../../includes/sssb-md.md)] solicitan objetos de transmisión y con qué frecuencia se escriben los objetos de transmisión en **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="84dfc-103">The SQLServer:Broker TO Statistics performance object reports information about how many times [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialogs request transmission objects, and how often transmission objects are written to **tempdb**.</span></span>  
  
 <span data-ttu-id="84dfc-104">Los objetos de transmisión registran el estado de las transmisiones de mensajes para un diálogo de [!INCLUDE[ssSB](../../includes/sssb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="84dfc-104">Transmission objects record the state of message transmissions for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] dialog.</span></span> <span data-ttu-id="84dfc-105">Están almacenados en la memoria.</span><span class="sxs-lookup"><span data-stu-id="84dfc-105">They are stored in memory.</span></span> <span data-ttu-id="84dfc-106">Para liberar memoria, [!INCLUDE[ssSB](../../includes/sssb-md.md)] escribe periódicamente lotes de objetos de transmisión inactivos en las tablas de trabajo de **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="84dfc-106">To free memory, [!INCLUDE[ssSB](../../includes/sssb-md.md)] periodically writes batches of inactive transmission objects to work tables in **tempdb**.</span></span>  
  
 <span data-ttu-id="84dfc-107">En la tabla siguiente se muestran los contadores incluidos en este objeto.</span><span class="sxs-lookup"><span data-stu-id="84dfc-107">The following table lists the counters that this object contains.</span></span>  
  
|<span data-ttu-id="84dfc-108">Contadores de SQL Server Broker TO Statistics</span><span class="sxs-lookup"><span data-stu-id="84dfc-108">SQL Server Broker TO Statistics counters</span></span>|<span data-ttu-id="84dfc-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="84dfc-109">Description</span></span>|  
|----------------------------------------------|-----------------|  
|<span data-ttu-id="84dfc-110">**Avg. longitud de escrituras por lotes**</span><span class="sxs-lookup"><span data-stu-id="84dfc-110">**Avg. Length of Batched Writes**</span></span>|<span data-ttu-id="84dfc-111">Promedio de objetos de transmisión guardados en un lote.</span><span class="sxs-lookup"><span data-stu-id="84dfc-111">The average number of transmission objects saved in a batch.</span></span>|  
|<span data-ttu-id="84dfc-112">**Avg. tiempo para escribir un lote (ms)**</span><span class="sxs-lookup"><span data-stu-id="84dfc-112">**Avg. Time To Write Batch (ms)**</span></span>|<span data-ttu-id="84dfc-113">Promedio de milisegundos necesarios para guardar un lote de objetos de transmisión.</span><span class="sxs-lookup"><span data-stu-id="84dfc-113">The average number of milliseconds required to save a batch of transmission objects.</span></span>|  
|<span data-ttu-id="84dfc-114">**Avg. tiempo entre lotes (ms)**</span><span class="sxs-lookup"><span data-stu-id="84dfc-114">**Avg. Time Between Batches (ms)**</span></span>|<span data-ttu-id="84dfc-115">Promedio de milisegundos entre las escrituras de lotes de objetos de transmisión.</span><span class="sxs-lookup"><span data-stu-id="84dfc-115">The average number of milliseconds between writes of transmission object batches.</span></span>|  
|<span data-ttu-id="84dfc-116">**Obtenciones de objeto de transmisión/s**</span><span class="sxs-lookup"><span data-stu-id="84dfc-116">**Tran Object Gets/sec**</span></span>|<span data-ttu-id="84dfc-117">Número de veces por segundo en que los diálogos solicitaron objetos de transmisión.</span><span class="sxs-lookup"><span data-stu-id="84dfc-117">The number of times per second that dialogs requested transmission objects.</span></span>|  
|<span data-ttu-id="84dfc-118">**Número de objetos de transmisión marcados con errores/s**</span><span class="sxs-lookup"><span data-stu-id="84dfc-118">**Tran Objects Marked Dirty/sec**</span></span>|<span data-ttu-id="84dfc-119">Número de veces por segundo en que se han marcado con errores los objetos de transmisión.</span><span class="sxs-lookup"><span data-stu-id="84dfc-119">The number of times per second that transmission objects were marked as dirty.</span></span> <span data-ttu-id="84dfc-120">Los objetos de transmisión se marcan con errores al producirse la primera modificación que hace que la copia en memoria difiera de la copia almacenada en **tempdb**.</span><span class="sxs-lookup"><span data-stu-id="84dfc-120">Transmission objects are marked as dirty by the first modification that causes the in-memory copy to differ from the copy stored in **tempdb**.</span></span> <span data-ttu-id="84dfc-121">Los objetos de transmisión se modifican cuando [!INCLUDE[ssSB](../../includes/sssb-md.md)] tiene que registrar un cambio en el estado de las transmisiones de mensajes para el diálogo.</span><span class="sxs-lookup"><span data-stu-id="84dfc-121">Transmission objects are modified when [!INCLUDE[ssSB](../../includes/sssb-md.md)] has to record a change in the state of message transmissions for the dialog.</span></span>|  
|<span data-ttu-id="84dfc-122">**Escrituras de objeto de transmisión/s**</span><span class="sxs-lookup"><span data-stu-id="84dfc-122">**Tran Object Writes/sec**</span></span>|<span data-ttu-id="84dfc-123">El número de veces por segundo en que un lote de objetos de transmisión se escribió en las tablas de trabajo de **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="84dfc-123">The number of times per second that a batch of transmission objects were written to **tempdb** work tables.</span></span> <span data-ttu-id="84dfc-124">Si se produce un gran número escrituras, podría deberse a que la memoria de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está siendo a sometida una gran demanda.</span><span class="sxs-lookup"><span data-stu-id="84dfc-124">Large numbers of writes could indicate that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] memory is being stressed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="84dfc-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84dfc-125">See Also</span></span>  
 <span data-ttu-id="84dfc-126">[Access Methods (objeto de SQL Server)](sql-server-access-methods-object.md) </span><span class="sxs-lookup"><span data-stu-id="84dfc-126">[SQL Server, Access Methods Object](sql-server-access-methods-object.md) </span></span>  
 <span data-ttu-id="84dfc-127">[Memory Manager (objeto de SQL Server)](sql-server-memory-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="84dfc-127">[SQL Server, Memory Manager Object](sql-server-memory-manager-object.md) </span></span>  
 [<span data-ttu-id="84dfc-128">Supervisar el uso de recursos&#40;Monitor de sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="84dfc-128">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
