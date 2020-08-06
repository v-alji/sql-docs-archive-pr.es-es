---
title: MSSQLSERVER_7995 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7995 (Database Engine error)
ms.assetid: af6d6322-3cba-43d8-be97-e6ef15f8c933
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8c65cf2b16c4d7a0dcf40272f8280205a111d08e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673687"
---
# <a name="mssqlserver_7995"></a><span data-ttu-id="29b6b-102">MSSQLSERVER_7995</span><span class="sxs-lookup"><span data-stu-id="29b6b-102">MSSQLSERVER_7995</span></span>
    
## <a name="details"></a><span data-ttu-id="29b6b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="29b6b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29b6b-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="29b6b-104">Product Name</span></span>|<span data-ttu-id="29b6b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="29b6b-105">SQL Server</span></span>|  
|<span data-ttu-id="29b6b-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="29b6b-106">Event ID</span></span>|<span data-ttu-id="29b6b-107">7995</span><span class="sxs-lookup"><span data-stu-id="29b6b-107">7995</span></span>|  
|<span data-ttu-id="29b6b-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="29b6b-108">Event Source</span></span>|<span data-ttu-id="29b6b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="29b6b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="29b6b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="29b6b-110">Component</span></span>|<span data-ttu-id="29b6b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="29b6b-111">SQLEngine</span></span>|  
|<span data-ttu-id="29b6b-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="29b6b-112">Symbolic Name</span></span>|<span data-ttu-id="29b6b-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="29b6b-113">DBCC2_SYSTEM_CATALOGS_CORRUPT</span></span>|  
|<span data-ttu-id="29b6b-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="29b6b-114">Message Text</span></span>|<span data-ttu-id="29b6b-115">Base de datos 'DBNAME': errores de incoherencia en catálogos del sistema impiden el procesamiento de DBCC CHECKNAME.</span><span class="sxs-lookup"><span data-stu-id="29b6b-115">Database 'DBNAME': consistency errors in system catalogs prevent further DBCC CHECKNAME processing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="29b6b-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="29b6b-116">Explanation</span></span>  
 <span data-ttu-id="29b6b-117">El proceso de DBCC CHECKDB consta de las tres fases siguientes:</span><span class="sxs-lookup"><span data-stu-id="29b6b-117">The DBCC CHECKDB process consists of the following three stages:</span></span>  
  
1.  <span data-ttu-id="29b6b-118">Comprobaciones de asignación.</span><span class="sxs-lookup"><span data-stu-id="29b6b-118">Allocation checks.</span></span> <span data-ttu-id="29b6b-119">Esto equivale a ejecutar DBCC CHECKALLOC.</span><span class="sxs-lookup"><span data-stu-id="29b6b-119">This is equivalent to running DBCC CHECKALLOC.</span></span>  
  
2.  <span data-ttu-id="29b6b-120">Comprobaciones de coherencia de las tablas del sistema.</span><span class="sxs-lookup"><span data-stu-id="29b6b-120">System tables consistency checks.</span></span> <span data-ttu-id="29b6b-121">Esto equivale a ejecutar DBCC CHECKTABLE en una pequeña lista de tablas base necesarias del sistema.</span><span class="sxs-lookup"><span data-stu-id="29b6b-121">This is equivalent to running DBCC CHECKTABLE on a small list of necessary system base tables.</span></span>  
  
3.  <span data-ttu-id="29b6b-122">Comprobaciones completas de coherencia de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="29b6b-122">Complete database consistency checks.</span></span>  
  
 <span data-ttu-id="29b6b-123">MSSQLEngine_7995 se produce en la fase 2 para indicar que DBCC CHECKDB ha encontrado errores que el comando no puede reparar o que no se ha especificado REPAIR.</span><span class="sxs-lookup"><span data-stu-id="29b6b-123">MSSQLEngine_7995 is raised in stage 2 to indicate that DBCC CHECKDB has found errors that the command cannot repair or that REPAIR has not been specified.</span></span> <span data-ttu-id="29b6b-124">DBCC CHECKDB no puede continuar con la fase 3 porque las tablas base del sistema en cuestión almacenan los metadatos de todos los objetos de la base de datos o las tablas base del sistema están dañadas.</span><span class="sxs-lookup"><span data-stu-id="29b6b-124">DBCC CHECKDB cannot continue with stage 3 because either the system base tables in question store the metadata for all objects in the database or the system base tables are corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="29b6b-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="29b6b-125">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="29b6b-126">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="29b6b-126">Look for Hardware Failure</span></span>  
 <span data-ttu-id="29b6b-127">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="29b6b-127">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="29b6b-128">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="29b6b-128">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="29b6b-129">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="29b6b-129">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="29b6b-130">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="29b6b-130">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="29b6b-131">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="29b6b-131">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="29b6b-132">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="29b6b-132">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="29b6b-133">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="29b6b-133">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="29b6b-134">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="29b6b-134">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="29b6b-135">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="29b6b-135">Restore from Backup</span></span>  
 <span data-ttu-id="29b6b-136">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="29b6b-136">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="29b6b-137">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="29b6b-137">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="29b6b-138">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="29b6b-138">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="29b6b-139">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="29b6b-139">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="29b6b-140">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="29b6b-140">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="29b6b-141">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="29b6b-141">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="29b6b-142">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="29b6b-142">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="29b6b-143">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="29b6b-143">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="29b6b-144">Examine la lista de errores para ver qué hará REPAIR para cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="29b6b-144">Examine the list of errors to see what REPAIR will do for each.</span></span>  
  
  
