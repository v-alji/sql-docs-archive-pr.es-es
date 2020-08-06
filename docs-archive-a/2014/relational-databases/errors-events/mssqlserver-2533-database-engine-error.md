---
title: MSSQLSERVER_2533 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2533 (Database Engine error)
ms.assetid: 0418352c-0ab2-4dc7-b8b9-5c3bad94560c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1eb3e2780693a3a0ffed21ce7b9d7887615536c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745773"
---
# <a name="mssqlserver_2533"></a><span data-ttu-id="b08c9-102">MSSQLSERVER_2533</span><span class="sxs-lookup"><span data-stu-id="b08c9-102">MSSQLSERVER_2533</span></span>
    
## <a name="details"></a><span data-ttu-id="b08c9-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b08c9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b08c9-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b08c9-104">Product Name</span></span>|<span data-ttu-id="b08c9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b08c9-105">SQL Server</span></span>|  
|<span data-ttu-id="b08c9-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b08c9-106">Event ID</span></span>|<span data-ttu-id="b08c9-107">2533</span><span class="sxs-lookup"><span data-stu-id="b08c9-107">2533</span></span>|  
|<span data-ttu-id="b08c9-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b08c9-108">Event Source</span></span>|<span data-ttu-id="b08c9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b08c9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b08c9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b08c9-110">Component</span></span>|<span data-ttu-id="b08c9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b08c9-111">SQLEngine</span></span>|  
|<span data-ttu-id="b08c9-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b08c9-112">Symbolic Name</span></span>|<span data-ttu-id="b08c9-113">DBCC_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="b08c9-113">DBCC_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="b08c9-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b08c9-114">Message Text</span></span>|<span data-ttu-id="b08c9-115">Error de tabla: no se vio la página P_ID asignada al id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="b08c9-115">Table error: Page P_ID allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) was not seen.</span></span> <span data-ttu-id="b08c9-116">La página puede no ser válida o puede tener un Id. de unidad de asignación incorrecto en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="b08c9-116">Page may be invalid or have incorrect alloc unit ID in its header.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b08c9-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="b08c9-117">Explanation</span></span>  
 <span data-ttu-id="b08c9-118">Se ha asignado una página al Id. de unidad de asignación, *A_ID*, pero este Id. de unidad de asignación no se encuentra en el encabezado de la página.</span><span class="sxs-lookup"><span data-stu-id="b08c9-118">A page is allocated to the allocation unit ID, *A_ID*, but this allocation unit ID is not in the header of the page.</span></span> <span data-ttu-id="b08c9-119">El encabezado tiene un identificador de unidad de asignación diferente.</span><span class="sxs-lookup"><span data-stu-id="b08c9-119">The header has a different allocation unit ID.</span></span> <span data-ttu-id="b08c9-120">Si dicho identificador en el encabezado de la página corresponde a un objeto válido, la página puede tener un error de coincidencia MSSQLEngine_2534.</span><span class="sxs-lookup"><span data-stu-id="b08c9-120">If the allocation unit ID in the header of the page is for a valid object, the page may have a matching MSSQLEngine_2534 error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b08c9-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b08c9-121">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b08c9-122">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="b08c9-122">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b08c9-123">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="b08c9-123">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b08c9-124">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="b08c9-124">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b08c9-125">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="b08c9-125">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b08c9-126">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="b08c9-126">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b08c9-127">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="b08c9-127">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b08c9-128">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="b08c9-128">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b08c9-129">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="b08c9-129">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b08c9-130">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b08c9-130">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b08c9-131">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b08c9-131">Restore from Backup</span></span>  
 <span data-ttu-id="b08c9-132">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b08c9-132">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b08c9-133">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b08c9-133">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b08c9-134">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="b08c9-134">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="b08c9-135">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="b08c9-135">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="b08c9-136">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="b08c9-136">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b08c9-137">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="b08c9-137">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="b08c9-138">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="b08c9-138">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="b08c9-139">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="b08c9-139">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="b08c9-140">REPAIR cancelará la asignación de la página.</span><span class="sxs-lookup"><span data-stu-id="b08c9-140">REPAIR will deallocate the page.</span></span> <span data-ttu-id="b08c9-141">Si la página estaba en una unidad de asignación de datos de manera consecutiva, el índice, si existe, se volverá a generar.</span><span class="sxs-lookup"><span data-stu-id="b08c9-141">If the page was from an in-row data allocation unit, the index, if one exists, will be rebuilt.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b08c9-142">Esta reparación puede causar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="b08c9-142">This repair may cause data loss.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b08c9-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b08c9-143">See Also</span></span>  
 [<span data-ttu-id="b08c9-144">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="b08c9-144">MSSQLSERVER_2534</span></span>](mssqlserver-2534-database-engine-error.md)  
  
  
