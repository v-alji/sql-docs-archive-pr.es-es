---
title: Cuadro de diálogo ' agregar publicador '
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.addpublisher.f1
helpviewer_keywords:
- Add Publisher dialog box
ms.assetid: 4b57e298-655f-42c2-82bc-25cdad94a194
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c7e607c04aa74db7e5facf13051bf0c47c9dae0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663426"
---
# <a name="sql-server-replication-add-publisher-dialog-box"></a><span data-ttu-id="3b760-102">Replicación de SQL Server cuadro de diálogo ' agregar publicador '</span><span class="sxs-lookup"><span data-stu-id="3b760-102">SQL Server Replication 'Add Publisher' dialog box</span></span> 
  <span data-ttu-id="3b760-103">El cuadro de diálogo **Agregar publicador** permite agregar uno o varios publicadores en el panel izquierdo del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="3b760-103">The **Add Publisher** dialog box allows you to add to one or more Publishers to the left pane of Replication Monitor.</span></span> <span data-ttu-id="3b760-104">Después de agregar un publicador, selecciónelo en el panel izquierdo para mostrar información del publicador en el panel derecho.</span><span class="sxs-lookup"><span data-stu-id="3b760-104">After adding a Publisher, selecting the Publisher in the left pane shows information on the Publisher in the right pane.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3b760-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="3b760-105">Options</span></span>  
 <span data-ttu-id="3b760-106">**Add (Agregar)**</span><span class="sxs-lookup"><span data-stu-id="3b760-106">**Add**</span></span>  
 <span data-ttu-id="3b760-107">Haga clic en para seleccionar el tipo de publicador que se agregará a fin de abrir el cuadro de diálogo **Conectar al servidor** .</span><span class="sxs-lookup"><span data-stu-id="3b760-107">Click to select a type of Publisher to add, which launches the **Connect to Server** dialog box.</span></span> <span data-ttu-id="3b760-108">Las opciones son:</span><span class="sxs-lookup"><span data-stu-id="3b760-108">The options are:</span></span>  
  
-   <span data-ttu-id="3b760-109">**Agregar SQL Server publicador...**</span><span class="sxs-lookup"><span data-stu-id="3b760-109">**Add SQL Server Publisher...**</span></span>  
  
     <span data-ttu-id="3b760-110">Conéctese al publicador mediante el cuadro de diálogo **Conectar al servidor** .</span><span class="sxs-lookup"><span data-stu-id="3b760-110">Connect to the Publisher using the **Connect to Server** dialog box.</span></span>  
  
-   <span data-ttu-id="3b760-111">**Agregar publicador de Oracle...**</span><span class="sxs-lookup"><span data-stu-id="3b760-111">**Add Oracle Publisher...**</span></span>  
  
     <span data-ttu-id="3b760-112">Conéctese al distribuidor de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asociado con el publicador de Oracle mediante el cuadro de diálogo **Conectar al servidor**.</span><span class="sxs-lookup"><span data-stu-id="3b760-112">Connect to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor associated with the Oracle Publisher using the **Connect to Server** dialog box.</span></span>  
  
-   <span data-ttu-id="3b760-113">**Especificar un distribuidor y agregar sus publicadores...**</span><span class="sxs-lookup"><span data-stu-id="3b760-113">**Specify a Distributor and Add Its Publishers...**</span></span>  
  
     <span data-ttu-id="3b760-114">Conéctese al distribuidor de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] asociado con uno o varios publicadores mediante el cuadro de diálogo **Conectar al servidor** .</span><span class="sxs-lookup"><span data-stu-id="3b760-114">Connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor associated with one or more Publishers using the **Connect to Server** dialog box.</span></span>  
  
 <span data-ttu-id="3b760-115">Después de conectarse correctamente al publicador o al distribuidor, el nombre de cada publicador y su distribuidor se muestran en la cuadrícula de la parte superior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3b760-115">After successfully connecting to the Publisher or Distributor, the name of each Publisher and its Distributor are displayed in the grid at the top of the dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b760-116">El distribuidor y el publicador normalmente se ejecutan en la misma instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], pero el distribuidor puede ejecutarse en otra instancia (esta configuración se conoce como distribuidor remoto).</span><span class="sxs-lookup"><span data-stu-id="3b760-116">The Distributor and Publisher often run on the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the Distributor can run on another instance (this configuration is referred to as a remote Distributor).</span></span>  
  
 <span data-ttu-id="3b760-117">**Remove**</span><span class="sxs-lookup"><span data-stu-id="3b760-117">**Remove**</span></span>  
 <span data-ttu-id="3b760-118">Seleccione un publicador en la cuadrícula de la parte superior del cuadro de diálogo y haga clic en **Quitar** para quitar el publicador de la lista de publicadores que se van a agregar.</span><span class="sxs-lookup"><span data-stu-id="3b760-118">Select a Publisher in the grid at the top of the dialog box, and click **Remove** to remove the Publisher from the list of Publishers to be added.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3b760-119">Este botón no se puede utilizar para quitar un publicador que ya aparece en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="3b760-119">This button cannot be used to remove a Publisher that is already displayed in Replication Monitor.</span></span> <span data-ttu-id="3b760-120">Para quitar un publicador que ya aparece en Monitor de replicación, haga clic con el botón secundario en el publicador en el panel izquierdo y, a continuación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="3b760-120">To remove a Publisher that is already displayed right-click the Publisher in the left pane of Replication Monitor and click **Remove**.</span></span>  
  
 <span data-ttu-id="3b760-121">**Conectar automáticamente cuando se inicia el Monitor de replicación**</span><span class="sxs-lookup"><span data-stu-id="3b760-121">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="3b760-122">Active esta casilla para permitir que el Monitor de replicación se conecte automáticamente con el distribuidor y recupere información de estado para el publicador seleccionado en la cuadrícula de la parte superior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3b760-122">Select to allow Replication Monitor to automatically connect to the Distributor and retrieve status information for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="3b760-123">Si esta casilla está desactivada, debe conectarse manualmente después de iniciar el Monitor de replicación: haga clic con el botón secundario en el publicador en el panel izquierdo del Monitor de replicación y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="3b760-123">If this checkbox is cleared, you must manually connect after launching Replication Monitor: right-click the Publisher in the left pane of Replication Monitor, and click **Connect**.</span></span>  
  
 <span data-ttu-id="3b760-124">**Actualizar automáticamente el estado de este publicador y sus publicaciones**</span><span class="sxs-lookup"><span data-stu-id="3b760-124">**Automatically refresh the status of this Publisher and its publications**</span></span>  
 <span data-ttu-id="3b760-125">Active esta casilla para permitir que el Monitor de replicación actualice automáticamente el estado del publicador seleccionado en la cuadrícula de la parte superior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="3b760-125">Select to allow Replication Monitor to automatically refresh status for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="3b760-126">Si esta opción está activada, el Monitor de replicación sondea el distribuidor buscando información de estado en el publicador y sus publicaciones.</span><span class="sxs-lookup"><span data-stu-id="3b760-126">If this option is selected, Replication Monitor polls the Distributor for status information on the Publisher and its publications.</span></span> <span data-ttu-id="3b760-127">El intervalo de sondeo se establece mediante la opción **Frecuencia de actualización** .</span><span class="sxs-lookup"><span data-stu-id="3b760-127">The polling interval is set by the **Refresh rate** option.</span></span> <span data-ttu-id="3b760-128">Para obtener más información sobre la actualización en el Monitor de replicación, vea [Almacenamiento en caché, actualización y rendimiento del Monitor de replicación](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="3b760-128">For more information on refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="3b760-129">**Frecuencia de actualización**</span><span class="sxs-lookup"><span data-stu-id="3b760-129">**Refresh rate**</span></span>  
 <span data-ttu-id="3b760-130">Escriba un valor (en segundos) para especificar la frecuencia con la que el Monitor de replicación debe sondear el distribuidor en búsqueda de información de estado.</span><span class="sxs-lookup"><span data-stu-id="3b760-130">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="3b760-131">Los valores más bajos producen un sondeo más frecuente, lo que puede afectar al rendimiento del distribuidor si se supervisa un gran número de publicadores.</span><span class="sxs-lookup"><span data-stu-id="3b760-131">Lower values result in more frequent polling, which can affect performance at the Distributor if you are monitoring a large number of Publishers.</span></span> <span data-ttu-id="3b760-132">Se recomienda probar el sistema para determinar un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="3b760-132">It is recommended that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="3b760-133">El valor **Frecuencia de actualización** también se utiliza si se selecciona **Actualizar automáticamente** en cualquiera de las ventanas de detalle del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="3b760-133">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="3b760-134">**Mostrar estos publicadores en el siguiente grupo**</span><span class="sxs-lookup"><span data-stu-id="3b760-134">**Show this Publisher in the following group**</span></span>  
 <span data-ttu-id="3b760-135">Seleccione un grupo de publicadores de la lista.</span><span class="sxs-lookup"><span data-stu-id="3b760-135">Select a Publisher group from the list.</span></span> <span data-ttu-id="3b760-136">El publicador se muestra en este grupo en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="3b760-136">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="3b760-137">Los grupos proporcionan una forma de organizar los publicadores y no afectan al funcionamiento de la replicación.</span><span class="sxs-lookup"><span data-stu-id="3b760-137">Groups provide a way to organize Publishers and have no effect on how replication functions.</span></span> <span data-ttu-id="3b760-138">Si no hay ningún grupo definido o si desea crear uno nuevo, haga clic en **Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="3b760-138">If no groups are defined or you want to create a new one, click **New Group**.</span></span>  
  
 <span data-ttu-id="3b760-139">**Nuevo grupo**</span><span class="sxs-lookup"><span data-stu-id="3b760-139">**New Group**</span></span>  
 <span data-ttu-id="3b760-140">Haga clic aquí para crear un nuevo grupo de publicadores.</span><span class="sxs-lookup"><span data-stu-id="3b760-140">Click to create a new Publisher group.</span></span> <span data-ttu-id="3b760-141">Un grupo de publicadores proporciona una forma cómoda de organizar publicadores en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="3b760-141">A Publisher group provides a convenient way to organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="3b760-142">Los grupos no afectan a la replicación de datos ni a la relación entre los servidores de una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="3b760-142">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b760-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b760-143">See Also</span></span>  
 <span data-ttu-id="3b760-144">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="3b760-144">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="3b760-145">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="3b760-145">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
