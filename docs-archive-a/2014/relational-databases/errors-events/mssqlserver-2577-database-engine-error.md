---
title: MSSQLSERVER_2577 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2577 (Database Engine error)
ms.assetid: f53256a2-2fb0-47fd-9ed9-c45389104145
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9e4b7b85f59ba721eae6b4a0ac8db1b2d288422d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675903"
---
# <a name="mssqlserver_2577"></a><span data-ttu-id="4d2af-102">MSSQLSERVER_2577</span><span class="sxs-lookup"><span data-stu-id="4d2af-102">MSSQLSERVER_2577</span></span>
    
## <a name="details"></a><span data-ttu-id="4d2af-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4d2af-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4d2af-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="4d2af-104">Product Name</span></span>|<span data-ttu-id="4d2af-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4d2af-105">SQL Server</span></span>|  
|<span data-ttu-id="4d2af-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4d2af-106">Event ID</span></span>|<span data-ttu-id="4d2af-107">2577</span><span class="sxs-lookup"><span data-stu-id="4d2af-107">2577</span></span>|  
|<span data-ttu-id="4d2af-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="4d2af-108">Event Source</span></span>|<span data-ttu-id="4d2af-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4d2af-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4d2af-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4d2af-110">Component</span></span>|<span data-ttu-id="4d2af-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4d2af-111">SQLEngine</span></span>|  
|<span data-ttu-id="4d2af-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4d2af-112">Symbolic Name</span></span>|<span data-ttu-id="4d2af-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span><span class="sxs-lookup"><span data-stu-id="4d2af-113">DBCC_IAM_CHAIN_SEQUENCE_OUT_OF_ORDER</span></span>|  
|<span data-ttu-id="4d2af-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4d2af-114">Message Text</span></span>|<span data-ttu-id="4d2af-115">Los números de secuencia de cadena no están ordenados en la cadena IAM (Mapa de asignación de índices) para el Id. de objeto O_ID, Id. de índice I_ID, Id. de partición PN_ID, Id. de unidad de asignación A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="4d2af-115">Chain sequence numbers out of order in the Index Allocation Map (IAM) chain for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="4d2af-116">La página P_ID1 con el número de secuencia SEQUENCE1 apunta a la página P_ID2 con el número de secuencia SEQUENCE2.</span><span class="sxs-lookup"><span data-stu-id="4d2af-116">Page P_ID1 with sequence number SEQUENCE1 points to page P_ID2 with sequence number SEQUENCE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4d2af-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="4d2af-117">Explanation</span></span>  
 <span data-ttu-id="4d2af-118">Cada página IAM (Mapa de asignación de índices) tiene un número de secuencia.</span><span class="sxs-lookup"><span data-stu-id="4d2af-118">Every Index Allocation Map (IAM) page has a sequence number.</span></span> <span data-ttu-id="4d2af-119">Este número es la posición de la página IAM en la cadena IAM.</span><span class="sxs-lookup"><span data-stu-id="4d2af-119">The sequence number is the position of the IAM page within the IAM chain.</span></span> <span data-ttu-id="4d2af-120">La regla es que los números de secuencia aumenten de uno en uno para cada página IAM.</span><span class="sxs-lookup"><span data-stu-id="4d2af-120">The rule is that sequence numbers increase by one for each IAM page.</span></span> <span data-ttu-id="4d2af-121">La página IAM, *P_ID2*, tiene un número de secuencia que no sigue esta regla.</span><span class="sxs-lookup"><span data-stu-id="4d2af-121">IAM page, *P_ID2*, has a sequence number that does not follow this rule.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4d2af-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4d2af-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4d2af-123">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="4d2af-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4d2af-124">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="4d2af-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4d2af-125">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="4d2af-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4d2af-126">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="4d2af-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4d2af-127">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="4d2af-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4d2af-128">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="4d2af-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4d2af-129">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="4d2af-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4d2af-130">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="4d2af-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4d2af-131">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4d2af-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4d2af-132">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="4d2af-132">Restore from Backup</span></span>  
 <span data-ttu-id="4d2af-133">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4d2af-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4d2af-134">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4d2af-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4d2af-135">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="4d2af-135">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="4d2af-136">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="4d2af-136">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="4d2af-137">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="4d2af-137">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4d2af-138">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="4d2af-138">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="4d2af-139">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="4d2af-139">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="4d2af-140">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="4d2af-140">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="4d2af-141">Al ejecutar REPAIR se volverá a generar la cadena IAM.</span><span class="sxs-lookup"><span data-stu-id="4d2af-141">Running REPAIR will rebuild the IAM chain.</span></span> <span data-ttu-id="4d2af-142">REPAIR divide primero la cadena IAM existente en dos mitades.</span><span class="sxs-lookup"><span data-stu-id="4d2af-142">REPAIR first splits the existing IAM chain in two halves.</span></span> <span data-ttu-id="4d2af-143">La primera mitad de la cadena finalizará con la página IAM, *P_ID1*.</span><span class="sxs-lookup"><span data-stu-id="4d2af-143">The first half of the chain will end with IAM page, *P_ID1*.</span></span> <span data-ttu-id="4d2af-144">El puntero de página siguiente de la página *P_ID1* se establecerá en (0:0).</span><span class="sxs-lookup"><span data-stu-id="4d2af-144">The next page pointer of the *P_ID1* page will be set to (0:0).</span></span> <span data-ttu-id="4d2af-145">La segunda mitad de la cadena comenzará con la página IAM, *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="4d2af-145">The second half of the chain will start with IAM page, *P_ID2*.</span></span> <span data-ttu-id="4d2af-146">El puntero de página anterior de la página *P_ID2* se establecerá en (0:0).</span><span class="sxs-lookup"><span data-stu-id="4d2af-146">The previous page pointer of the *P_ID2* page will be set to (0:0).</span></span>  
  
 <span data-ttu-id="4d2af-147">Después, REPAIR conectará las dos mitades de la cadena y volverá a generar los números de secuencia de la cadena IAM.</span><span class="sxs-lookup"><span data-stu-id="4d2af-147">REPAIR will then connect the two haves of the chain together and regenerate the sequence numbers for the IAM chain.</span></span> <span data-ttu-id="4d2af-148">Se cancelará la asignación de las páginas IAM que no se puedan reparar.</span><span class="sxs-lookup"><span data-stu-id="4d2af-148">Any IAM pages that cannot be repaired will be deallocated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="4d2af-149">Esta reparación puede causar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="4d2af-149">This repair may cause data loss.</span></span>  
  
  
