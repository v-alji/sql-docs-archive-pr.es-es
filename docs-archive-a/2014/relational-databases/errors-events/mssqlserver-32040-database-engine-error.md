---
title: MSSQLSERVER_32040 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 32040 (Database Engine error)
ms.assetid: 709219b1-f8b2-4696-8923-dd2e91492eb8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05692e2f20b0719c1ca8f48282c3b7aaed8e2341
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672070"
---
# <a name="mssqlserver_32040"></a><span data-ttu-id="4adbb-102">MSSQLSERVER_32040</span><span class="sxs-lookup"><span data-stu-id="4adbb-102">MSSQLSERVER_32040</span></span>
    
## <a name="details"></a><span data-ttu-id="4adbb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4adbb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4adbb-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="4adbb-104">Product Name</span></span>|<span data-ttu-id="4adbb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4adbb-105">SQL Server</span></span>|  
|<span data-ttu-id="4adbb-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4adbb-106">Event ID</span></span>|<span data-ttu-id="4adbb-107">32040</span><span class="sxs-lookup"><span data-stu-id="4adbb-107">32040</span></span>|  
|<span data-ttu-id="4adbb-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="4adbb-108">Event Source</span></span>|<span data-ttu-id="4adbb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4adbb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4adbb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4adbb-110">Component</span></span>|<span data-ttu-id="4adbb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4adbb-111">SQLEngine</span></span>|  
|<span data-ttu-id="4adbb-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4adbb-112">Symbolic Name</span></span>|<span data-ttu-id="4adbb-113">SQLErrorNum32040</span><span class="sxs-lookup"><span data-stu-id="4adbb-113">SQLErrorNum32040</span></span>|  
|<span data-ttu-id="4adbb-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4adbb-114">Message Text</span></span>|<span data-ttu-id="4adbb-115">Se ha producido la alerta para 'transacción sin enviar más antigua'.</span><span class="sxs-lookup"><span data-stu-id="4adbb-115">The alert for 'oldest unsent transaction' has been raised.</span></span> <span data-ttu-id="4adbb-116">El valor actual de '%d' sobrepasa el umbral '%d'.</span><span class="sxs-lookup"><span data-stu-id="4adbb-116">The current value of '%d' surpasses the threshold '%d'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4adbb-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="4adbb-117">Explanation</span></span>  
 <span data-ttu-id="4adbb-118">Este evento de creación de reflejo de la base de datos se genera en la instancia del servidor principal para indicar que la edad de la transacción sin enviar más antigua ha alcanzado el valor umbral especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4adbb-118">This database mirroring event is issued on the principal server instance to indicate that the age of the oldest unsent transaction has reached a user-specified threshold value.</span></span> <span data-ttu-id="4adbb-119">Normalmente, este evento se produce al cambiar el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="4adbb-119">Typically, this event occurs because the performance of the system has changed.</span></span> <span data-ttu-id="4adbb-120">El ancho de banda entre los dos sistemas ha disminuido, o bien la carga ha aumentado.</span><span class="sxs-lookup"><span data-stu-id="4adbb-120">Either the bandwidth between the two systems has decreased, or the load has increased.</span></span>  
  
 <span data-ttu-id="4adbb-121">La edad de la transacción sin enviar más antigua es una medida del rendimiento que le puede ayudar a evaluar el potencial de pérdida de datos como medida del número de minutos de transacciones sin enviar.</span><span class="sxs-lookup"><span data-stu-id="4adbb-121">The age of the oldest unsent transaction is a performance metric that can help you evaluate the potential for data loss as measured by the number of minutes of unsent transactions.</span></span> <span data-ttu-id="4adbb-122">Esta medida es especialmente relevante en sesiones de modo de alto rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4adbb-122">This metric is especially relevant for high-performance mode sessions.</span></span> <span data-ttu-id="4adbb-123">No obstante, esta medida también es importante para la sesión de modo de alta seguridad cuando la creación de reflejo se detiene o suspende debido a que los asociados se han desconectado.</span><span class="sxs-lookup"><span data-stu-id="4adbb-123">However, this metric is also relevant for high-safety mode session when mirroring is paused or suspended because the partners become disconnected.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4adbb-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4adbb-124">User Action</span></span>  
 <span data-ttu-id="4adbb-125">Compruebe las cargas en las instancias del servidor principal y reflejado y su conexión de red para localizar la causa.</span><span class="sxs-lookup"><span data-stu-id="4adbb-125">Check the loads on the principal and mirror server instances and their network connection for the cause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4adbb-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4adbb-126">See Also</span></span>  
 <span data-ttu-id="4adbb-127">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4adbb-127">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="4adbb-128">Usar alertas y umbrales de advertencia de las métricas de rendimiento de la creación de reflejo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4adbb-128">Use Warning Thresholds and Alerts on Mirroring Performance Metrics &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/use-warning-thresholds-and-alerts-on-mirroring-performance-metrics-sql-server.md)  
  
  
