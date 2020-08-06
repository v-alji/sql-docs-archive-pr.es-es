---
title: Información de publicación, Todas las suscripciones (Publicación de instantáneas) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.allsubscriptions.snapshot.f1
ms.assetid: 7ce656c2-6e60-4625-8955-1daff641070c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 75eb85adae46481ddd4360f095c00060af5677fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673649"
---
# <a name="publication-information-all-subscriptions-snapshot-publication"></a><span data-ttu-id="507bd-102">Información de publicación, Todas las suscripciones (Publicación de instantáneas)</span><span class="sxs-lookup"><span data-stu-id="507bd-102">Publication Information, All Subscriptions (Snapshot Publication)</span></span>
  <span data-ttu-id="507bd-103">La pestaña **Todas las suscripciones** muestra información de todas las suscripciones a la publicación de instantáneas seleccionada.</span><span class="sxs-lookup"><span data-stu-id="507bd-103">The **All Subscriptions** tab displays information on all subscriptions to the selected snapshot publication.</span></span>  
  
## <a name="options"></a><span data-ttu-id="507bd-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="507bd-104">Options</span></span>  
 <span data-ttu-id="507bd-105">Para obtener información más detallada y las tareas de una suscripción, haga clic con el botón secundario en la fila de dicha suscripción y, a continuación, haga clic en una opción del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="507bd-105">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="507bd-106">Para cambiar la manera que la cuadrícula muestra los datos, haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="507bd-106">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="507bd-107">**Ordenar**: ordene en una o más columnas en el cuadro de diálogo **Ordenar columnas** .</span><span class="sxs-lookup"><span data-stu-id="507bd-107">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="507bd-108">**Elegir columnas para mostrar**: seleccione las columnas que se mostrarán y el orden en el que se mostrarán en el cuadro de diálogo **Elegir columnas** .</span><span class="sxs-lookup"><span data-stu-id="507bd-108">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="507bd-109">**Filtro**: filtre filas en la cuadrícula basándose en los valores de columna en el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="507bd-109">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="507bd-110">**Borrar filtro**: borre cualquier configuración de filtro para la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="507bd-110">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="507bd-111">La configuración del filtro es específica de cada cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="507bd-111">Filter settings are specific to each grid.</span></span> <span data-ttu-id="507bd-112">La selección y ordenación de las columnas se aplica a todas las cuadrículas del mismo tipo, como la cuadrícula de las publicaciones para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="507bd-112">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="507bd-113">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="507bd-113">**Show**</span></span>  
 <span data-ttu-id="507bd-114">Solo para [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="507bd-114">[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only.</span></span> <span data-ttu-id="507bd-115">Seleccione los estados de la suscripción que se mostrarán para el tipo de suscripción seleccionado.</span><span class="sxs-lookup"><span data-stu-id="507bd-115">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="507bd-116">Por ejemplo, puede seleccionar mostrar solo aquellas suscripciones que tienen errores.</span><span class="sxs-lookup"><span data-stu-id="507bd-116">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="507bd-117">**Estado**</span><span class="sxs-lookup"><span data-stu-id="507bd-117">**Status**</span></span>  
 <span data-ttu-id="507bd-118">Muestra el estado de cada suscripción, que viene determinado por el estado del Agente de instantáneas o el Agente de distribución (se muestra el estado de prioridad más alto).</span><span class="sxs-lookup"><span data-stu-id="507bd-118">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="507bd-119">De forma predeterminada, la cuadrícula que contiene la información de la suscripción se ordena por la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="507bd-119">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="507bd-120">La siguiente lista muestra los valores de estado posibles y el criterio de ordenación de los valores (por ejemplo, los errores se muestran siempre en la parte superior de la cuadrícula).</span><span class="sxs-lookup"><span data-stu-id="507bd-120">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="507bd-121">Error</span><span class="sxs-lookup"><span data-stu-id="507bd-121">Error</span></span>  
  
-   <span data-ttu-id="507bd-122">Con expiración en breve/Expirado (solo para[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="507bd-122">Expiring soon/Expired ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="507bd-123">Suscripción no inicializada (solo para[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="507bd-123">Uninitialized subscription ([!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions only)</span></span>  
  
-   <span data-ttu-id="507bd-124">Reintentando comando con errores</span><span class="sxs-lookup"><span data-stu-id="507bd-124">Retrying failed command</span></span>  
  
-   <span data-ttu-id="507bd-125">Sincronizando</span><span class="sxs-lookup"><span data-stu-id="507bd-125">Synchronizing</span></span>  
  
-   <span data-ttu-id="507bd-126">No se están sincronizando</span><span class="sxs-lookup"><span data-stu-id="507bd-126">Not synchronizing</span></span>  
  
 <span data-ttu-id="507bd-127">El criterio de clasificación también determina qué valor se muestra si una misma suscripción presenta varios estados.</span><span class="sxs-lookup"><span data-stu-id="507bd-127">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="507bd-128">Por ejemplo, si una suscripción tiene un error y expirará en breve, la columna **Estado** muestra **Error**.</span><span class="sxs-lookup"><span data-stu-id="507bd-128">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="507bd-129">Los valores de estado **Con expiración en breve/Expirado** y **Suscripción no inicializada** son advertencias.</span><span class="sxs-lookup"><span data-stu-id="507bd-129">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="507bd-130">Cuando se muestra una advertencia, también aparece la columna **Estado** si un agente está ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="507bd-130">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="507bd-131">Por ejemplo, el estado podría ser **En ejecución, Con expiración en breve/Expirado**.</span><span class="sxs-lookup"><span data-stu-id="507bd-131">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="507bd-132">El valor de estado **Con expiración en breve/Expirado** solamente se muestra si se ha establecido un umbral.</span><span class="sxs-lookup"><span data-stu-id="507bd-132">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="507bd-133">Para obtener más información, vea [Establecer umbrales y advertencias en el Monitor de replicación](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="507bd-133">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="507bd-134">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="507bd-134">**Subscription**</span></span>  
 <span data-ttu-id="507bd-135">Muestra el nombre de cada suscripción, en el formato: *nombreDeSuscriptor: nombreDeBaseDeDatosDeSuscripción*.</span><span class="sxs-lookup"><span data-stu-id="507bd-135">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="507bd-136">**Última sincronización**</span><span class="sxs-lookup"><span data-stu-id="507bd-136">**Last Synchronization**</span></span>  
 <span data-ttu-id="507bd-137">Indica la hora en que se ejecutó por última vez el Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="507bd-137">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="507bd-138">Si la sincronización está en curso, se muestra **En curso** .</span><span class="sxs-lookup"><span data-stu-id="507bd-138">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507bd-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="507bd-139">See Also</span></span>  
 <span data-ttu-id="507bd-140">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="507bd-140">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="507bd-141">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="507bd-141">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="507bd-142">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="507bd-142">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
