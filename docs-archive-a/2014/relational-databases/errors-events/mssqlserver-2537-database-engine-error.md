---
title: MSSQLSERVER_2537 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2537 (Database Engine error)
ms.assetid: 0af6ff69-d75a-4c39-8da2-9bd0695277c6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c227867bac5a0ea5789ba653414444d011e5910d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675911"
---
# <a name="mssqlserver_2537"></a><span data-ttu-id="8162b-102">MSSQLSERVER_2537</span><span class="sxs-lookup"><span data-stu-id="8162b-102">MSSQLSERVER_2537</span></span>
    
## <a name="details"></a><span data-ttu-id="8162b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="8162b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8162b-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="8162b-104">Product Name</span></span>|<span data-ttu-id="8162b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8162b-105">SQL Server</span></span>|  
|<span data-ttu-id="8162b-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="8162b-106">Event ID</span></span>|<span data-ttu-id="8162b-107">2537</span><span class="sxs-lookup"><span data-stu-id="8162b-107">2537</span></span>|  
|<span data-ttu-id="8162b-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="8162b-108">Event Source</span></span>|<span data-ttu-id="8162b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8162b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8162b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8162b-110">Component</span></span>|<span data-ttu-id="8162b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8162b-111">SQLEngine</span></span>|  
|<span data-ttu-id="8162b-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="8162b-112">Symbolic Name</span></span>|<span data-ttu-id="8162b-113">DBCC_RECORD_CHECK_FAILED</span><span class="sxs-lookup"><span data-stu-id="8162b-113">DBCC_RECORD_CHECK_FAILED</span></span>|  
|<span data-ttu-id="8162b-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="8162b-114">Message Text</span></span>|<span data-ttu-id="8162b-115">Error de tabla: id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE), página P_ID, fila ROW_ID.</span><span class="sxs-lookup"><span data-stu-id="8162b-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), page P_ID, row ROW_ID.</span></span> <span data-ttu-id="8162b-116">Error en la comprobación de registro (CHECK_TEXT).</span><span class="sxs-lookup"><span data-stu-id="8162b-116">Record check (CHECK_TEXT) failed.</span></span> <span data-ttu-id="8162b-117">Los valores son VALUE1 y VALUE2.</span><span class="sxs-lookup"><span data-stu-id="8162b-117">Values are VALUE1 and VALUE2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8162b-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="8162b-118">Explanation</span></span>  
 <span data-ttu-id="8162b-119">El ROW_ID de fila (o una columna de la fila) produjo un error en la prueba o condición que se describe en CHECK_TEXT.</span><span class="sxs-lookup"><span data-stu-id="8162b-119">The row ROW_ID (or a column in the row) failed the test or condition described by CHECK_TEXT.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8162b-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="8162b-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="8162b-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="8162b-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="8162b-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="8162b-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="8162b-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="8162b-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="8162b-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="8162b-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="8162b-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="8162b-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="8162b-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="8162b-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="8162b-127">Si cree que el problema se debe a la memoria caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="8162b-127">If you suspect that write-caching is the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="8162b-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="8162b-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="8162b-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="8162b-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="8162b-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="8162b-130">Restore from Backup</span></span>  
 <span data-ttu-id="8162b-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="8162b-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="8162b-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="8162b-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="8162b-133">Si no tiene disponible una copia de seguridad limpia, ejecute DBCC CHECKDB sin una cláusula REPAIR para determinar el alcance de los daños.</span><span class="sxs-lookup"><span data-stu-id="8162b-133">If no clean backup is available, run DBCC CHECKDB without a REPAIR clause to determine the extent of the corruption.</span></span> <span data-ttu-id="8162b-134">DBCC CHECKDB recomendará el uso de una cláusula REPAIR.</span><span class="sxs-lookup"><span data-stu-id="8162b-134">DBCC CHECKDB will recommend a REPAIR clause to use.</span></span> <span data-ttu-id="8162b-135">A continuación, ejecute DBCC CHECKDB con la cláusula REPAIR recomendada.</span><span class="sxs-lookup"><span data-stu-id="8162b-135">Then, run DBCC CHECKDB with the recommended REPAIR clause.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="8162b-136">Si no está seguro del efecto que tendrá DBCC CHECKDB con una cláusula REPAIR en los datos, póngase en contacto con su proveedor principal de soporte antes de ejecutar esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="8162b-136">If you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider before running this statement.</span></span>  
  
 <span data-ttu-id="8162b-137">Si ejecuta DBCC CHECKDB con una de las cláusulas REPAIR y no se soluciona el problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="8162b-137">If running DBCC CHECKDB with one of the REPAIR clauses does not correct the problem, contact your primary support provider.</span></span>  
  
### <a name="results-of-running-repair-options"></a><span data-ttu-id="8162b-138">Resultados de ejecutar opciones REPAIR</span><span class="sxs-lookup"><span data-stu-id="8162b-138">Results of Running REPAIR Options</span></span>  
 <span data-ttu-id="8162b-139">REPAIR vuelve a generar el índice (si existe).</span><span class="sxs-lookup"><span data-stu-id="8162b-139">REPAIR will rebuild the index if an index exists.</span></span>  
  
 <span data-ttu-id="8162b-140">**PRECAUCIÓN:** Esta reparación puede causar la pérdida de datos.</span><span class="sxs-lookup"><span data-stu-id="8162b-140">**Caution** This repair may cause data loss.</span></span>  
  
  
