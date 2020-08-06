---
title: MSSQLSERVER_7984 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7984 (Database Engine error)
ms.assetid: e3192f56-e4e2-41da-b132-65f1e7540b1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7f92fe4f3751621e0cc636ffcd2d4de73b348d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675419"
---
# <a name="mssqlserver_7984"></a><span data-ttu-id="fb18f-102">MSSQLSERVER_7984</span><span class="sxs-lookup"><span data-stu-id="fb18f-102">MSSQLSERVER_7984</span></span>
    
## <a name="details"></a><span data-ttu-id="fb18f-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fb18f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb18f-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="fb18f-104">Product Name</span></span>|<span data-ttu-id="fb18f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fb18f-105">SQL Server</span></span>|  
|<span data-ttu-id="fb18f-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fb18f-106">Event ID</span></span>|<span data-ttu-id="fb18f-107">7984</span><span class="sxs-lookup"><span data-stu-id="fb18f-107">7984</span></span>|  
|<span data-ttu-id="fb18f-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="fb18f-108">Event Source</span></span>|<span data-ttu-id="fb18f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fb18f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fb18f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fb18f-110">Component</span></span>|<span data-ttu-id="fb18f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fb18f-111">SQLEngine</span></span>|  
|<span data-ttu-id="fb18f-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fb18f-112">Symbolic Name</span></span>|<span data-ttu-id="fb18f-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span><span class="sxs-lookup"><span data-stu-id="fb18f-113">DBCC2_PRE_CHECKS_BAD_PAGE_TYPE</span></span>|  
|<span data-ttu-id="fb18f-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fb18f-114">Message Text</span></span>|<span data-ttu-id="fb18f-115">Comprobaciones previas de tabla del sistema: id. de objeto O_ID.</span><span class="sxs-lookup"><span data-stu-id="fb18f-115">System table pre-checks: Object ID O_ID.</span></span> <span data-ttu-id="fb18f-116">La página P_ID tiene un tipo de página inesperado PAGETYPE.</span><span class="sxs-lookup"><span data-stu-id="fb18f-116">Page P_ID has unexpected page type PAGETYPE.</span></span> <span data-ttu-id="fb18f-117">Instrucción de comprobación terminada debido a un error irreparable.</span><span class="sxs-lookup"><span data-stu-id="fb18f-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fb18f-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="fb18f-118">Explanation</span></span>  
 <span data-ttu-id="fb18f-119">Se encontró una página con un tipo distinto de DATA_PAGE en el nivel de datos del objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="fb18f-119">A page with a type other than DATA_PAGE was found in the data level of the specified object.</span></span> <span data-ttu-id="fb18f-120">Este error se produce durante la primera fase de las comprobaciones del comando DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="fb18f-120">This error is raised during the first phase of the DBCC CHECKDB command checks.</span></span> <span data-ttu-id="fb18f-121">Durante esa fase, DBCC CHECKDB realiza comprobaciones básicas en las páginas de datos de las tablas base críticas del sistema.</span><span class="sxs-lookup"><span data-stu-id="fb18f-121">During this phase, DBCC CHECKDB performs primitive checks on the data pages of critical system base tables.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb18f-122">Si se encuentran errores en las tablas del sistema, los errores no se pueden reparar; por lo tanto, el comando DBCC CHECKDB finaliza inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="fb18f-122">If any errors are found in the system tables, the errors cannot be repaired; therefore, the DBCC CHECKDB command ends immediately.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fb18f-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fb18f-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="fb18f-124">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="fb18f-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="fb18f-125">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="fb18f-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="fb18f-126">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="fb18f-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="fb18f-127">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="fb18f-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="fb18f-128">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="fb18f-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="fb18f-129">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="fb18f-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="fb18f-130">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="fb18f-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="fb18f-131">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="fb18f-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="fb18f-132">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fb18f-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="fb18f-133">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="fb18f-133">Restore from Backup</span></span>  
 <span data-ttu-id="fb18f-134">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fb18f-134">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="fb18f-135">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="fb18f-135">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="fb18f-136">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="fb18f-136">Not applicable.</span></span> <span data-ttu-id="fb18f-137">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fb18f-137">This error cannot be repaired automatically.</span></span> <span data-ttu-id="fb18f-138">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el Servicio de atención al cliente y soporte técnico (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb18f-138">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
