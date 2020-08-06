---
title: Actualización de datos en el Monitor de replicación | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- refreshing data
ms.assetid: e9582244-7d00-45f4-be16-020a65c76a5e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2f097dea21b06540293e9b60b7de9315323b4168
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750729"
---
# <a name="refresh-data-in-replication-monitor"></a><span data-ttu-id="8a37b-102">Actualizar datos en el Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="8a37b-102">Refresh Data in Replication Monitor</span></span>
  <span data-ttu-id="8a37b-103">En el Monitor de replicación, la ventana principal y las ventanas de detalles (las ventanas que se inician desde la ventana principal) se pueden actualizar automática o manualmente.</span><span class="sxs-lookup"><span data-stu-id="8a37b-103">In Replication Monitor, the main window and detail windows (those windows launched from the main window) can be refreshed automatically or manually.</span></span> <span data-ttu-id="8a37b-104">Para actualizar una ventana manualmente, presione F5.</span><span class="sxs-lookup"><span data-stu-id="8a37b-104">To refresh a window manually, press F5.</span></span> <span data-ttu-id="8a37b-105">De manera predeterminada, la ventana principal se actualiza automáticamente cada cinco segundos; este valor se puede personalizar para cada publicador.</span><span class="sxs-lookup"><span data-stu-id="8a37b-105">By default, the main window is refreshed automatically every five seconds; the rate can be customized for each Publisher.</span></span>  
  
 <span data-ttu-id="8a37b-106">Los datos que se muestran en el Monitor de replicación se consultan desde una caché; para obtener información sobre la relación entre la caché y la actualización del Monitor de replicación, vea [Almacenamiento en caché, actualización y rendimiento del Monitor de replicación](caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="8a37b-106">The data displayed in Replication Monitor is queried from a cache; for information about the relationship between the cache and refreshing Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](caching-refresh-and-replication-monitor-performance.md).</span></span> <span data-ttu-id="8a37b-107">Para información sobre cómo iniciar el Monitor de replicación, vea [Iniciar el Monitor de replicación](start-the-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="8a37b-107">For information about starting Replication Monitor, see [Start the Replication Monitor](start-the-replication-monitor.md).</span></span>  
  
### <a name="to-set-refresh-options-for-replication-monitor"></a><span data-ttu-id="8a37b-108">Para establecer las opciones de actualización del Monitor de replicación</span><span class="sxs-lookup"><span data-stu-id="8a37b-108">To set refresh options for Replication Monitor</span></span>  
  
1.  <span data-ttu-id="8a37b-109">Haga clic con el botón secundario en el panel izquierdo del Monitor de replicación y, a continuación, haga clic en **Configuración del publicador**.</span><span class="sxs-lookup"><span data-stu-id="8a37b-109">Right-click a Publisher in the left pane of Replication Monitor, and then click **Publisher Settings**.</span></span>  
  
2.  <span data-ttu-id="8a37b-110">En el cuadro de diálogo **Configuración del publicador** , establezca las opciones **Actualizar automáticamente** y **Frecuencia de actualización** .</span><span class="sxs-lookup"><span data-stu-id="8a37b-110">In the **Publisher Settings** dialog box, set the **Auto refresh** and **Refresh rate** options.</span></span> <span data-ttu-id="8a37b-111">El valor establecido en **Actualizar automáticamente** afecta a la ventana principal del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="8a37b-111">The **Auto refresh** setting affects the main window in Replication Monitor.</span></span> <span data-ttu-id="8a37b-112">El valor establecido en **Frecuencia de actualización** también afecta a las ventanas de detalles cuya configuración se haya establecido de modo que se actualicen automáticamente (los cambios en la configuración solo afectan a las ventanas de detalles abiertas después del cambio).</span><span class="sxs-lookup"><span data-stu-id="8a37b-112">The **Refresh rate** setting also affects any detail windows that are set to refresh automatically (changes to the setting only affect the detail windows opened after the change).</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-specify-that-a-detail-window-should-automatically-refresh"></a><span data-ttu-id="8a37b-113">Para especificar que una ventana de detalles se actualice automáticamente</span><span class="sxs-lookup"><span data-stu-id="8a37b-113">To specify that a detail window should automatically refresh</span></span>  
  
1.  <span data-ttu-id="8a37b-114">Abra una ventana de detalles en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="8a37b-114">Open a detail window in Replication Monitor.</span></span> <span data-ttu-id="8a37b-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a37b-115">For example:</span></span>  
  
    1.  <span data-ttu-id="8a37b-116">Expanda un grupo de publicador en el panel izquierdo, expanda un publicador y, a continuación, haga clic en una publicación.</span><span class="sxs-lookup"><span data-stu-id="8a37b-116">Expand a Publisher group in the left pane, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="8a37b-117">Haga clic en la pestaña **Todas las suscripciones** .</span><span class="sxs-lookup"><span data-stu-id="8a37b-117">Click the **All Subscriptions** tab.</span></span>  
  
    3.  <span data-ttu-id="8a37b-118">Haga clic con el botón secundario en una suscripción y, a continuación, haga clic en **Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="8a37b-118">Right-click a subscription, and then click **View Details**.</span></span>  
  
2.  <span data-ttu-id="8a37b-119">En la ventana de detalles **Suscripción \<SubscriptionName>** , haga clic en **Acción** y, después, en **Actualizar automáticamente**.</span><span class="sxs-lookup"><span data-stu-id="8a37b-119">In the **Subscription \<SubscriptionName>** detail window, click **Action**, and then click **Auto Refresh**.</span></span> <span data-ttu-id="8a37b-120">La frecuencia de actualización es establece con el valor que se especifique en **Frecuencia de actualización** en el cuadro de diálogo **Configuración del publicador** .</span><span class="sxs-lookup"><span data-stu-id="8a37b-120">The refresh rate is determined by the **Refresh rate** setting in the **Publisher Settings** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a37b-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a37b-121">See Also</span></span>  
 [<span data-ttu-id="8a37b-122">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="8a37b-122">Monitoring Replication</span></span>](../monitoring-replication.md)  
  
  
