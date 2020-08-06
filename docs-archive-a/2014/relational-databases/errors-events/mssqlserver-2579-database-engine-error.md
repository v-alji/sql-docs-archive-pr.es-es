---
title: MSSQLSERVER_2579 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2579 (Database Engine error)
ms.assetid: 8f929d69-8eb4-4fe9-be52-b9680a7820db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e68cd090ff9d20b14b3456dcda66496fc2bc02d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675899"
---
# <a name="mssqlserver_2579"></a><span data-ttu-id="74249-102">MSSQLSERVER_2579</span><span class="sxs-lookup"><span data-stu-id="74249-102">MSSQLSERVER_2579</span></span>
    
## <a name="details"></a><span data-ttu-id="74249-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="74249-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74249-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="74249-104">Product Name</span></span>|<span data-ttu-id="74249-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="74249-105">SQL Server</span></span>|  
|<span data-ttu-id="74249-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="74249-106">Event ID</span></span>|<span data-ttu-id="74249-107">2579</span><span class="sxs-lookup"><span data-stu-id="74249-107">2579</span></span>|  
|<span data-ttu-id="74249-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="74249-108">Event Source</span></span>|<span data-ttu-id="74249-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="74249-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="74249-110">Componente</span><span class="sxs-lookup"><span data-stu-id="74249-110">Component</span></span>|<span data-ttu-id="74249-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="74249-111">SQLEngine</span></span>|  
|<span data-ttu-id="74249-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="74249-112">Symbolic Name</span></span>|<span data-ttu-id="74249-113">DBCC_EXTENT_OUT_OF_RANGE</span><span class="sxs-lookup"><span data-stu-id="74249-113">DBCC_EXTENT_OUT_OF_RANGE</span></span>|  
|<span data-ttu-id="74249-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="74249-114">Message Text</span></span>|<span data-ttu-id="74249-115">Error de tabla: la extensión P_ID del id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE) está fuera del intervalo de esta base de datos.</span><span class="sxs-lookup"><span data-stu-id="74249-115">Table error: Extent P_ID in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) is beyond the range of this database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="74249-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="74249-116">Explanation</span></span>  
 <span data-ttu-id="74249-117">*P_ID* es un Id. de página con el formato *(filenum:pageinfile)* .</span><span class="sxs-lookup"><span data-stu-id="74249-117">*P_ID* is a PageID of the form *(filenum:pageinfile)*.</span></span> <span data-ttu-id="74249-118">El valor de *pageinfile* de esta extensión es mayor que el tamaño físico de *filenum* en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="74249-118">The *pageinfile* of this extent is greater than the physical size of the file (*filenum)* of the database.</span></span> <span data-ttu-id="74249-119">La extensión se marca como asignada en una página IAM para el Id. de unidad de asignación indicado.</span><span class="sxs-lookup"><span data-stu-id="74249-119">The extent is marked as being allocated in an IAM page for the indicated allocation unit ID.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74249-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="74249-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="74249-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="74249-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="74249-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="74249-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="74249-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="74249-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="74249-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="74249-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="74249-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="74249-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="74249-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="74249-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="74249-127">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="74249-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="74249-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="74249-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="74249-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="74249-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="74249-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="74249-130">Restore from Backup</span></span>  
 <span data-ttu-id="74249-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="74249-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="74249-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="74249-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="74249-133">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="74249-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="74249-134">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="74249-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="74249-135">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="74249-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="74249-136">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="74249-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="74249-137">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="74249-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="74249-138">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="74249-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="74249-139">La ejecución de REPAIR provocará la cancelación de la asignación de la extensión en la página IAM.</span><span class="sxs-lookup"><span data-stu-id="74249-139">Running REPAIR will cause the extent to be deallocated from the IAM page.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="74249-140">Esta reparación puede causar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="74249-140">This repair may cause data loss.</span></span>  
  
  
