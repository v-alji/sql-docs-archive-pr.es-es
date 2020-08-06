---
title: Cuadro de diálogo ' configuración del distribuidor ' | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.DistributorSettings.f1
helpviewer_keywords:
- Distributor Settings dialog box
ms.assetid: 8276a521-bdd1-4783-bdb6-7ab43499c0ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b864620f155e899868c95f58350f98e2b659c4e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663382"
---
# <a name="sql-server-replication-distributor-settings-dialog-box"></a><span data-ttu-id="16aff-102">Cuadro de diálogo Replicación de SQL Server ' configuración del distribuidor '</span><span class="sxs-lookup"><span data-stu-id="16aff-102">SQL Server Replication 'Distributor Settings' dialog box</span></span>
  <span data-ttu-id="16aff-103">El cuadro de diálogo **Configuración del distribuidor** le permite cambiar la configuración de los distribuidores que se han agregado al panel izquierdo del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="16aff-103">The **Distributor Settings** dialog box enables you to change settings for Distributors that were added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="16aff-104">Opciones</span><span class="sxs-lookup"><span data-stu-id="16aff-104">Options</span></span>  
 <span data-ttu-id="16aff-105">**Conectar automáticamente cuando se inicia el Monitor de replicación**</span><span class="sxs-lookup"><span data-stu-id="16aff-105">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="16aff-106">Seleccione esta opción para permitir que el Monitor de replicación se conecte al distribuidor y recupere información de estado.</span><span class="sxs-lookup"><span data-stu-id="16aff-106">Select to let Replication Monitor connect to the Distributor and retrieve status information.</span></span>  
  
 <span data-ttu-id="16aff-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="16aff-107">**Connection**</span></span>  
 <span data-ttu-id="16aff-108">Haga clic aquí para mostrar el cuadro de diálogo **Conectar con el servidor** .</span><span class="sxs-lookup"><span data-stu-id="16aff-108">Click to display the **Connect to Server** dialog box.</span></span> <span data-ttu-id="16aff-109">Esto le permite ver y cambiar las propiedades de conexión y las credenciales que el Monitor de replicación utiliza para conectarse al distribuidor.</span><span class="sxs-lookup"><span data-stu-id="16aff-109">This enables you to view and change the connection properties and credentials that Replication Monitor uses to connect to the Distributor.</span></span>  
  
 <span data-ttu-id="16aff-110">**Actualizar automáticamente el estado de este distribuidor y sus publicaciones**</span><span class="sxs-lookup"><span data-stu-id="16aff-110">**Automatically refresh the status of this Distributor and its publications**</span></span>  
 <span data-ttu-id="16aff-111">Seleccione esta opción para permitir que el Monitor de replicación actualice automáticamente el estado del distribuidor.</span><span class="sxs-lookup"><span data-stu-id="16aff-111">Select to let Replication Monitor automatically refresh the status for the Distributor.</span></span> <span data-ttu-id="16aff-112">Si esta opción está seleccionada, el Monitor de replicación sondea al distribuidor para obtener información de estado basada en el intervalo de sondeo establecido por la opción **Frecuencia de actualización** .</span><span class="sxs-lookup"><span data-stu-id="16aff-112">If this option is selected, Replication Monitor polls the Distributor for status information based on the polling interval set by the **Refresh rate** option.</span></span> <span data-ttu-id="16aff-113">Para obtener más información sobre la actualización en el Monitor de replicación, vea [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="16aff-113">For more information about refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="16aff-114">**Frecuencia de actualización**</span><span class="sxs-lookup"><span data-stu-id="16aff-114">**Refresh rate**</span></span>  
 <span data-ttu-id="16aff-115">Escriba un valor (en segundos) para especificar la frecuencia con la que el Monitor de replicación debe sondear el distribuidor en búsqueda de información de estado.</span><span class="sxs-lookup"><span data-stu-id="16aff-115">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="16aff-116">Los valores menores producen sondeos más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="16aff-116">Lower values result in more frequent polling.</span></span> <span data-ttu-id="16aff-117">Esto puede afectar al rendimiento del distribuidor si está supervisando muchos publicadores.</span><span class="sxs-lookup"><span data-stu-id="16aff-117">This can affect performance at the Distributor if you are monitoring many Publishers.</span></span> <span data-ttu-id="16aff-118">Se recomienda probar el sistema para determinar un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="16aff-118">We recommend that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="16aff-119">El valor **Frecuencia de actualización** también se utiliza si se selecciona **Actualizar automáticamente** en cualquiera de las ventanas de detalle del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="16aff-119">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="16aff-120">**Mostrar todos los publicadores de este distribuidor en el siguiente grupo**</span><span class="sxs-lookup"><span data-stu-id="16aff-120">**Show all Publishers of this Distributor in the following group**</span></span>  
 <span data-ttu-id="16aff-121">Seleccione un grupo de publicadores de la lista.</span><span class="sxs-lookup"><span data-stu-id="16aff-121">Select a Publisher group from the list.</span></span> <span data-ttu-id="16aff-122">El publicador se muestra en este grupo en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="16aff-122">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="16aff-123">Los grupos proporcionan una forma de organizar los publicadores y no afectan al funcionamiento de la replicación.</span><span class="sxs-lookup"><span data-stu-id="16aff-123">Groups provide a way for you to organize Publishers and do not affect how replication functions.</span></span>  
  
 <span data-ttu-id="16aff-124">**Nuevo grupo**</span><span class="sxs-lookup"><span data-stu-id="16aff-124">**New Group**</span></span>  
 <span data-ttu-id="16aff-125">Haga clic aquí para crear un nuevo grupo de publicadores.</span><span class="sxs-lookup"><span data-stu-id="16aff-125">Click to create a new Publisher group.</span></span> <span data-ttu-id="16aff-126">Un grupo de publicadores proporciona una forma cómoda de organizar publicadores dentro del Monitor de replicación.</span><span class="sxs-lookup"><span data-stu-id="16aff-126">A Publisher group provides a way for you to conveniently organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="16aff-127">Los grupos no afectan a la replicación de datos ni a la relación entre los servidores de una topología de replicación.</span><span class="sxs-lookup"><span data-stu-id="16aff-127">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16aff-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="16aff-128">See Also</span></span>  
 <span data-ttu-id="16aff-129">[Iniciar el Monitor de replicación](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="16aff-129">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="16aff-130">Supervisar la replicación</span><span class="sxs-lookup"><span data-stu-id="16aff-130">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
