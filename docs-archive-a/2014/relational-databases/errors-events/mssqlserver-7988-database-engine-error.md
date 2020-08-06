---
title: MSSQLSERVER_7988 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7988 (Database Engine error)
ms.assetid: 29b967b8-de30-4618-99a8-8b1155e69026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 984cb03aeb5feaa230762e200304f16cd8c5df08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745767"
---
# <a name="mssqlserver_7988"></a><span data-ttu-id="9ba31-102">MSSQLSERVER_7988</span><span class="sxs-lookup"><span data-stu-id="9ba31-102">MSSQLSERVER_7988</span></span>
    
## <a name="details"></a><span data-ttu-id="9ba31-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9ba31-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ba31-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="9ba31-104">Product Name</span></span>|<span data-ttu-id="9ba31-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9ba31-105">SQL Server</span></span>|  
|<span data-ttu-id="9ba31-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="9ba31-106">Event ID</span></span>|<span data-ttu-id="9ba31-107">7988</span><span class="sxs-lookup"><span data-stu-id="9ba31-107">7988</span></span>|  
|<span data-ttu-id="9ba31-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="9ba31-108">Event Source</span></span>|<span data-ttu-id="9ba31-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9ba31-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9ba31-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9ba31-110">Component</span></span>|<span data-ttu-id="9ba31-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9ba31-111">SQLEngine</span></span>|  
|<span data-ttu-id="9ba31-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9ba31-112">Symbolic Name</span></span>|<span data-ttu-id="9ba31-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span><span class="sxs-lookup"><span data-stu-id="9ba31-113">DBCC2_PRE_CHECKS_CHAIN_LOOP_DETECTED</span></span>|  
|<span data-ttu-id="9ba31-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9ba31-114">Message Text</span></span>|<span data-ttu-id="9ba31-115">Comprobaciones previas de tabla del sistema: id. de objeto O_ID.</span><span class="sxs-lookup"><span data-stu-id="9ba31-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="9ba31-116">Se detectó un bucle en una cadena de datos en P_ID.</span><span class="sxs-lookup"><span data-stu-id="9ba31-116">Loop in data chain detected at P_ID.</span></span> <span data-ttu-id="9ba31-117">Instrucción de comprobación terminada debido a un error irreparable.</span><span class="sxs-lookup"><span data-stu-id="9ba31-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9ba31-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="9ba31-118">Explanation</span></span>  
 <span data-ttu-id="9ba31-119">La primera fase de DBCC CHECKDB es hacer comprobaciones básicas en las páginas de datos de las tablas críticas del sistema.</span><span class="sxs-lookup"><span data-stu-id="9ba31-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="9ba31-120">Si se encuentra algún error, no puede repararse; por tanto, DBCC CHECKDB termina inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9ba31-120">If any errors are found, they cannot be repaired; therefore, DBCC CHECKDB terminates immediately.</span></span> <span data-ttu-id="9ba31-121">Se ha detectado un bucle de vinculación de páginas en la página *P_ID*.</span><span class="sxs-lookup"><span data-stu-id="9ba31-121">A page linkage loop has been detected on page *P_ID*.</span></span> <span data-ttu-id="9ba31-122">Un bucle de vinculación de páginas se produce cuando los punteros de página siguiente de una página vuelven finalmente a la página.</span><span class="sxs-lookup"><span data-stu-id="9ba31-122">A page linkage loop occurs when the next page pointers from a page eventually return to the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9ba31-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9ba31-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="9ba31-124">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="9ba31-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="9ba31-125">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="9ba31-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="9ba31-126">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="9ba31-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="9ba31-127">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="9ba31-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="9ba31-128">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="9ba31-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="9ba31-129">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="9ba31-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="9ba31-130">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="9ba31-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="9ba31-131">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="9ba31-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="9ba31-132">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9ba31-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="9ba31-133">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="9ba31-133">Restore from Backup</span></span>  
 <span data-ttu-id="9ba31-134">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9ba31-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="9ba31-135">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="9ba31-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="9ba31-136">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="9ba31-136">Not applicable.</span></span> <span data-ttu-id="9ba31-137">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="9ba31-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="9ba31-138">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el Servicio de atención al cliente y soporte técnico (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ba31-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
