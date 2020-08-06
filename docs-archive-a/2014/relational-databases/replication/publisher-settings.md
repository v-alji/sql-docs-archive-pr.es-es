---
title: Cuadro de diálogo "Configuración del publicador" de Replicación de SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publishersettings.f1
helpviewer_keywords:
- Publisher Settings dialog box
ms.assetid: 4fb70427-082d-4179-82a1-34b235accc43
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3a9a5ca5b0d7bfae895287708af159f3316e4474
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749709"
---
# <a name="sql-server-replication-publisher-settings-dialog-box"></a><span data-ttu-id="1b8e6-102">Cuadro de diálogo "Configuración del publicador" de Replicación de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b8e6-102">SQL Server Replication 'Publisher Settings' dialog box</span></span>
  <span data-ttu-id="1b8e6-103">El cuadro de diálogo **Configuración del publicador** permite cambiar la configuración de los publicadores que se han agregado al panel izquierdo del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-103">The **Publisher Settings** dialog box allows you to change settings for Publishers that have been added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1b8e6-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="1b8e6-104">Options</span></span>  
 <span data-ttu-id="1b8e6-105">**Conexión del publicador**</span><span class="sxs-lookup"><span data-stu-id="1b8e6-105">**Publisher Connection**</span></span>  
 <span data-ttu-id="1b8e6-106">Haga clic para abrir el cuadro de diálogo **Conectar al servidor** , que permite ver y cambiar las propiedades de la conexión y las credenciales que utiliza el Monitor de replicación para conectarse a un publicador.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-106">Click to launch the **Connect to Server** dialog box, which allows you to view and change the connection properties and credentials Replication Monitor uses to connect to a Publisher.</span></span>  
  
 <span data-ttu-id="1b8e6-107">**Conexión del distribuidor**</span><span class="sxs-lookup"><span data-stu-id="1b8e6-107">**Distributor Connection**</span></span>  
 <span data-ttu-id="1b8e6-108">Solo se muestra si el publicador utiliza un distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-108">Displayed only if the Publisher uses a remote Distributor.</span></span> <span data-ttu-id="1b8e6-109">Haga clic para abrir el cuadro de diálogo **Conectar al servidor** , que permite ver y cambiar las propiedades de la conexión y las credenciales que utiliza el Monitor de replicación para conectarse a un distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-109">Click to launch the **Connect to Server** dialog box, which allows you to view and change the connection properties and credentials Replication Monitor uses to connect to the remote Distributor.</span></span>  
  
 <span data-ttu-id="1b8e6-110">**Conectar automáticamente cuando se inicia el Monitor de replicación**</span><span class="sxs-lookup"><span data-stu-id="1b8e6-110">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="1b8e6-111">Active esta casilla para permitir que el Monitor de replicación se conecte automáticamente con el distribuidor y recupere información de estado para el publicador seleccionado en la cuadrícula de la parte superior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-111">Select to allow Replication Monitor to automatically connect to the Distributor and retrieve status information for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="1b8e6-112">Si esta casilla está desactivada, debe conectarse manualmente después de iniciar el Monitor de replicación: haga clic con el botón secundario en el publicador en el panel izquierdo del Monitor de replicación y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-112">If this checkbox is cleared, you must manually connect after launching Replication Monitor: right-click the Publisher in the left pane of Replication Monitor, and click **Connect**.</span></span>  
  
 <span data-ttu-id="1b8e6-113">**Actualizar automáticamente el estado de este publicador y sus publicaciones**</span><span class="sxs-lookup"><span data-stu-id="1b8e6-113">**Automatically refresh the status of this Publisher and its publications**</span></span>  
 <span data-ttu-id="1b8e6-114">Active esta casilla para permitir que el Monitor de replicación actualice automáticamente el estado del publicador seleccionado en la cuadrícula de la parte superior del cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-114">Select to allow Replication Monitor to automatically refresh status for the Publisher selected in the grid at the top of the dialog box.</span></span> <span data-ttu-id="1b8e6-115">Si esta opción está activada, el Monitor de replicación sondea el distribuidor buscando información de estado en el publicador y sus publicaciones.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-115">If this option is selected, Replication Monitor polls the Distributor for status information on the Publisher and its publications.</span></span> <span data-ttu-id="1b8e6-116">El intervalo de sondeo se establece mediante la opción **Frecuencia de actualización** .</span><span class="sxs-lookup"><span data-stu-id="1b8e6-116">The polling interval is set by the **Refresh rate** option.</span></span> <span data-ttu-id="1b8e6-117">Para obtener más información sobre la actualización en el Monitor de replicación, vea [Almacenamiento en caché, actualización y rendimiento del Monitor de replicación](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="1b8e6-117">For more information on refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="1b8e6-118">**Frecuencia de actualización**</span><span class="sxs-lookup"><span data-stu-id="1b8e6-118">**Refresh rate**</span></span>  
 <span data-ttu-id="1b8e6-119">Escriba un valor (en segundos) para especificar la frecuencia con la que el Monitor de replicación debe sondear el distribuidor en búsqueda de información de estado.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-119">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="1b8e6-120">Los valores más bajos producen un sondeo más frecuente, lo que puede afectar al rendimiento del distribuidor si se supervisa un gran número de publicadores.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-120">Lower values result in more frequent polling, which can affect performance at the Distributor if you are monitoring a large number of Publishers.</span></span> <span data-ttu-id="1b8e6-121">Se recomienda probar el sistema para determinar un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-121">It is recommended that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="1b8e6-122">El valor **Frecuencia de actualización** también se utiliza si se selecciona **Actualizar automáticamente** en cualquiera de las ventanas de detalle del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-122">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="1b8e6-123">**Mostrar estos publicadores en el siguiente grupo**</span><span class="sxs-lookup"><span data-stu-id="1b8e6-123">**Show this Publisher in the following group**</span></span>  
 <span data-ttu-id="1b8e6-124">Seleccione un grupo de publicadores de la lista.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-124">Select a Publisher group from the list.</span></span> <span data-ttu-id="1b8e6-125">El publicador se muestra en este grupo en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-125">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="1b8e6-126">Los grupos proporcionan una forma de organizar los publicadores y no afectan al funcionamiento de la replicación.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-126">Groups provide a way to organize Publishers and have no effect on how replication functions.</span></span>  
  
 <span data-ttu-id="1b8e6-127">**Nuevo grupo**</span><span class="sxs-lookup"><span data-stu-id="1b8e6-127">**New Group**</span></span>  
 <span data-ttu-id="1b8e6-128">Haga clic aquí para crear un nuevo grupo de publicadores.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-128">Click to create a new Publisher group.</span></span> <span data-ttu-id="1b8e6-129">Un grupo de publicadores proporciona una forma cómoda de organizar publicadores en el Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-129">A Publisher group provides a convenient way to organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="1b8e6-130">Los grupos no afectan a la replicación de datos ni a la relación entre los servidores de una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="1b8e6-130">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8e6-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b8e6-131">See Also</span></span>  
 <span data-ttu-id="1b8e6-132">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1b8e6-132">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="1b8e6-133">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="1b8e6-133">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  