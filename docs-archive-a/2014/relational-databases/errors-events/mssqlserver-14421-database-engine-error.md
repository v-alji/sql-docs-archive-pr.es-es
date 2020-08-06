---
title: MSSQLSERVER_14421 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 14421 (Database Engine error)
ms.assetid: 03e76d4a-d463-4673-8843-08e4ecaefe27
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d6bc793911797c334d87238ec46531f7afbf63ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675950"
---
# <a name="mssqlserver_14421"></a><span data-ttu-id="6f325-102">MSSQLSERVER_14421</span><span class="sxs-lookup"><span data-stu-id="6f325-102">MSSQLSERVER_14421</span></span>
    
## <a name="details"></a><span data-ttu-id="6f325-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="6f325-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6f325-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="6f325-104">Product Name</span></span>|<span data-ttu-id="6f325-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f325-105">SQL Server</span></span>|  
|<span data-ttu-id="6f325-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="6f325-106">Event ID</span></span>|<span data-ttu-id="6f325-107">14421</span><span class="sxs-lookup"><span data-stu-id="6f325-107">14421</span></span>|  
|<span data-ttu-id="6f325-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="6f325-108">Event Source</span></span>|<span data-ttu-id="6f325-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6f325-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6f325-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6f325-110">Component</span></span>|<span data-ttu-id="6f325-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6f325-111">SQLEngine</span></span>|  
|<span data-ttu-id="6f325-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="6f325-112">Symbolic Name</span></span>|<span data-ttu-id="6f325-113">SQLErrorNum14421</span><span class="sxs-lookup"><span data-stu-id="6f325-113">SQLErrorNum14421</span></span>|  
|<span data-ttu-id="6f325-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="6f325-114">Message Text</span></span>|<span data-ttu-id="6f325-115">La base de datos secundaria de trasvase de registros %s.%s tiene un umbral de restauración de %d minutos y no está sincronizada. No se ha realizado ninguna operación de restauración durante %d minutos.</span><span class="sxs-lookup"><span data-stu-id="6f325-115">The log shipping secondary database %s.%s has restore threshold of %d minutes and is out of sync. No restore was performed for %d minutes.</span></span> <span data-ttu-id="6f325-116">La latencia restaurada es de %d minutos.</span><span class="sxs-lookup"><span data-stu-id="6f325-116">Restored latency is %d minutes.</span></span> <span data-ttu-id="6f325-117">Compruebe la información del registro de agente y del monitor de trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="6f325-117">Check agent log and logshipping monitor information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6f325-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="6f325-118">Explanation</span></span>  
 <span data-ttu-id="6f325-119">Este mensaje indica que el trasvase de registros no está sincronizado más allá del umbral de restauración.</span><span class="sxs-lookup"><span data-stu-id="6f325-119">This message indicates that log shipping is out of synchronization beyond the restore threshold.</span></span> <span data-ttu-id="6f325-120">El umbral de restauración es la cantidad de minutos que pueden transcurrir entre las operaciones de restauración antes de que se genere un mensaje.</span><span class="sxs-lookup"><span data-stu-id="6f325-120">The restore threshold is the number of minutes that can elapse between restore operations before a message is generated.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="6f325-121">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="6f325-121">Possible Causes</span></span>  
 <span data-ttu-id="6f325-122">Este mensaje no indica necesariamente un problema en el trasvase de registros.</span><span class="sxs-lookup"><span data-stu-id="6f325-122">This message does not necessarily indicate a problem with log shipping.</span></span> <span data-ttu-id="6f325-123">En su lugar, puede indicar uno de los siguientes problemas:</span><span class="sxs-lookup"><span data-stu-id="6f325-123">Instead, this message might indicate one of the following problems:</span></span>  
  
-   <span data-ttu-id="6f325-124">El trabajo de restauración no está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6f325-124">The restore job is not running.</span></span>  
  
     <span data-ttu-id="6f325-125">Entre las posibles causas que impiden la ejecución del trabajo se encuentran: el servicio del Agente SQL Server en la instancia del servidor secundario no se está ejecutando, el trabajo está deshabilitado o la programación del trabajo ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="6f325-125">Possible causes of the job not running include the following: the SQL Server Agent service on the secondary server instance is not running, the job is disabled, or the schedule of the job has been changed.</span></span>  
  
-   <span data-ttu-id="6f325-126">Error en el trabajo de restauración.</span><span class="sxs-lookup"><span data-stu-id="6f325-126">The restore job is failing.</span></span>  
  
     <span data-ttu-id="6f325-127">Entre las posibles causas del error del trabajo se encuentran: la ruta de acceso de la carpeta de restauración no es válida, el disco está lleno o cualquier otro motivo por el que la instrucción RESTORE generó un error.</span><span class="sxs-lookup"><span data-stu-id="6f325-127">Possible causes of the job failing include the following: the restore folder path is not valid, the disk is full, or any other reason that the RESTORE statement could fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6f325-128">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="6f325-128">User Action</span></span>  
 <span data-ttu-id="6f325-129">Para solucionar el problema de este mensaje:</span><span class="sxs-lookup"><span data-stu-id="6f325-129">To troubleshoot this message:</span></span>  
  
-   <span data-ttu-id="6f325-130">Asegúrese de que el servicio del Agente SQL Server está en ejecución para la instancia del servidor secundario y que el trabajo de restauración de la base de datos secundaria está habilitado y programado para funcionar con la frecuencia adecuada.</span><span class="sxs-lookup"><span data-stu-id="6f325-130">Make sure that the SQL Server Agent service is running for the secondary server instance and that the restore job for this secondary database is enabled and is scheduled to run at the appropriate frequency.</span></span>  
  
-   <span data-ttu-id="6f325-131">Es posible que exista un error en el trabajo de restauración del servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="6f325-131">The restore job on the secondary server might be failing.</span></span> <span data-ttu-id="6f325-132">En este caso, compruebe el historial de trabajos del trabajo de restauración para buscar la causa.</span><span class="sxs-lookup"><span data-stu-id="6f325-132">In this case, check the job history for the restore job to look for the cause.</span></span>  
  
-   <span data-ttu-id="6f325-133">Es posible que el trabajo de restauración del trasvase de registros, que se ejecuta en la instancia del servidor secundario, no pueda conectarse a la instancia del servidor de supervisión para actualizar la tabla **log_shipping_monitor_secondary**.</span><span class="sxs-lookup"><span data-stu-id="6f325-133">The log shipping restore job, which runs on the secondary server instance, might not be able to connect to the monitor server instance to update the **log_shipping_monitor_secondary** table.</span></span> <span data-ttu-id="6f325-134">Esto puede deberse a un problema de autenticación entre la instancia del servidor de supervisión y la instancia del servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="6f325-134">This might be caused by an authentication problem between the monitor server instance and the secondary server instance.</span></span>  
  
-   <span data-ttu-id="6f325-135">Es posible que el umbral de alerta de la copia de seguridad tenga un valor incorrecto.</span><span class="sxs-lookup"><span data-stu-id="6f325-135">The backup alert threshold might have an incorrect value.</span></span> <span data-ttu-id="6f325-136">Lo ideal sería establecer este valor en el triple de la frecuencia del trabajo de restauración.</span><span class="sxs-lookup"><span data-stu-id="6f325-136">Ideally, this value is set to at least three times the frequency of the restore job.</span></span> <span data-ttu-id="6f325-137">Si cambia la frecuencia del trabajo de restauración después de configurar y poner en funcionamiento el trasvase de registros, debe actualizar en consecuencia el valor del umbral de alerta de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6f325-137">If you change the frequency of the restore job after log shipping is configured and functional, you must update the value of the backup alert threshold accordingly.</span></span>  
  
-   <span data-ttu-id="6f325-138">Cuando la instancia del servidor de supervisión se desconecta y se vuelve a conectar posteriormente, la tabla **log_shipping_monitor_secondary** no se actualiza con los valores actuales antes de que se ejecute el trabajo del mensaje de alerta.</span><span class="sxs-lookup"><span data-stu-id="6f325-138">When the monitor server instance goes offline and then comes back online, the **log_shipping_monitor_secondary** table is not updated with the current values before the alert message job runs.</span></span> <span data-ttu-id="6f325-139">El error 14421 se puede generar cuando un trabajo de restauración concluye correctamente y se muestra: "No se pudo encontrar un archivo de copia de seguridad de registros que se pudiera aplicar a la base de datos secundaria."</span><span class="sxs-lookup"><span data-stu-id="6f325-139">Error 14421 can be raised when a restore job succeeds with, "Could not find a log backup file that could be applied to secondary database."</span></span> <span data-ttu-id="6f325-140">Cuando esto sucede, no se actualiza la hora de la restauración.</span><span class="sxs-lookup"><span data-stu-id="6f325-140">When this occurs, the restore time is not updated.</span></span> <span data-ttu-id="6f325-141">Es posible que la causa del error sea, en este caso, un problema en el trabajo de copia.</span><span class="sxs-lookup"><span data-stu-id="6f325-141">The cause of the error in this case might be an issue with the copy job.</span></span>  
  
     <span data-ttu-id="6f325-142">Para actualizar las tablas de supervisión con los últimos datos de la base de datos secundaria, ejecute **sp_refresh_log_shipping_monitor** en la instancia del servidor secundario.</span><span class="sxs-lookup"><span data-stu-id="6f325-142">To update the monitor tables with the latest data for the secondary database, run **sp_refresh_log_shipping_monitor** on the secondary server instance.</span></span>  
  
-   <span data-ttu-id="6f325-143">La fecha o la hora es incorrecta en la instancia del servidor de supervisión o secundario.</span><span class="sxs-lookup"><span data-stu-id="6f325-143">On the secondary or monitor server instance, the date or time is incorrect.</span></span> <span data-ttu-id="6f325-144">Esto puede generar también mensajes de alerta.</span><span class="sxs-lookup"><span data-stu-id="6f325-144">This may also generate alert messages.</span></span> <span data-ttu-id="6f325-145">Es posible que la fecha o la hora del sistema se haya modificado en uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="6f325-145">Possibly the system date or time was modified on the one of them.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6f325-146">El hecho de que existan diferentes zonas horarias en las dos instancias de servidor no debería causar problemas.</span><span class="sxs-lookup"><span data-stu-id="6f325-146">Different time zones for the two server instances should not cause a problem.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f325-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f325-147">See Also</span></span>  
 <span data-ttu-id="6f325-148">[log_shipping_monitor_secondary &#40;&#41;de Transact-SQL](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6f325-148">[log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="6f325-149">[Acerca del trasvase de registros &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="6f325-149">[About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="6f325-150">[sp_help_log_shipping_monitor_secondary &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6f325-150">[sp_help_log_shipping_monitor_secondary &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql) </span></span>  
 <span data-ttu-id="6f325-151">[sp_refresh_log_shipping_monitor &#40;&#41;de Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6f325-151">[sp_refresh_log_shipping_monitor &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql) </span></span>  
 [<span data-ttu-id="6f325-152">Acerca del trasvase de registros &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6f325-152">About Log Shipping &#40;SQL Server&#41;</span></span>](../../database-engine/log-shipping/about-log-shipping-sql-server.md)  
  
  
