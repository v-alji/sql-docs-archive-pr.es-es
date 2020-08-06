---
title: MSSQLSERVER_2515 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2515 (Database Engine error)
ms.assetid: af93aa29-70c9-4923-90af-aafadb20c1c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 73b2d8b8ff01b97428ba6149f537d96044c6ae3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744717"
---
# <a name="mssqlserver_2515"></a><span data-ttu-id="479fb-102">MSSQLSERVER_2515</span><span class="sxs-lookup"><span data-stu-id="479fb-102">MSSQLSERVER_2515</span></span>
    
## <a name="details"></a><span data-ttu-id="479fb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="479fb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="479fb-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="479fb-104">Product Name</span></span>|<span data-ttu-id="479fb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="479fb-105">SQL Server</span></span>|  
|<span data-ttu-id="479fb-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="479fb-106">Event ID</span></span>|<span data-ttu-id="479fb-107">2515</span><span class="sxs-lookup"><span data-stu-id="479fb-107">2515</span></span>|  
|<span data-ttu-id="479fb-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="479fb-108">Event Source</span></span>|<span data-ttu-id="479fb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="479fb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="479fb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="479fb-110">Component</span></span>|<span data-ttu-id="479fb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="479fb-111">SQLEngine</span></span>|  
|<span data-ttu-id="479fb-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="479fb-112">Symbolic Name</span></span>|<span data-ttu-id="479fb-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span><span class="sxs-lookup"><span data-stu-id="479fb-113">DBCC_DIFF_MAP_OUT_OF_SYNC</span></span>|  
|<span data-ttu-id="479fb-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="479fb-114">Message Text</span></span>|<span data-ttu-id="479fb-115">Página P_ID, Id. de objeto O_ID, Id. de índice I_ID, Id. de partición PN_ID, Id. de unidad de asignación A_ID (tipo TYPE): se ha modificado, pero no está marcada como modificada en el mapa de bits de la copia de seguridad diferencial.</span><span class="sxs-lookup"><span data-stu-id="479fb-115">Page P_ID, object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID type TYPE has been modified but is not marked modified in the differential backup bitmap.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="479fb-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="479fb-116">Explanation</span></span>  
 <span data-ttu-id="479fb-117">La página especificada tiene un número de secuencia de registro (LSN) mayor que el LSN de referencia diferencial del BackupManager de la base de datos o el LSN de base diferencial del bloque de control de archivos del archivo, el que sea más reciente.</span><span class="sxs-lookup"><span data-stu-id="479fb-117">The page specified has a log sequence number (LSN) that is higher than the differential reference LSN in the BackupManager of the database, or the differential base LSN in the file control block of the file, whichever is more recent.</span></span> <span data-ttu-id="479fb-118">Sin embargo, la página no está marcada como modificada en el mapa de bits de la copia de seguridad diferencial.</span><span class="sxs-lookup"><span data-stu-id="479fb-118">However, the page is not marked as changed in the differential backup bitmap.</span></span>  
  
 <span data-ttu-id="479fb-119">Solo se incluirá una página por base de datos en el informe, ya que esta comprobación se realiza únicamente cuando se sabe que el mapa de bits diferencial está libre de errores.</span><span class="sxs-lookup"><span data-stu-id="479fb-119">Only one page per database will be reported, because this check is only performed when the differential bitmap is known to be error free.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="479fb-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="479fb-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="479fb-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="479fb-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="479fb-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="479fb-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="479fb-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="479fb-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="479fb-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="479fb-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="479fb-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="479fb-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="479fb-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="479fb-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="479fb-127">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="479fb-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="479fb-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="479fb-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="479fb-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="479fb-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="479fb-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="479fb-130">Restore from Backup</span></span>  
 <span data-ttu-id="479fb-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="479fb-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="479fb-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="479fb-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="479fb-133">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="479fb-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="479fb-134">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="479fb-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="479fb-135">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="479fb-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="479fb-136">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="479fb-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="479fb-137">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="479fb-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="479fb-138">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="479fb-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="479fb-139">La ejecución de REPAIR invalidará el mapa de bits diferencial.</span><span class="sxs-lookup"><span data-stu-id="479fb-139">Running REPAIR will invalidate the differential bitmap.</span></span> <span data-ttu-id="479fb-140">No se puede realizar una copia de seguridad diferencial hasta que se lleve a cabo una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="479fb-140">You cannot perform a differential backup until a full database backup is taken.</span></span> <span data-ttu-id="479fb-141">La copia de seguridad completa de la base de datos proporciona una línea base para la regeneración del mapa de bits diferencial.</span><span class="sxs-lookup"><span data-stu-id="479fb-141">The full database backup provides a baseline for the differential bitmap to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479fb-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="479fb-142">See Also</span></span>  
 <span data-ttu-id="479fb-143">[Crear una copia de seguridad completa de base de datos &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="479fb-143">[Create a Full Database Backup &#40;SQL Server&#41;](../backup-restore/create-a-full-database-backup-sql-server.md) </span></span>  
 [<span data-ttu-id="479fb-144">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="479fb-144">MSSQLSERVER_2516</span></span>](mssqlserver-2516-database-engine-error.md)  
  
  
