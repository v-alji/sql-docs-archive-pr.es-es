---
title: Almacenamiento XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 4070580b-880d-4f4c-abcc-626a4fe0c9a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: efd4a9eba36060d3d4bab9b371678ab2b2c409ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673667"
---
# <a name="xtp-storage"></a><span data-ttu-id="69917-102">XTP Storage</span><span class="sxs-lookup"><span data-stu-id="69917-102">XTP Storage</span></span>
  <span data-ttu-id="69917-103">El objeto de rendimiento XTP Storage contiene contadores relacionados con el almacenamiento de XTP en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69917-103">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="69917-104">En esta tabla se describen los contadores de **XTP Storage** .</span><span class="sxs-lookup"><span data-stu-id="69917-104">This table describes the **XTP Storage** counters.</span></span>  
  
|<span data-ttu-id="69917-105">Contador</span><span class="sxs-lookup"><span data-stu-id="69917-105">Counter</span></span>|<span data-ttu-id="69917-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="69917-106">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69917-107">**Checkpoints Closed**</span><span class="sxs-lookup"><span data-stu-id="69917-107">**Checkpoints Closed**</span></span>|<span data-ttu-id="69917-108">Número de puntos de comprobación cerrados realizados por el agente en línea.</span><span class="sxs-lookup"><span data-stu-id="69917-108">Count of checkpoints closed done by online agent.</span></span>|  
|<span data-ttu-id="69917-109">**Checkpoints Completed**</span><span class="sxs-lookup"><span data-stu-id="69917-109">**Checkpoints Completed**</span></span>|<span data-ttu-id="69917-110">Número de puntos de comprobación procesados por el subproceso de punto de comprobación sin conexión.</span><span class="sxs-lookup"><span data-stu-id="69917-110">Count of checkpoints processed by offline checkpoint thread.</span></span>|  
|<span data-ttu-id="69917-111">**Core Merges Completed**</span><span class="sxs-lookup"><span data-stu-id="69917-111">**Core Merges Completed**</span></span>|<span data-ttu-id="69917-112">Número de mezclas básicas completadas por el subproceso de trabajo de mezcla.</span><span class="sxs-lookup"><span data-stu-id="69917-112">The number of core merges completed by the merge worker thread.</span></span> <span data-ttu-id="69917-113">Todavía será necesario instalar estas mezclas.</span><span class="sxs-lookup"><span data-stu-id="69917-113">These merges still need to be installed.</span></span>|  
|<span data-ttu-id="69917-114">**Merge Policy Evaluations**</span><span class="sxs-lookup"><span data-stu-id="69917-114">**Merge Policy Evaluations**</span></span>|<span data-ttu-id="69917-115">Número de evaluaciones de directivas de mezcla desde que el servidor se inició.</span><span class="sxs-lookup"><span data-stu-id="69917-115">The number of merge policy evaluations since the server started.</span></span>|  
|<span data-ttu-id="69917-116">**Merge Requests Outstanding**</span><span class="sxs-lookup"><span data-stu-id="69917-116">**Merge Requests Outstanding**</span></span>|<span data-ttu-id="69917-117">Número de solicitudes de mezcla pendientes desde que el servidor se inició.</span><span class="sxs-lookup"><span data-stu-id="69917-117">The number of merge requests outstanding since the server started.</span></span>|  
|<span data-ttu-id="69917-118">**Merges Abandoned**</span><span class="sxs-lookup"><span data-stu-id="69917-118">**Merges Abandoned**</span></span>|<span data-ttu-id="69917-119">Número de mezclas abandonadas debido a un error.</span><span class="sxs-lookup"><span data-stu-id="69917-119">The number of merges abandoned due to failure.</span></span>|  
|<span data-ttu-id="69917-120">**Merges Installed**</span><span class="sxs-lookup"><span data-stu-id="69917-120">**Merges Installed**</span></span>|<span data-ttu-id="69917-121">Número de mezclas instaladas correctamente.</span><span class="sxs-lookup"><span data-stu-id="69917-121">The number of merges successfully installed.</span></span>|  
|<span data-ttu-id="69917-122">**Total Files Merged**</span><span class="sxs-lookup"><span data-stu-id="69917-122">**Total Files Merged**</span></span>|<span data-ttu-id="69917-123">Número total de archivos de origen mezclados.</span><span class="sxs-lookup"><span data-stu-id="69917-123">The total number of source files merged.</span></span> <span data-ttu-id="69917-124">Este número se puede usar para determinar el número promedio de archivos de origen de la mezcla.</span><span class="sxs-lookup"><span data-stu-id="69917-124">This count can be used to find the average number of source files in the merge.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69917-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69917-125">See Also</span></span>  
 [<span data-ttu-id="69917-126">Contadores de rendimiento de OLTP &#40;en memoria&#41;</span><span class="sxs-lookup"><span data-stu-id="69917-126">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
