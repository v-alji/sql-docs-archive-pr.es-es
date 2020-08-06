---
title: MSSQLSERVER_32043 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32043 (Database Engine error)
ms.assetid: a0c48ae3-4c8c-419c-afb5-579fcefac01d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2febc7173c8144451c7a9b0576f2293d5594c6df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662989"
---
# <a name="mssqlserver_32043"></a><span data-ttu-id="d8473-102">MSSQLSERVER_32043</span><span class="sxs-lookup"><span data-stu-id="d8473-102">MSSQLSERVER_32043</span></span>
    
## <a name="details"></a><span data-ttu-id="d8473-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="d8473-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8473-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="d8473-104">Product Name</span></span>|<span data-ttu-id="d8473-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8473-105">SQL Server</span></span>|  
|<span data-ttu-id="d8473-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="d8473-106">Event ID</span></span>|<span data-ttu-id="d8473-107">32043</span><span class="sxs-lookup"><span data-stu-id="d8473-107">32043</span></span>|  
|<span data-ttu-id="d8473-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="d8473-108">Event Source</span></span>|<span data-ttu-id="d8473-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d8473-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d8473-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d8473-110">Component</span></span>|<span data-ttu-id="d8473-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d8473-111">SQLEngine</span></span>|  
|<span data-ttu-id="d8473-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="d8473-112">Symbolic Name</span></span>|<span data-ttu-id="d8473-113">SQLErrorNum32043</span><span class="sxs-lookup"><span data-stu-id="d8473-113">SQLErrorNum32043</span></span>|  
|<span data-ttu-id="d8473-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="d8473-114">Message Text</span></span>|<span data-ttu-id="d8473-115">Se ha producido la alerta para 'registro sin restaurar'.</span><span class="sxs-lookup"><span data-stu-id="d8473-115">The alert for 'unrestored log' has been raised.</span></span> <span data-ttu-id="d8473-116">El valor actual de '%d' sobrepasa el umbral '%d'.</span><span class="sxs-lookup"><span data-stu-id="d8473-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8473-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="d8473-117">Explanation</span></span>  
 <span data-ttu-id="d8473-118">Este evento de creación de reflejo de la base de datos se genera en la instancia del servidor reflejado para indicar que la cantidad de registro sin restaurar ha alcanzado el valor umbral especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d8473-118">This database mirroring event is issued on the mirror server instance to indicate that the amount of unrestored log reached a user-specified threshold value.</span></span> <span data-ttu-id="d8473-119">Normalmente, este evento se produce al cambiar el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="d8473-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="d8473-120">El ancho de banda entre los dos sistemas ha disminuido, o bien la carga ha aumentado.</span><span class="sxs-lookup"><span data-stu-id="d8473-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="d8473-121">Un registro sin restaurar es un registro recibido por la instancia del servidor reflejado y escrito en el disco, pero que está esperando a ser restaurado en la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="d8473-121">An unrestored log is a log that has been received by the mirror server instance and written to disk but is waiting to be restored to the mirror database.</span></span> <span data-ttu-id="d8473-122">La cantidad de registro no restaurado en kilobytes (KB) es una medida del rendimiento que le puede ayudar a evaluar el tiempo de conmutación por error actual.</span><span class="sxs-lookup"><span data-stu-id="d8473-122">The amount of unrestored log in kilobytes (KB) is a performance metric that can help you evaluate the current failover time.</span></span> <span data-ttu-id="d8473-123">El tiempo necesario para aplicar el registro sin restaurar es el factor principal en el tiempo de conmutación por error, junto con un breve tiempo adicional necesario para recuperar la base de datos y ponerla en línea.</span><span class="sxs-lookup"><span data-stu-id="d8473-123">The time that is required to apply the unrestored log is the main factor in failover time, along with a short additional time that is required to recover the database and bring it online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d8473-124">En el caso de una conmutación automática por error, el tiempo para que el sistema notifique el error no depende del tiempo de conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="d8473-124">For an automatic failover, the time for the system to notice the failure is independent of the failover time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8473-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="d8473-125">User Action</span></span>  
 <span data-ttu-id="d8473-126">Compruebe las cargas en las instancias del servidor principal y reflejado y su conexión de red para localizar la causa.</span><span class="sxs-lookup"><span data-stu-id="d8473-126">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8473-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8473-127">See Also</span></span>  
 <span data-ttu-id="d8473-128">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d8473-128">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="d8473-129">Usar alertas y umbrales de advertencia de las métricas de rendimiento de la creación de reflejo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d8473-129">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
