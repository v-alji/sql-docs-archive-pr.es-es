---
title: MSSQLSERVER_2576 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2576 (Database Engine error)
ms.assetid: b727cc2f-c76c-46f8-bbbe-5e7a05a6eabf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f378051c7844bf08d617db56666d69b22ecf732
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671078"
---
# <a name="mssqlserver_2576"></a><span data-ttu-id="bbc87-102">MSSQLSERVER_2576</span><span class="sxs-lookup"><span data-stu-id="bbc87-102">MSSQLSERVER_2576</span></span>
    
## <a name="details"></a><span data-ttu-id="bbc87-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bbc87-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbc87-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="bbc87-104">Product Name</span></span>|<span data-ttu-id="bbc87-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bbc87-105">SQL Server</span></span>|  
|<span data-ttu-id="bbc87-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="bbc87-106">Event ID</span></span>|<span data-ttu-id="bbc87-107">2576</span><span class="sxs-lookup"><span data-stu-id="bbc87-107">2576</span></span>|  
|<span data-ttu-id="bbc87-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="bbc87-108">Event Source</span></span>|<span data-ttu-id="bbc87-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bbc87-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bbc87-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bbc87-110">Component</span></span>|<span data-ttu-id="bbc87-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bbc87-111">SQLEngine</span></span>|  
|<span data-ttu-id="bbc87-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bbc87-112">Symbolic Name</span></span>|<span data-ttu-id="bbc87-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="bbc87-113">DBCC_IAM_PARENT_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="bbc87-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bbc87-114">Message Text</span></span>|<span data-ttu-id="bbc87-115">El puntero anterior de la página IAM (Mapa de asignación de índices) P_ID2 [Id. de objeto O_ID, Id. de partición PN_ID, unidad de asignación A_ID (tipo TYPE)] apunta a la página IAM P_ID1, pero no se detectó en el recorrido.</span><span class="sxs-lookup"><span data-stu-id="bbc87-115">The Index Allocation Map (IAM) page P_ID1 is pointed to by the previous pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bbc87-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="bbc87-116">Explanation</span></span>  
 <span data-ttu-id="bbc87-117">No se encontró una página IAM (Mapa de asignación de índices ) o una entrada de metadatos, aunque existe una referencia a la página como el vínculo de página anterior en otra página IAM de una cadena IAM.</span><span class="sxs-lookup"><span data-stu-id="bbc87-117">An Index Allocation Map (IAM) page or metadata entry was not located, even though a reference to the page exists as the previous page link on another IAM page in an IAM chain.</span></span> <span data-ttu-id="bbc87-118">Si la página *P_ID1* es (0:0), la página IAM, *P_ID2*, es el inicio de una cadena IAM y falta la entrada de metadatos de la cadena IAM.</span><span class="sxs-lookup"><span data-stu-id="bbc87-118">If the *P_ID1* page is (0:0), the IAM page, *P_ID2*, is the start of an IAM chain, and the metadata entry for the IAM chain is missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bbc87-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bbc87-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="bbc87-120">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="bbc87-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="bbc87-121">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="bbc87-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="bbc87-122">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="bbc87-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="bbc87-123">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="bbc87-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="bbc87-124">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="bbc87-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="bbc87-125">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="bbc87-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="bbc87-126">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="bbc87-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="bbc87-127">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="bbc87-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="bbc87-128">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bbc87-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="bbc87-129">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="bbc87-129">Restore from Backup</span></span>  
 <span data-ttu-id="bbc87-130">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bbc87-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="bbc87-131">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="bbc87-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="bbc87-132">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="bbc87-132">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="bbc87-133">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="bbc87-133">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="bbc87-134">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="bbc87-134">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="bbc87-135">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="bbc87-135">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="bbc87-136">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="bbc87-136">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="bbc87-137">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="bbc87-137">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="bbc87-138">REPAIR intentará volver a generar la cadena IAM que incluye la página *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="bbc87-138">REPAIR will try to rebuild the IAM chain involving the *P_ID2* page.</span></span> <span data-ttu-id="bbc87-139">La regeneración de la cadena puede incluir la eliminación de páginas de la cadena o la eliminación de la cadena completa si los metadatos están dañados.</span><span class="sxs-lookup"><span data-stu-id="bbc87-139">Rebuilding the chain may involve removing pages from the chain, or removing the whole chain if the metadata is corrupted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="bbc87-140">Esta reparación puede causar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="bbc87-140">This repair may cause data loss.</span></span>  
  
  
