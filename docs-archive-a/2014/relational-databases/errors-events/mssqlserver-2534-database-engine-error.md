---
title: MSSQLSERVER_2534 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2534 (Database Engine error)
ms.assetid: 121cf99d-0722-494c-be24-3369c1a0badc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 409c429f961cd8357bfa2e40663c33f3c1f2e36d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675916"
---
# <a name="mssqlserver_2534"></a><span data-ttu-id="21889-102">MSSQLSERVER_2534</span><span class="sxs-lookup"><span data-stu-id="21889-102">MSSQLSERVER_2534</span></span>
    
## <a name="details"></a><span data-ttu-id="21889-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="21889-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21889-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="21889-104">Product Name</span></span>|<span data-ttu-id="21889-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="21889-105">SQL Server</span></span>|  
|<span data-ttu-id="21889-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="21889-106">Event ID</span></span>|<span data-ttu-id="21889-107">2534</span><span class="sxs-lookup"><span data-stu-id="21889-107">2534</span></span>|  
|<span data-ttu-id="21889-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="21889-108">Event Source</span></span>|<span data-ttu-id="21889-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="21889-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="21889-110">Componente</span><span class="sxs-lookup"><span data-stu-id="21889-110">Component</span></span>|<span data-ttu-id="21889-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="21889-111">SQLEngine</span></span>|  
|<span data-ttu-id="21889-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="21889-112">Symbolic Name</span></span>|<span data-ttu-id="21889-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span><span class="sxs-lookup"><span data-stu-id="21889-113">DBCC_PAGE_ALLOCATED_TO_OTHER_OBJECT</span></span>|  
|<span data-ttu-id="21889-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="21889-114">Message Text</span></span>|<span data-ttu-id="21889-115">Error de tabla: la página P_ID, cuyo encabezado indica que está asignada al id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE), está asignada mediante otro objeto.</span><span class="sxs-lookup"><span data-stu-id="21889-115">Table error: Page P_ID, whose header indicates it as being allocated to object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), is allocated by another object.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="21889-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="21889-116">Explanation</span></span>  
 <span data-ttu-id="21889-117">El encabezado de la página contiene el Id. de unidad de asignación, *A_ID*, pero ninguna de las páginas IAM (Mapa de asignación de índices) de esa unidad de asignación asigna la página.</span><span class="sxs-lookup"><span data-stu-id="21889-117">The header of the page contains the allocation unit ID, *A_ID*, but none of the Index Allocation Map (IAM) pages of that allocation unit allocates the page.</span></span> <span data-ttu-id="21889-118">Por tanto, el encabezado de la página contiene un Id. de unidad de asignación incorrecto y la página tendrá un error de coincidencia MSSQLServer_2533 que corresponde al Id. de unidad de asignación al que la página está realmente asignada.</span><span class="sxs-lookup"><span data-stu-id="21889-118">Therefore, the header of the page contains the wrong allocation unit ID, and the page will have a matching MSSQLServer_2533 error that corresponds to the allocation unit ID to which the page is actually allocated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21889-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="21889-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="21889-120">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="21889-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="21889-121">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="21889-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="21889-122">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="21889-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="21889-123">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="21889-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="21889-124">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="21889-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="21889-125">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="21889-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="21889-126">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="21889-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="21889-127">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="21889-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="21889-128">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="21889-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="21889-129">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="21889-129">Restore from Backup</span></span>  
 <span data-ttu-id="21889-130">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="21889-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="21889-131">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="21889-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="21889-132">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="21889-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="21889-133">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="21889-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="21889-134">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="21889-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="21889-135">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="21889-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="21889-136">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="21889-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="21889-137">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="21889-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="21889-138">REPAIR vuelve a generar el índice (si existe).</span><span class="sxs-lookup"><span data-stu-id="21889-138">REPAIR will rebuild the index if an index exists.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="21889-139">Al ejecutar REPAIR para el error de coincidencia [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md), se cancela la asignación de la página antes de la reconstrucción.</span><span class="sxs-lookup"><span data-stu-id="21889-139">Running REPAIR for the matching [MSSQLSERVER_2533](mssqlserver-2533-database-engine-error.md) error deallocates the page before the rebuild.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="21889-140">Esta reparación puede causar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="21889-140">This repair may cause data loss.</span></span>  
  
  
