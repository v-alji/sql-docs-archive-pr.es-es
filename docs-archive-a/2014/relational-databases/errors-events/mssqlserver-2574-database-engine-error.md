---
title: MSSQLSERVER_2574 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2574 (Database Engine error)
ms.assetid: efba507a-b5ad-4f1d-b0c8-f73b663a0562
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44fd103f8c651ca968ae997ae9c3d544b41cbf3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744713"
---
# <a name="mssqlserver_2574"></a><span data-ttu-id="8d49e-102">MSSQLSERVER_2574</span><span class="sxs-lookup"><span data-stu-id="8d49e-102">MSSQLSERVER_2574</span></span>
    
## <a name="details"></a><span data-ttu-id="8d49e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d49e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d49e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="8d49e-104">Product Name</span></span>|<span data-ttu-id="8d49e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d49e-105">SQL Server</span></span>|  
|<span data-ttu-id="8d49e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8d49e-106">Event ID</span></span>|<span data-ttu-id="8d49e-107">2574</span><span class="sxs-lookup"><span data-stu-id="8d49e-107">2574</span></span>|  
|<span data-ttu-id="8d49e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="8d49e-108">Event Source</span></span>|<span data-ttu-id="8d49e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8d49e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8d49e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8d49e-110">Component</span></span>|<span data-ttu-id="8d49e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8d49e-111">SQLEngine</span></span>|  
|<span data-ttu-id="8d49e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8d49e-112">Symbolic Name</span></span>|<span data-ttu-id="8d49e-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span><span class="sxs-lookup"><span data-stu-id="8d49e-113">DBCC_EMPTY_INDEX_TREE_LEVEL_PAGE</span></span>|  
|<span data-ttu-id="8d49e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8d49e-114">Message Text</span></span>|<span data-ttu-id="8d49e-115">Error de tabla: la página P_ID está vacía en el id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="8d49e-115">Table error: Page P_ID is empty in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="8d49e-116">Esto no se permite en el nivel LEVEL del árbol b.</span><span class="sxs-lookup"><span data-stu-id="8d49e-116">This is not permitted at level LEVEL of the B-tree.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8d49e-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="8d49e-117">Explanation</span></span>  
 <span data-ttu-id="8d49e-118">Una página de árbol B por encima del nivel hoja del índice especificado está vacía, es decir, no tiene ninguna fila.</span><span class="sxs-lookup"><span data-stu-id="8d49e-118">A B-tree page above the leaf level of the specified index is empty, that is it has no rows.</span></span> <span data-ttu-id="8d49e-119">Este comportamiento es posible para las páginas de nivel de hoja de [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], pero nunca ha sido posible en los niveles de árbol.</span><span class="sxs-lookup"><span data-stu-id="8d49e-119">This behavior is possible for leaf-level pages in [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], but has never been possible in tree levels.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d49e-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8d49e-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="8d49e-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="8d49e-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="8d49e-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="8d49e-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="8d49e-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="8d49e-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="8d49e-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="8d49e-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="8d49e-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="8d49e-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="8d49e-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="8d49e-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="8d49e-127">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="8d49e-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="8d49e-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="8d49e-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="8d49e-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8d49e-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="8d49e-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="8d49e-130">Restore from Backup</span></span>  
 <span data-ttu-id="8d49e-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8d49e-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="8d49e-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="8d49e-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="8d49e-133">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="8d49e-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="8d49e-134">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="8d49e-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="8d49e-135">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="8d49e-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="8d49e-136">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="8d49e-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="8d49e-137">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="8d49e-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="8d49e-138">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="8d49e-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="8d49e-139">DBCC volverá a generar el índice.</span><span class="sxs-lookup"><span data-stu-id="8d49e-139">DBCC will rebuild the index.</span></span>  
  
  
