---
title: MSSQLSERVER_8993 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8993 (Database Engine error)
ms.assetid: 06aac110-a41c-4853-bc8e-a83e8535b8be
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5ee9497e9c4484fd885803c0feff20362a159ff2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662982"
---
# <a name="mssqlserver_8993"></a><span data-ttu-id="9cf0a-102">MSSQLSERVER_8993</span><span class="sxs-lookup"><span data-stu-id="9cf0a-102">MSSQLSERVER_8993</span></span>
    
## <a name="details"></a><span data-ttu-id="9cf0a-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9cf0a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9cf0a-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="9cf0a-104">Product Name</span></span>|<span data-ttu-id="9cf0a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9cf0a-105">SQL Server</span></span>|  
|<span data-ttu-id="9cf0a-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="9cf0a-106">Event ID</span></span>|<span data-ttu-id="9cf0a-107">8993</span><span class="sxs-lookup"><span data-stu-id="9cf0a-107">8993</span></span>|  
|<span data-ttu-id="9cf0a-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="9cf0a-108">Event Source</span></span>|<span data-ttu-id="9cf0a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9cf0a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9cf0a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9cf0a-110">Component</span></span>|<span data-ttu-id="9cf0a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9cf0a-111">SQLEngine</span></span>|  
|<span data-ttu-id="9cf0a-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9cf0a-112">Symbolic Name</span></span>|<span data-ttu-id="9cf0a-113">DBCC3_MISSING_FORWARDED_ROW</span><span class="sxs-lookup"><span data-stu-id="9cf0a-113">DBCC3_MISSING_FORWARDED_ROW</span></span>|  
|<span data-ttu-id="9cf0a-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9cf0a-114">Message Text</span></span>|<span data-ttu-id="9cf0a-115">El Id. de objeto O_ID, página de fila reenviada P_ID1, zona S_ID1 apunta a la página P_ID2, zona S_ID2.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-115">Object ID O_ID, forwarding row page P_ID1, slot S_ID1 points to page P_ID2, slot S_ID2.</span></span> <span data-ttu-id="9cf0a-116">No se encontró la fila reenviada.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-116">Did not encounter forwarded row.</span></span> <span data-ttu-id="9cf0a-117">Posible error de asignación.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-117">Possible allocation error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9cf0a-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="9cf0a-118">Explanation</span></span>  
 <span data-ttu-id="9cf0a-119">Una fila reenviada en un montón apunta a una fila reenviada que no existe.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-119">A forwarding row in a heap points to a nonexistent forwarded row.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9cf0a-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9cf0a-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="9cf0a-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="9cf0a-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="9cf0a-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="9cf0a-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="9cf0a-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="9cf0a-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="9cf0a-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="9cf0a-127">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="9cf0a-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="9cf0a-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="9cf0a-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9cf0a-130">Restore from Backup</span></span>  
 <span data-ttu-id="9cf0a-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="9cf0a-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="9cf0a-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="9cf0a-133">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="9cf0a-134">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="9cf0a-135">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="9cf0a-136">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="9cf0a-137">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="9cf0a-138">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="9cf0a-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="9cf0a-139">La fila reenviada se eliminará y volverán a generarse todos los índices no clúster.</span><span class="sxs-lookup"><span data-stu-id="9cf0a-139">The forwarding row will be deleted and any nonclustered indexes will be rebuilt.</span></span>  
  
  
