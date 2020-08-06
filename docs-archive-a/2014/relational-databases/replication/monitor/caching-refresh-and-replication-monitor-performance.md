---
title: Almacenamiento en caché, actualización y rendimiento del Monitor de replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- monitoring performance [SQL Server replication], Replication Monitor
- cache [SQL Server], replication
- Replication Monitor, caching
- refreshing data
- Replication Monitor, refreshing
ms.assetid: a2d8b666-ed41-4f86-b2b8-c8e118416ab7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b04a91e971e65d19c66cc36f142d8c4764b1b05a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670933"
---
# <a name="caching-refresh-and-replication-monitor-performance"></a><span data-ttu-id="fe896-102">Almacenamiento en caché, actualización y rendimiento del Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="fe896-102">Caching, Refresh, and Replication Monitor Performance</span></span>
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)]<span data-ttu-id="fe896-103">El [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] monitor de replicación está diseñado para supervisar de manera eficaz un gran número de equipos en un sistema de producción.</span><span class="sxs-lookup"><span data-stu-id="fe896-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Replication Monitor is designed to efficiently monitor a large number of computers in a production system.</span></span> <span data-ttu-id="fe896-104">Las consultas que utiliza el Monitor de replicación para realizar cálculos y recopilar datos se almacenan en caché y se actualizan periódicamente.</span><span class="sxs-lookup"><span data-stu-id="fe896-104">The queries that Replication Monitor uses to perform calculations and gather data are cached and refreshed on a periodic basis.</span></span> <span data-ttu-id="fe896-105">El almacenamiento en caché reduce el número de consultas y cálculos necesarios para ver diferentes páginas en el Monitor de replicación, y permite escalar la supervisión para varios usuarios.</span><span class="sxs-lookup"><span data-stu-id="fe896-105">Caching reduces the number of queries and calculations required as you view different pages in Replication Monitor and allows monitoring to scale well for multiple users.</span></span>  
  
 <span data-ttu-id="fe896-106">Un trabajo del Agente [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , el **Actualizador de supervisión de replicación para distribución**, controla la actualización de la caché.</span><span class="sxs-lookup"><span data-stu-id="fe896-106">Cache refresh is handled by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent job, the **Replication monitoring refresher for distribution**.</span></span> <span data-ttu-id="fe896-107">El trabajo se ejecuta continuamente, pero la programación de actualización de la caché se basa en esperar determinado tiempo después de la actualización anterior:</span><span class="sxs-lookup"><span data-stu-id="fe896-107">The job runs continuously, but the cache refresh schedule is based on waiting a certain amount time after the previous refresh:</span></span>  
  
-   <span data-ttu-id="fe896-108">Si hay cambios en el historial del agente desde que se creó la caché por última vez, el tiempo de espera es el menor de los siguientes: 4 segundos o el tiempo necesario para crear la caché anterior.</span><span class="sxs-lookup"><span data-stu-id="fe896-108">If there were agent history changes since the cache was last created, the wait time is the minimum of: 4 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
-   <span data-ttu-id="fe896-109">Si no hay cambios en el historial del agente desde que se creó la caché por última vez (aunque haya habido otros cambios), el tiempo de espera es el mayor de los siguientes: 30 segundos o el tiempo necesario para crear la caché anterior.</span><span class="sxs-lookup"><span data-stu-id="fe896-109">If there were no agent history changes since the cache was last created (there could have been other changes), the wait time is the maximum of: 30 seconds; or the amount of time taken to create the previous cache.</span></span>  
  
## <a name="refreshing-the-replication-monitor-user-interface"></a><span data-ttu-id="fe896-110">Actualizar la interfaz de usuario del Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="fe896-110">Refreshing the Replication Monitor User Interface</span></span>  
 <span data-ttu-id="fe896-111">La interfaz de usuario del Monitor de replicación se puede actualizar de varias formas:</span><span class="sxs-lookup"><span data-stu-id="fe896-111">The Replication Monitor user interface can be refreshed in the following ways:</span></span>  
  
-   <span data-ttu-id="fe896-112">La ventana principal del Monitor de replicación (y todas sus pestañas) se actualiza automáticamente, de manera predeterminada, cada cinco segundos.</span><span class="sxs-lookup"><span data-stu-id="fe896-112">The main Replication Monitor window (including all tabs), automatically refreshes by default every five seconds.</span></span> <span data-ttu-id="fe896-113">Las actualizaciones automáticas no obligan a actualizar la caché; la interfaz de usuario muestra la versión más reciente de los datos de la caché.</span><span class="sxs-lookup"><span data-stu-id="fe896-113">Automatic refreshes do not force a refresh of the cache; the user interface displays the most recent version of the data from the cache.</span></span> <span data-ttu-id="fe896-114">Puede personalizar la velocidad de actualización utilizada para todas las ventanas asociadas con un publicador si modifica la configuración de éste.</span><span class="sxs-lookup"><span data-stu-id="fe896-114">You can customize the refresh rate used for all windows associated with a Publisher by editing the Publisher settings.</span></span> <span data-ttu-id="fe896-115">También puede deshabilitar las actualizaciones automáticas para un publicador.</span><span class="sxs-lookup"><span data-stu-id="fe896-115">You can also disable automatic refreshes for a Publisher.</span></span>  
  
-   <span data-ttu-id="fe896-116">Las ventanas de detalles que se abren desde el Monitor de replicación no se actualizan automáticamente de manera predeterminada, con excepción de las ventanas relacionadas con las suscripciones de mezcla que se están sincronizando.</span><span class="sxs-lookup"><span data-stu-id="fe896-116">The detail windows that are launched from Replication Monitor are not automatically refreshed by default, with the exception of windows related to merge subscriptions that are synchronizing.</span></span> <span data-ttu-id="fe896-117">Si especifica que se actualicen automáticamente las ventanas de detalles, se actualizarán con la misma programación que la ventana principal del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="fe896-117">If you specify that detail windows should automatically refresh, they refresh on the same schedule as the main Replication Monitor window.</span></span>  
  
-   <span data-ttu-id="fe896-118">Todas las ventanas se pueden actualizar manualmente presionando F5, o haciendo clic con el botón secundario en un nodo del árbol del Monitor de replicación y, después, haciendo clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="fe896-118">All windows can be manually refreshed by pressing F5 or by right-clicking a node in the Replication Monitor tree and clicking **Refresh**.</span></span> <span data-ttu-id="fe896-119">La actualización manual fuerza una actualización de la caché.</span><span class="sxs-lookup"><span data-stu-id="fe896-119">Manual refreshes force a refresh of the cache.</span></span>  
  
 <span data-ttu-id="fe896-120">Para más información, vea [Actualizar datos en el Monitor de replicación](refresh-data-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="fe896-120">For more information, see [Refresh Data in Replication Monitor](refresh-data-in-replication-monitor.md).</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="fe896-121">Consideraciones de rendimiento</span><span class="sxs-lookup"><span data-stu-id="fe896-121">Performance Considerations</span></span>  
 <span data-ttu-id="fe896-122">A pesar de que el Monitor de replicación está diseñado para ejecutarse de forma eficaz, debe tener en cuenta los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="fe896-122">Although Replication Monitor is designed to run efficiently, be aware of the following:</span></span>  
  
-   <span data-ttu-id="fe896-123">Si tiene un gran número de publicaciones o suscripciones, configure una programación de actualización automática menos frecuente para la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="fe896-123">If you have a large number of publications or subscriptions, consider setting a less frequent automatic refresh schedule for the user interface.</span></span>  
  
-   <span data-ttu-id="fe896-124">Evite ejecutar simultáneamente varias instancias del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="fe896-124">Avoid concurrently running multiple instances of Replication Monitor.</span></span>  
  
-   <span data-ttu-id="fe896-125">Evite registrar un gran número de distribuidores y configurar el Monitor de replicación para que se conecte automáticamente a todos ellos.</span><span class="sxs-lookup"><span data-stu-id="fe896-125">Avoid registering a large number of Distributors and setting Replication Monitor to automatically connect to all of them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe896-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fe896-126">See Also</span></span>  
 <span data-ttu-id="fe896-127">[Ejecutar trabajos de mantenimiento de replicación &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="fe896-127">[Run Replication Maintenance Jobs &#40;SQL Server Management Studio&#41;](../../../ssms/sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="fe896-128">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="fe896-128">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
