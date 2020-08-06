---
title: MSSQLSERVER_2575 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2575 (Database Engine error)
ms.assetid: 92dfe449-a122-4730-942b-e1d319862d20
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 461d2b57b5ace98ca624f8dc3717c98f3e9e4d67
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662990"
---
# <a name="mssqlserver_2575"></a><span data-ttu-id="5b493-102">MSSQLSERVER_2575</span><span class="sxs-lookup"><span data-stu-id="5b493-102">MSSQLSERVER_2575</span></span>
    
## <a name="details"></a><span data-ttu-id="5b493-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="5b493-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b493-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="5b493-104">Product Name</span></span>|<span data-ttu-id="5b493-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b493-105">SQL Server</span></span>|  
|<span data-ttu-id="5b493-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="5b493-106">Event ID</span></span>|<span data-ttu-id="5b493-107">2575</span><span class="sxs-lookup"><span data-stu-id="5b493-107">2575</span></span>|  
|<span data-ttu-id="5b493-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="5b493-108">Event Source</span></span>|<span data-ttu-id="5b493-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5b493-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5b493-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5b493-110">Component</span></span>|<span data-ttu-id="5b493-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5b493-111">SQLEngine</span></span>|  
|<span data-ttu-id="5b493-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="5b493-112">Symbolic Name</span></span>|<span data-ttu-id="5b493-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span><span class="sxs-lookup"><span data-stu-id="5b493-113">DBCC_IAM_PAGE_WAS_NOT_SEEN</span></span>|  
|<span data-ttu-id="5b493-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="5b493-114">Message Text</span></span>|<span data-ttu-id="5b493-115">El siguiente puntero de la página IAM (Mapa de asignación de índices) P_ID2 [Id. de objeto O_ID, Id. de índice I_ID, Id. de partición PN_ID, Id. de unidad de asignación A_ID (tipo TYPE)] apunta a la página IAM P_ID1, pero no se detectó en el recorrido.</span><span class="sxs-lookup"><span data-stu-id="5b493-115">IAM page P_ID1 is pointed to by the next pointer of IAM page P_ID2 in object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) but was not detected in the scan.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b493-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="5b493-116">Explanation</span></span>  
 <span data-ttu-id="5b493-117">Se encontró una página IAM (Mapa de asignación de índices) para el índice especificado; sin embargo, no se encontró la página IAM para el puntero de página siguiente.</span><span class="sxs-lookup"><span data-stu-id="5b493-117">An Index Allocation Map (IAM) page was found for the specified index; however, the IAM page for its next-page pointer was not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b493-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="5b493-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="5b493-119">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="5b493-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="5b493-120">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="5b493-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="5b493-121">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="5b493-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="5b493-122">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="5b493-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="5b493-123">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="5b493-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="5b493-124">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="5b493-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="5b493-125">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="5b493-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="5b493-126">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="5b493-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="5b493-127">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5b493-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="5b493-128">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="5b493-128">Restore from Backup</span></span>  
 <span data-ttu-id="5b493-129">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5b493-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="5b493-130">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="5b493-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="5b493-131">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="5b493-131">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="5b493-132">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="5b493-132">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="5b493-133">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="5b493-133">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="5b493-134">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="5b493-134">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="5b493-135">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="5b493-135">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
#### <a name="results-of-running-repair-options"></a><span data-ttu-id="5b493-136">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="5b493-136">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="5b493-137">DBCC volverá a generar el índice.</span><span class="sxs-lookup"><span data-stu-id="5b493-137">DBCC will rebuild the index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b493-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5b493-138">See Also</span></span>  
 [<span data-ttu-id="5b493-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="5b493-139">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
