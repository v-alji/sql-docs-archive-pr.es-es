---
title: Agregar una instantánea al historial de informes (Administrador de informes) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
helpviewer_keywords:
- report history [Reporting Services], adding snapshots
- historical data [Reporting Services]
- snapshots [Reporting Services], adding report snapshots
- adding snapshots to report history
- report snapshots [Reporting Services], adding
ms.custom: ''
ms.date: 06/13/2017
ms.openlocfilehash: 84d4c264ab0b82fca2a34e6356b53113d63e6994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87674621"
---
# <a name="add-a-snapshot-to-report-history-report-manager"></a><span data-ttu-id="73bc4-102">Agregar una instantánea al historial de informes (Administrador de informes)</span><span class="sxs-lookup"><span data-stu-id="73bc4-102">Add a Snapshot to Report History (Report Manager)</span></span>

<span data-ttu-id="73bc4-103">El historial de informes es un conjunto de instantáneas de informe que se crean a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="73bc4-103">Report history is a collection of report snapshots that you create over time.</span></span> <span data-ttu-id="73bc4-104">Una instantánea de informe es un informe que contiene información de diseño y resultados de consultas que se recuperaron en un momento concreto.</span><span class="sxs-lookup"><span data-stu-id="73bc4-104">A report snapshot is a report that contains layout information and query results that were retrieved at a specific point in time.</span></span> <span data-ttu-id="73bc4-105">A diferencia de los informes a petición, que obtienen resultados de consulta actualizados cuando se seleccionan, las instantáneas de informe se procesan según una programación y luego se guardan en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="73bc4-105">Unlike on-demand reports, which get up-to-date query results when you select the report, report snapshots are processed on a schedule and then saved to a report server.</span></span> <span data-ttu-id="73bc4-106">Al seleccionar una instantánea de informe para su visualización, el servidor de informes recupera el informe almacenado en la base de datos del servidor de informes y muestra los datos y el diseño actualizados para el informe en el momento en que se creó la instantánea.</span><span class="sxs-lookup"><span data-stu-id="73bc4-106">When you select a report snapshot for viewing, the report server retrieves the stored report from the report server database and shows the data and layout that were current for the report at the time the snapshot was created.</span></span>  
  
<span data-ttu-id="73bc4-107">Las instantáneas de informe no se guardan con un formato de representación concreto.</span><span class="sxs-lookup"><span data-stu-id="73bc4-107">Report snapshots are not saved in a particular rendering format.</span></span> <span data-ttu-id="73bc4-108">En su lugar, las instantáneas de informe se representan en un formato de visualización final (como HTML) solo cuando un usuario o una aplicación lo solicita.</span><span class="sxs-lookup"><span data-stu-id="73bc4-108">Instead, report snapshots are rendered in a final viewing format (such as HTML) only when a user or an application requests it.</span></span> <span data-ttu-id="73bc4-109">La representación aplazada hace que las instantáneas sean portátiles.</span><span class="sxs-lookup"><span data-stu-id="73bc4-109">Deferred rendering makes a snapshot portable.</span></span> <span data-ttu-id="73bc4-110">El informe se puede representar con el formato correcto para el dispositivo o explorador web que lo solicita.</span><span class="sxs-lookup"><span data-stu-id="73bc4-110">The report can be rendered in the correct format for the requesting device or Web browser.</span></span>  
  
## <a name="to-manually-add-snapshots-to-report-history"></a><span data-ttu-id="73bc4-111">Para agregar manualmente instantáneas a un historial de informe</span><span class="sxs-lookup"><span data-stu-id="73bc4-111">To manually add snapshots to report history</span></span>

1. <span data-ttu-id="73bc4-112">En el Administrador de informes, vaya a la página **Contenido** , desplace el puntero sobre el elemento del que quiere ver el historial y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="73bc4-112">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>
  
2. <span data-ttu-id="73bc4-113">En el menú desplegable, haga clic en **Ver historial de informes**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-113">In the drop-down menu, click **View Report History**.</span></span>  
  
3. <span data-ttu-id="73bc4-114">Haga clic en **Nueva instantánea**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-114">Click **New Snapshot**.</span></span> <span data-ttu-id="73bc4-115">Se crea una nueva instantánea en la columna **Cuando se ejecuta** .</span><span class="sxs-lookup"><span data-stu-id="73bc4-115">A new snapshot is created in the **When Run** column.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="73bc4-116">Para ello, el administrador debe haber configurado el historial de informes con la opción **Permitir que el historial se cree manualmente**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-116">In order to do this, the report history must be configured by the administrator to **Allow history to be created manually**.</span></span> <span data-ttu-id="73bc4-117">Para obtener más información, vea [Limitar el historial de informe &#40;Administrador de informes&#41;](../reports/limit-report-history-report-manager.md).</span><span class="sxs-lookup"><span data-stu-id="73bc4-117">For more information, see [Limit Report History &#40;Report Manager&#41;](../reports/limit-report-history-report-manager.md).</span></span>

4. <span data-ttu-id="73bc4-118">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-118">Click **Apply**.</span></span>

## <a name="to-automatically-add-all-snapshots-to-report-history"></a><span data-ttu-id="73bc4-119">Para agregar automáticamente todas las instantáneas al historial de informes</span><span class="sxs-lookup"><span data-stu-id="73bc4-119">To automatically add all snapshots to report history</span></span>  
  
1. <span data-ttu-id="73bc4-120">Para un informe que ya está configurado para ejecutarse como una instantánea de ejecución de informes, puede establecer propiedades adicionales para guardar una copia de la instantánea en el historial del informe cada vez que se actualiza la instantánea.</span><span class="sxs-lookup"><span data-stu-id="73bc4-120">For a report that is already configured to run as a report execution snapshot, you can set additional properties to save a copy of the snapshot to report history each time the snapshot is refreshed.</span></span>  
  
2. <span data-ttu-id="73bc4-121">En el Administrador de informes, vaya a la página **Contenido** , desplace el puntero sobre el elemento del que quiere ver el historial y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="73bc4-121">In Report Manager, navigate to the **Contents** page, hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
3. <span data-ttu-id="73bc4-122">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-122">In the drop-down menu, click **Manage**.</span></span>  
  
4. <span data-ttu-id="73bc4-123">Haga clic en **Opciones de instantánea**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-123">Click **Snapshot Options**.</span></span>  
  
5. <span data-ttu-id="73bc4-124">Active la casilla correspondiente a **Almacenar todas las instantáneas de ejecución de informes en el historial**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-124">Select the check box for **Store all report execution snapshots in history**.</span></span>  
  
6. <span data-ttu-id="73bc4-125">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-125">Click **Apply**.</span></span>  
  
### <a name="to-automatically-add-snapshots-to-report-history-based-on-a-schedule"></a><span data-ttu-id="73bc4-126">Para agregar automáticamente instantáneas al historial del informe basándose en una programación</span><span class="sxs-lookup"><span data-stu-id="73bc4-126">To automatically add snapshots to report history based on a schedule</span></span>  
  
1. <span data-ttu-id="73bc4-127">En el Administrador de informes, vaya a la página **Contenido** , desplace el puntero sobre el elemento del que quiere ver el historial y haga clic en la flecha de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="73bc4-127">In Report Manager, navigate to the **Contents** page, and hover over the item that you want to view history for, and click the drop-down arrow.</span></span>  
  
2. <span data-ttu-id="73bc4-128">En el menú desplegable, haga clic en **Administrar**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-128">In the drop-down menu, click **Manage**.</span></span>  
  
3. <span data-ttu-id="73bc4-129">Haga clic en **Opciones de instantánea**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-129">Click **Snapshot Options**.</span></span>  
  
4. <span data-ttu-id="73bc4-130">Active la casilla correspondiente a **Utilizar la siguiente programación para agregar instantáneas al historial de informe**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-130">Select the check box for **Use the following schedule to add snapshots to report history**.</span></span> <span data-ttu-id="73bc4-131">Realice una de las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="73bc4-131">Perform one of the following:</span></span>  
  
    - <span data-ttu-id="73bc4-132">Seleccione **Programación específica del informe**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-132">Select **Report-specific schedule**.</span></span> <span data-ttu-id="73bc4-133">Rellene los detalles de la programación, seleccione las fechas de inicio y fin de la programación y, por último, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-133">Fill in the schedule details, select the start and end dates for the schedule, and then click **OK**.</span></span>  
  
    - <span data-ttu-id="73bc4-134">Seleccione **Programación compartida**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-134">Select **Shared schedule**.</span></span> <span data-ttu-id="73bc4-135">En la lista, seleccione la programación que prefiera.</span><span class="sxs-lookup"><span data-stu-id="73bc4-135">From the list, select the preferred schedule.</span></span>  
  
5. <span data-ttu-id="73bc4-136">Haga clic en **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="73bc4-136">Click **Apply**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bc4-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73bc4-137">See Also</span></span>

- [<span data-ttu-id="73bc4-138">Configurar las propiedades de ejecución de un informe &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="73bc4-138">Configure Execution Properties for a Report  &#40;Report Manager&#41;</span></span>](../reports/configure-execution-properties-for-a-report-report-manager.md)
- [<span data-ttu-id="73bc4-139">Abrir y cerrar un informe &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="73bc4-139">Open and Close a Report &#40;Report Manager&#41;</span></span>](../reports/open-and-close-a-report-report-manager.md)
- [<span data-ttu-id="73bc4-140">Limitar el historial de informes &#40;Administrador de informes&#41;</span><span class="sxs-lookup"><span data-stu-id="73bc4-140">Limit Report History &#40;Report Manager&#41;</span></span>](../reports/limit-report-history-report-manager.md)
- [<span data-ttu-id="73bc4-141">Programaciones</span><span class="sxs-lookup"><span data-stu-id="73bc4-141">Schedules</span></span>](../subscriptions/schedules.md)   
- [<span data-ttu-id="73bc4-142">Administrador de informes &#40;Modo nativo de SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="73bc4-142">Report Manager  &#40;SSRS Native Mode&#41;</span></span>](../report-manager-ssrs-native-mode.md)