---
title: MSSQLSERVER_8974 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8974 (Database Engine error)
ms.assetid: 52098678-0858-4a14-ad07-37ebbafca5fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3107f5b62caf04e232532c2d2b93d5da19fb53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678193"
---
# <a name="mssqlserver_8974"></a><span data-ttu-id="57a91-102">MSSQLSERVER_8974</span><span class="sxs-lookup"><span data-stu-id="57a91-102">MSSQLSERVER_8974</span></span>
    
## <a name="details"></a><span data-ttu-id="57a91-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="57a91-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="57a91-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="57a91-104">Product Name</span></span>|<span data-ttu-id="57a91-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="57a91-105">SQL Server</span></span>|  
|<span data-ttu-id="57a91-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="57a91-106">Event ID</span></span>|<span data-ttu-id="57a91-107">8974</span><span class="sxs-lookup"><span data-stu-id="57a91-107">8974</span></span>|  
|<span data-ttu-id="57a91-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="57a91-108">Event Source</span></span>|<span data-ttu-id="57a91-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="57a91-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="57a91-110">Componente</span><span class="sxs-lookup"><span data-stu-id="57a91-110">Component</span></span>|<span data-ttu-id="57a91-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="57a91-111">SQLEngine</span></span>|  
|<span data-ttu-id="57a91-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="57a91-112">Symbolic Name</span></span>|<span data-ttu-id="57a91-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span><span class="sxs-lookup"><span data-stu-id="57a91-113">DBCC3_OFF_ROW_DATA_NODE_HAS_TWO_PARENTS</span></span>|  
|<span data-ttu-id="57a91-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="57a91-114">Message Text</span></span>|<span data-ttu-id="57a91-115">Error de tabla: id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE).</span><span class="sxs-lookup"><span data-stu-id="57a91-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE).</span></span> <span data-ttu-id="57a91-116">Las páginas P_ID2, zona S_ID2 y P_ID3, zona P_ID3 apuntan al nodo de datos no consecutivos de la página P_ID1, zona S_ID1, Id. de texto TEXT_ID.</span><span class="sxs-lookup"><span data-stu-id="57a91-116">The off-row data node at page P_ID1, slot S_ID1, text ID TEXT_ID is pointed to by page P_ID2, slot S_ID2 and by page P_ID3, slot P_ID3.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="57a91-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="57a91-117">Explanation</span></span>  
 <span data-ttu-id="57a91-118">Un nodo de datos no consecutivos tiene dos registros de datos o índices que lo enumeran como un nodo secundario.</span><span class="sxs-lookup"><span data-stu-id="57a91-118">An off-row data node has two data or index records that list it as a child node.</span></span> <span data-ttu-id="57a91-119">Un nodo solo puede tener un nodo primario.</span><span class="sxs-lookup"><span data-stu-id="57a91-119">A node can have only one parent node.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57a91-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="57a91-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="57a91-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="57a91-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="57a91-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="57a91-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="57a91-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="57a91-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="57a91-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="57a91-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="57a91-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="57a91-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="57a91-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="57a91-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="57a91-127">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="57a91-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="57a91-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="57a91-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="57a91-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="57a91-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="57a91-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="57a91-130">Restore from Backup</span></span>  
 <span data-ttu-id="57a91-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="57a91-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="57a91-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="57a91-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="57a91-133">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="57a91-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="57a91-134">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="57a91-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="57a91-135">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="57a91-135">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="57a91-136">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="57a91-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="57a91-137">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="57a91-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="57a91-138">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="57a91-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="57a91-139">El nodo de datos no consecutivos de la página *P_ID1* se eliminará, así como las dos referencias de las páginas *P_ID2* y *P_ID3*.</span><span class="sxs-lookup"><span data-stu-id="57a91-139">The off-row data node on page *P_ID1* will be deleted and both references on pages *P_ID2* and *P_ID3* will be deleted.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="57a91-140">Esta reparación puede causar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="57a91-140">This repair might cause data loss.</span></span>  
  
  
