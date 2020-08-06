---
title: MSSQLSERVER_32042 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32042 (Database Engine error)
ms.assetid: 53a51c7a-dcd4-4c15-b4d2-6aaa9dce76da
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: bd959d84da2c54310dea5156b1a45b73490211a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672069"
---
# <a name="mssqlserver_32042"></a><span data-ttu-id="fe503-102">MSSQLSERVER_32042</span><span class="sxs-lookup"><span data-stu-id="fe503-102">MSSQLSERVER_32042</span></span>
    
## <a name="details"></a><span data-ttu-id="fe503-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fe503-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe503-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="fe503-104">Product Name</span></span>|<span data-ttu-id="fe503-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fe503-105">SQL Server</span></span>|  
|<span data-ttu-id="fe503-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fe503-106">Event ID</span></span>|<span data-ttu-id="fe503-107">32042</span><span class="sxs-lookup"><span data-stu-id="fe503-107">32042</span></span>|  
|<span data-ttu-id="fe503-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="fe503-108">Event Source</span></span>|<span data-ttu-id="fe503-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fe503-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fe503-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fe503-110">Component</span></span>|<span data-ttu-id="fe503-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fe503-111">SQLEngine</span></span>|  
|<span data-ttu-id="fe503-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fe503-112">Symbolic Name</span></span>|<span data-ttu-id="fe503-113">SQLErrorNum32042</span><span class="sxs-lookup"><span data-stu-id="fe503-113">SQLErrorNum32042</span></span>|  
|<span data-ttu-id="fe503-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fe503-114">Message Text</span></span>|<span data-ttu-id="fe503-115">Se ha producido la alerta para 'registro sin enviar'.</span><span class="sxs-lookup"><span data-stu-id="fe503-115">The alert for 'unsent log' has been raised.</span></span> <span data-ttu-id="fe503-116">El valor actual de '%d' sobrepasa el umbral '%d'.</span><span class="sxs-lookup"><span data-stu-id="fe503-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fe503-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="fe503-117">Explanation</span></span>  
 <span data-ttu-id="fe503-118">Este evento de creación de reflejo de la base de datos se genera en la instancia del servidor principal para indicar que la cantidad de registro sin enviar ha alcanzado el valor umbral especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fe503-118">This database mirroring event is issued on the principal server instance to indicate that the amount of unsent log has reached a user-specified threshold value.</span></span> <span data-ttu-id="fe503-119">Normalmente, este evento se produce al cambiar el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="fe503-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="fe503-120">El ancho de banda entre los dos sistemas ha disminuido, o bien la carga ha aumentado.</span><span class="sxs-lookup"><span data-stu-id="fe503-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="fe503-121">La cantidad de registro sin enviar es una medida de rendimiento que le puede ayudar a evaluar el potencial de pérdida de datos en número de kilobytes (KB) de registro sin enviar.</span><span class="sxs-lookup"><span data-stu-id="fe503-121">The amount of unsent log is a performance metric that can help you evaluate the potential for data loss in terms of the number of kilobytes (KB) of unsent log.</span></span> <span data-ttu-id="fe503-122">Esta medida es especialmente pertinente en sesiones de modo de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fe503-122">This metric is particularly relevant for high-performance mode sessions.</span></span> <span data-ttu-id="fe503-123">No obstante, esta medida también es importante para la sesión de modo de alta seguridad cuando la creación de reflejo se detiene o suspende debido a que los asociados se han desconectado.</span><span class="sxs-lookup"><span data-stu-id="fe503-123">However, this metric is also a relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fe503-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fe503-124">User Action</span></span>  
 <span data-ttu-id="fe503-125">Compruebe las cargas en las instancias del servidor principal y reflejado y su conexión de red para localizar la causa.</span><span class="sxs-lookup"><span data-stu-id="fe503-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe503-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe503-126">See Also</span></span>  
 <span data-ttu-id="fe503-127">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe503-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="fe503-128">Usar alertas y umbrales de advertencia de las métricas de rendimiento de la creación de reflejo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe503-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
