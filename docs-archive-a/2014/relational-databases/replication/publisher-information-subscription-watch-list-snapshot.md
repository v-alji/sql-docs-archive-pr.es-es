---
title: Información del publicador, lista de supervisión de suscripciones (publicación de instantáneas, SQL Server 2005 y versiones posteriores) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publisherinfo.subscriptionssummary.snapshot.f1
ms.assetid: 2ebeee62-7f54-4c77-9d37-15708bc5cc23
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ea44958c81465570c036ab7dd83247fb55652f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746245"
---
# <a name="publisher-information-subscription-watch-list-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="29bff-102">Información de publicador, Lista de supervisión de suscripciones (Publicación de instantáneas, SQL Server 2005 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="29bff-102">Publisher Information, Subscription Watch List (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="29bff-103">La pestaña **Lista de supervisión de suscripciones** está disponible para distribuidores que ejecutan [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] y versiones posteriores; está pensada para mostrar información sobre las suscripciones de todas las publicaciones disponibles en el publicador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="29bff-103">The **Subscription Watch List** tab is available for Distributors running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions; it is intended to display information on subscriptions from all publications available at the selected Publisher.</span></span> <span data-ttu-id="29bff-104">Puede filtrar la lista de suscripciones para ver errores, advertencias y las suscripciones que tienen un rendimiento bajo.</span><span class="sxs-lookup"><span data-stu-id="29bff-104">You can filter the list of subscriptions to see errors, warnings, and any poorly performing subscriptions.</span></span> <span data-ttu-id="29bff-105">Esta pestaña proporciona una ubicación única para que un administrador supervise toda la actividad de replicación en un publicador: el Monitor de replicación muestra todas las suscripciones que necesitan atención, basándose en el tipo de replicación seleccionado y en la opción elegida en el cuadro de lista desplegable **Mostrar** .</span><span class="sxs-lookup"><span data-stu-id="29bff-105">This tab provides a single location for an administrator to monitor all replication activity at a Publisher: Replication Monitor displays all subscriptions that require attention, based on the selected replication type and on the option chosen in the **Show** drop-down list box.</span></span> <span data-ttu-id="29bff-106">Puesto que los elementos mostrados en esta pestaña se basan en el rendimiento y el estado actual, las suscripciones se muestran en esta página solo si coinciden con la opción del cuadro de lista **Mostrar** en el momento actual.</span><span class="sxs-lookup"><span data-stu-id="29bff-106">Because the items displayed on this tab are based on current status and performance, subscriptions are displayed on this page only if they match the option in the **Show** list box at the current time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="29bff-107">Opciones</span><span class="sxs-lookup"><span data-stu-id="29bff-107">Options</span></span>  
 <span data-ttu-id="29bff-108">Para obtener información más detallada y las tareas de una suscripción, haga clic con el botón secundario en la fila de dicha suscripción y, a continuación, haga clic en una opción del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="29bff-108">For more detailed information and tasks related to a subscription, right-click the row for that subscription, and then click an option on the shortcut menu.</span></span> <span data-ttu-id="29bff-109">Para cambiar la manera que la cuadrícula muestra los datos, haga clic con el botón secundario en la cuadrícula y, a continuación, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="29bff-109">To change the way that the grid displays data, right-click the grid, and then click one of the following options:</span></span>  
  
-   <span data-ttu-id="29bff-110">**Ordenar**: ordene en una o más columnas en el cuadro de diálogo **Ordenar columnas** .</span><span class="sxs-lookup"><span data-stu-id="29bff-110">**Sort**: Sort on one or more columns in the **Sort Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="29bff-111">**Elegir columnas para mostrar**: seleccione las columnas que se mostrarán y el orden en el que se mostrarán en el cuadro de diálogo **Elegir columnas** .</span><span class="sxs-lookup"><span data-stu-id="29bff-111">**Choose Columns to Show**: Select which columns to display and the order in which to display them in the **Choose Columns** dialog box.</span></span>  
  
-   <span data-ttu-id="29bff-112">**Filtro**: filtre filas en la cuadrícula basándose en los valores de columna en el cuadro de diálogo **Configuración del filtro** .</span><span class="sxs-lookup"><span data-stu-id="29bff-112">**Filter**: Filter rows in the grid based on column values in the **Filter Settings** dialog box.</span></span>  
  
-   <span data-ttu-id="29bff-113">**Borrar filtro**: borre cualquier configuración de filtro para la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29bff-113">**Clear Filter**: Clear any filter settings for the grid.</span></span>  
  
 <span data-ttu-id="29bff-114">La configuración del filtro es específica de cada cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29bff-114">Filter settings are specific to each grid.</span></span> <span data-ttu-id="29bff-115">La selección y ordenación de las columnas se aplica a todas las cuadrículas del mismo tipo, como la cuadrícula de las publicaciones para cada Publicador.</span><span class="sxs-lookup"><span data-stu-id="29bff-115">Column selection and sorting are applied to all grids of the same type, such as the publications grid for each Publisher.</span></span>  
  
 <span data-ttu-id="29bff-116">**Mostrar suscripciones de instantáneas**</span><span class="sxs-lookup"><span data-stu-id="29bff-116">**Show Snapshot Subscriptions**</span></span>  
 <span data-ttu-id="29bff-117">Seleccione el tipo de suscripción (transaccional, de instantánea o de mezcla) que se mostrará para el publicador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="29bff-117">Select the type of subscriptions (transactional, snapshot, or merge) to display for the selected Publisher.</span></span>  
  
 <span data-ttu-id="29bff-118">**Mostrar**</span><span class="sxs-lookup"><span data-stu-id="29bff-118">**Show**</span></span>  
 <span data-ttu-id="29bff-119">Seleccione los estados de la suscripción que se mostrarán para el tipo de suscripción seleccionado.</span><span class="sxs-lookup"><span data-stu-id="29bff-119">Select the subscription states to display for the selected subscription type.</span></span> <span data-ttu-id="29bff-120">Por ejemplo, puede seleccionar mostrar solo aquellas suscripciones que tienen errores.</span><span class="sxs-lookup"><span data-stu-id="29bff-120">For example, you can select to display only those subscriptions that have an error.</span></span>  
  
 <span data-ttu-id="29bff-121">**Estado**</span><span class="sxs-lookup"><span data-stu-id="29bff-121">**Status**</span></span>  
 <span data-ttu-id="29bff-122">Muestra el estado de cada suscripción, que viene determinado por el estado del Agente de instantáneas o el Agente de distribución (se muestra el estado de prioridad más alto).</span><span class="sxs-lookup"><span data-stu-id="29bff-122">The status of each subscription, which is determined by the status of the Snapshot Agent or the Distribution Agent (the higher priority status is displayed).</span></span>  
  
 <span data-ttu-id="29bff-123">De forma predeterminada, la cuadrícula que contiene la información de la suscripción se ordena por la columna **Estado** .</span><span class="sxs-lookup"><span data-stu-id="29bff-123">By default, the grid containing subscription information is sorted by the **Status** column.</span></span> <span data-ttu-id="29bff-124">La siguiente lista muestra los valores de estado posibles y el criterio de ordenación de los valores (por ejemplo, los errores se muestran siempre en la parte superior de la cuadrícula).</span><span class="sxs-lookup"><span data-stu-id="29bff-124">The following list shows the possible status values and the sort order for the values (for example, errors are always shown at the top of the grid).</span></span>  
  
-   <span data-ttu-id="29bff-125">Error</span><span class="sxs-lookup"><span data-stu-id="29bff-125">Error</span></span>  
  
-   <span data-ttu-id="29bff-126">Con expiración en breve/Expirada</span><span class="sxs-lookup"><span data-stu-id="29bff-126">Expiring soon/Expired</span></span>  
  
-   <span data-ttu-id="29bff-127">Suscripción no inicializada</span><span class="sxs-lookup"><span data-stu-id="29bff-127">Uninitialized subscription</span></span>  
  
-   <span data-ttu-id="29bff-128">Reintentando comando con errores</span><span class="sxs-lookup"><span data-stu-id="29bff-128">Retrying failed command</span></span>  
  
-   <span data-ttu-id="29bff-129">Sincronizando</span><span class="sxs-lookup"><span data-stu-id="29bff-129">Synchronizing</span></span>  
  
-   <span data-ttu-id="29bff-130">No se están sincronizando</span><span class="sxs-lookup"><span data-stu-id="29bff-130">Not synchronizing</span></span>  
  
 <span data-ttu-id="29bff-131">El criterio de clasificación también determina qué valor se muestra si una misma suscripción presenta varios estados.</span><span class="sxs-lookup"><span data-stu-id="29bff-131">The sort order also determines which value is displayed if a given subscription is in more than one state.</span></span> <span data-ttu-id="29bff-132">Por ejemplo, si una suscripción tiene un error y expirará en breve, la columna **Estado** muestra **Error**.</span><span class="sxs-lookup"><span data-stu-id="29bff-132">For example, if a subscription has an error and is expiring soon, the **Status** column displays **Error**.</span></span>  
  
 <span data-ttu-id="29bff-133">Los valores de estado **Con expiración en breve/Expirado** y **Suscripción no inicializada** son advertencias.</span><span class="sxs-lookup"><span data-stu-id="29bff-133">The status values **Expiring soon/Expired** and **Uninitialized subscription** are warnings.</span></span> <span data-ttu-id="29bff-134">Cuando se muestra una advertencia, también aparece la columna **Estado** si un agente está ejecutándose.</span><span class="sxs-lookup"><span data-stu-id="29bff-134">When a warning is displayed, the **Status** column also displays if an agent is running.</span></span> <span data-ttu-id="29bff-135">Por ejemplo, el estado podría ser **En ejecución, Con expiración en breve/Expirado**.</span><span class="sxs-lookup"><span data-stu-id="29bff-135">For example, the status could be **Running, Expiring soon/Expired**.</span></span>  
  
 <span data-ttu-id="29bff-136">El valor de estado **Con expiración en breve/Expirado** solamente se muestra si se ha establecido un umbral.</span><span class="sxs-lookup"><span data-stu-id="29bff-136">The status value **Expiring soon/Expired** is displayed only if a threshold is set.</span></span> <span data-ttu-id="29bff-137">Para obtener más información, vea [Establecer umbrales y advertencias en el Monitor de replicación](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="29bff-137">For information on setting thresholds, see [Set Thresholds and Warnings in Replication Monitor](monitor/set-thresholds-and-warnings-in-replication-monitor.md).</span></span>  
  
 <span data-ttu-id="29bff-138">**Suscripción**</span><span class="sxs-lookup"><span data-stu-id="29bff-138">**Subscription**</span></span>  
 <span data-ttu-id="29bff-139">Muestra el nombre de cada suscripción, en el formato: *nombreDeSuscriptor: nombreDeBaseDeDatosDeSuscripción*.</span><span class="sxs-lookup"><span data-stu-id="29bff-139">The name of each subscription, in the form: *SubscriberName: SubscriptionDatabaseName*.</span></span>  
  
 <span data-ttu-id="29bff-140">**Publicación**</span><span class="sxs-lookup"><span data-stu-id="29bff-140">**Publication**</span></span>  
 <span data-ttu-id="29bff-141">Muestra el nombre de la publicación con la que se sincroniza una suscripción, en el formato: *nombreDeBaseDeDatosDePublicación: nombreDePublicación*.</span><span class="sxs-lookup"><span data-stu-id="29bff-141">The name of the publication with which a subscription synchronizes, in the form: *PublicationDatabaseName: PublicationName*.</span></span>  
  
 <span data-ttu-id="29bff-142">**Última sincronización**</span><span class="sxs-lookup"><span data-stu-id="29bff-142">**Last Synchronization**</span></span>  
 <span data-ttu-id="29bff-143">Indica la hora en que se ejecutó por última vez el Agente de distribución.</span><span class="sxs-lookup"><span data-stu-id="29bff-143">The time at which the Distribution Agent last ran.</span></span> <span data-ttu-id="29bff-144">Si la sincronización está en curso, se muestra **En curso** .</span><span class="sxs-lookup"><span data-stu-id="29bff-144">If synchronization is in progress, **In progress** is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bff-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29bff-145">See Also</span></span>  
 <span data-ttu-id="29bff-146">[Iniciar el monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="29bff-146">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="29bff-147">[Visualización de información y realización de tareas mediante el Monitor de replicación](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="29bff-147">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="29bff-148">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="29bff-148">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
