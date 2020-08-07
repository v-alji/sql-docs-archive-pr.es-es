---
title: Información de publicación, advertencias (publicación de instantáneas, SQL Server 2005 y versiones posteriores) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.snapshot.f1
ms.assetid: 7aa2eb52-b6b7-4dd3-8483-8ef00d9f0435
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3ae662a339e1e211ce4f46a588f4d7de65bf5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746914"
---
# <a name="publication-information-warnings-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="7d32e-102">Información de publicación, Advertencias (Publicación de instantáneas, SQL Server 2005 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="7d32e-102">Publication Information, Warnings (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="7d32e-103">La pestaña **Advertencias** está disponible para los distribuidores que ejecutan [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="7d32e-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="7d32e-104">La pestaña **Advertencias** permite realizar las siguientes tareas para la publicación seleccionada:</span><span class="sxs-lookup"><span data-stu-id="7d32e-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="7d32e-105">Habilitar advertencias.</span><span class="sxs-lookup"><span data-stu-id="7d32e-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="7d32e-106">Especificar umbrales asociados con las advertencias.</span><span class="sxs-lookup"><span data-stu-id="7d32e-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="7d32e-107">Definir alertas asociadas con advertencias.</span><span class="sxs-lookup"><span data-stu-id="7d32e-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="7d32e-108">Advertencias, umbrales y alertas</span><span class="sxs-lookup"><span data-stu-id="7d32e-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="7d32e-109">De forma predeterminada, el Monitor de replicación muestra advertencias de suscripciones no inicializadas: se muestra el estado **Suscripción no inicializada** como una advertencia en la columna **Estado** de las páginas que incluyen información de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="7d32e-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="7d32e-110">En las publicaciones de instantáneas también puede especificar que la expiración inminente de la suscripción genere una advertencia si configura la opción **Advertir si una suscripción expirará dentro del umbral**.</span><span class="sxs-lookup"><span data-stu-id="7d32e-110">For snapshot publications, you can also specify that imminent subscription expiration results in a warning by setting the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="7d32e-111">Si se alcanza o se supera el umbral especificado, se muestra el estado de la suscripción como **Con expiración en breve/Expirado** (a menos que tenga que mostrarse un problema con una prioridad superior).</span><span class="sxs-lookup"><span data-stu-id="7d32e-111">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="7d32e-112">Además de mostrar una advertencia en el Monitor de replicación, llegar a un umbral también puede desencadenar una alerta.</span><span class="sxs-lookup"><span data-stu-id="7d32e-112">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="7d32e-113">Para definir alertas, haga clic en **Configurar alertas** y proporcione información en el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="7d32e-113">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7d32e-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="7d32e-114">Options</span></span>  
 <span data-ttu-id="7d32e-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="7d32e-115">**Enabled**</span></span>  
 <span data-ttu-id="7d32e-116">Seleccione esta opción si desea habilitar una advertencia y especificar un umbral asociado.</span><span class="sxs-lookup"><span data-stu-id="7d32e-116">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="7d32e-117">**Warning (ADVERTENCIA)**</span><span class="sxs-lookup"><span data-stu-id="7d32e-117">**Warning**</span></span>  
 <span data-ttu-id="7d32e-118">Descripción de la advertencia asociada al umbral.</span><span class="sxs-lookup"><span data-stu-id="7d32e-118">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="7d32e-119">**Umbral**</span><span class="sxs-lookup"><span data-stu-id="7d32e-119">**Threshold**</span></span>  
 <span data-ttu-id="7d32e-120">Permite especificar un valor para el umbral.</span><span class="sxs-lookup"><span data-stu-id="7d32e-120">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="7d32e-121">**Configuración de alertas**</span><span class="sxs-lookup"><span data-stu-id="7d32e-121">**Configure Alerts**</span></span>  
 <span data-ttu-id="7d32e-122">Seleccione una fila en la cuadrícula **Advertencias** y haga clic en **Configurar alertas** para abrir el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="7d32e-122">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="7d32e-123">El cuadro de diálogo permite definir una alerta que se asociará al umbral y la advertencia seleccionados.</span><span class="sxs-lookup"><span data-stu-id="7d32e-123">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="7d32e-124">**Descartar cambios**</span><span class="sxs-lookup"><span data-stu-id="7d32e-124">**Discard Changes**</span></span>  
 <span data-ttu-id="7d32e-125">Haga clic para descartar los cambios realizados en las advertencias y los umbrales.</span><span class="sxs-lookup"><span data-stu-id="7d32e-125">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d32e-126">Hacer clic en **Descartar cambios** no afecta a las alertas definidas en el cuadro de diálogo **Configurar alertas de replicación** .</span><span class="sxs-lookup"><span data-stu-id="7d32e-126">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="7d32e-127">**Save Changes**</span><span class="sxs-lookup"><span data-stu-id="7d32e-127">**Save Changes**</span></span>  
 <span data-ttu-id="7d32e-128">Haga clic para guardar los cambios realizados en las advertencias y los umbrales.</span><span class="sxs-lookup"><span data-stu-id="7d32e-128">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d32e-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d32e-129">See Also</span></span>  
 <span data-ttu-id="7d32e-130">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="7d32e-130">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="7d32e-131">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="7d32e-131">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="7d32e-132">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="7d32e-132">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
