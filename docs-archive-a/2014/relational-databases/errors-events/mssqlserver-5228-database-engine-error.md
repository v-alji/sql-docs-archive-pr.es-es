---
title: MSSQLSERVER_5228 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5228 (Database Engine error)
ms.assetid: 5e83c617-4aa2-4755-bcc5-a798c46b97e4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: eef59e62f00a44aad7bfefb1719a6d8d2b3d0290
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662986"
---
# <a name="mssqlserver_5228"></a><span data-ttu-id="bd558-102">MSSQLSERVER_5228</span><span class="sxs-lookup"><span data-stu-id="bd558-102">MSSQLSERVER_5228</span></span>
    
## <a name="details"></a><span data-ttu-id="bd558-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="bd558-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bd558-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="bd558-104">Product Name</span></span>|<span data-ttu-id="bd558-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd558-105">SQL Server</span></span>|  
|<span data-ttu-id="bd558-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="bd558-106">Event ID</span></span>|<span data-ttu-id="bd558-107">5228</span><span class="sxs-lookup"><span data-stu-id="bd558-107">5228</span></span>|  
|<span data-ttu-id="bd558-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="bd558-108">Event Source</span></span>|<span data-ttu-id="bd558-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bd558-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bd558-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bd558-110">Component</span></span>|<span data-ttu-id="bd558-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bd558-111">SQLEngine</span></span>|  
|<span data-ttu-id="bd558-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="bd558-112">Symbolic Name</span></span>|<span data-ttu-id="bd558-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span><span class="sxs-lookup"><span data-stu-id="bd558-113">DBCC4_ANTIMATTER_COLUMN_DETECTED</span></span>|  
|<span data-ttu-id="bd558-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="bd558-114">Message Text</span></span>|<span data-ttu-id="bd558-115">Error de tabla: id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE), página PG_ID, fila R_ID.</span><span class="sxs-lookup"><span data-stu-id="bd558-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page PG_ID, row R_ID.</span></span> <span data-ttu-id="bd558-116">DBCC detectó una limpieza incompleta en una operación de generación de índice en línea.</span><span class="sxs-lookup"><span data-stu-id="bd558-116">DBCC detected incomplete cleanup from an online index build operation.</span></span> <span data-ttu-id="bd558-117">(El valor de la columna antimateria es VALUE.)</span><span class="sxs-lookup"><span data-stu-id="bd558-117">(Antimatter column value is VALUE.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bd558-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="bd558-118">Explanation</span></span>  
 <span data-ttu-id="bd558-119">Se detectó una generación de índice en línea incompleta para el objeto *O_ID*, índice *I_ID* y partición *PN_ID*.</span><span class="sxs-lookup"><span data-stu-id="bd558-119">An unfinished online index build was detected for object *O_ID*, index *I_ID*, and partition *PN_ID*.</span></span> <span data-ttu-id="bd558-120">Esto queda de manifiesto por la presencia de una columna antimateria en la fila *R_ID*.</span><span class="sxs-lookup"><span data-stu-id="bd558-120">This is manifested by the presence of an antimatter column on the row *R_ID*.</span></span> <span data-ttu-id="bd558-121">Se utiliza una columna antimateria al reconciliar los registros de varios orígenes durante una generación de índice en línea.</span><span class="sxs-lookup"><span data-stu-id="bd558-121">An antimatter column is used when reconciling records from multiple sources during an online index build.</span></span> <span data-ttu-id="bd558-122">El mensaje de error también indica el valor de la columna antimateria.</span><span class="sxs-lookup"><span data-stu-id="bd558-122">The error message also indicates the value of the antimatter column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bd558-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="bd558-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="bd558-124">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="bd558-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="bd558-125">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="bd558-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="bd558-126">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="bd558-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="bd558-127">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="bd558-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="bd558-128">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="bd558-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="bd558-129">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="bd558-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="bd558-130">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="bd558-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="bd558-131">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="bd558-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="bd558-132">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bd558-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="bd558-133">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="bd558-133">Restore from Backup</span></span>  
 <span data-ttu-id="bd558-134">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="bd558-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="bd558-135">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="bd558-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="bd558-136">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="bd558-136">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="bd558-137">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="bd558-137">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="bd558-138">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR apropiada para reparar el problema.</span><span class="sxs-lookup"><span data-stu-id="bd558-138">Then, run DBCC CHECKDB with the appropriate REPAIR clause to repair the corruption.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="bd558-139">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="bd558-139">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="bd558-140">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="bd558-140">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="bd558-141">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="bd558-141">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="bd558-142">Al ejecutar REPAIR, volverá generarse el índice especificado y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="bd558-142">Running REPAIR will cause the specified index and all its dependent indexes to be rebuilt.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd558-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bd558-143">See Also</span></span>  
 [<span data-ttu-id="bd558-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bd558-144">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
