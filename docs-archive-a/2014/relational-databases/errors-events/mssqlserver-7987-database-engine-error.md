---
title: MSSQLSERVER_7987 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7987 (Database Engine error)
ms.assetid: 314aebf1-6cdf-488d-a274-ce967fadb57b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2fec3cf707e2e9923084f48096a88c60655513e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746301"
---
# <a name="mssqlserver_7987"></a><span data-ttu-id="98e07-102">MSSQLSERVER_7987</span><span class="sxs-lookup"><span data-stu-id="98e07-102">MSSQLSERVER_7987</span></span>
    
## <a name="details"></a><span data-ttu-id="98e07-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="98e07-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98e07-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="98e07-104">Product Name</span></span>|<span data-ttu-id="98e07-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="98e07-105">SQL Server</span></span>|  
|<span data-ttu-id="98e07-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="98e07-106">Event ID</span></span>|<span data-ttu-id="98e07-107">7987</span><span class="sxs-lookup"><span data-stu-id="98e07-107">7987</span></span>|  
|<span data-ttu-id="98e07-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="98e07-108">Event Source</span></span>|<span data-ttu-id="98e07-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="98e07-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="98e07-110">Componente</span><span class="sxs-lookup"><span data-stu-id="98e07-110">Component</span></span>|<span data-ttu-id="98e07-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="98e07-111">SQLEngine</span></span>|  
|<span data-ttu-id="98e07-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="98e07-112">Symbolic Name</span></span>|<span data-ttu-id="98e07-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="98e07-113">DBCC2_PRE_CHECKS_CHAIN_LINKAGE_MISMATCH</span></span>|  
|<span data-ttu-id="98e07-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="98e07-114">Message Text</span></span>|<span data-ttu-id="98e07-115">Comprobaciones previas de tabla del sistema: el id. de objeto O_ID tiene un encadenamiento que no corresponde.</span><span class="sxs-lookup"><span data-stu-id="98e07-115">System table pre-checks: Object ID O_ID has chain linkage mismatch.</span></span> <span data-ttu-id="98e07-116">P_ID1->next = P_ID2, pero P_ID2->prev = P_ID3.</span><span class="sxs-lookup"><span data-stu-id="98e07-116">P_ID1->next = P_ID2, but P_ID2->prev = P_ID3.</span></span> <span data-ttu-id="98e07-117">Instrucción de comprobación terminada debido a un error irreparable.</span><span class="sxs-lookup"><span data-stu-id="98e07-117">Check statement terminated because of an irreparable error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="98e07-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="98e07-118">Explanation</span></span>  
 <span data-ttu-id="98e07-119">La primera fase de DBCC CHECKDB es hacer comprobaciones básicas en las páginas de datos de las tablas críticas del sistema.</span><span class="sxs-lookup"><span data-stu-id="98e07-119">The first phase of a DBCC CHECKDB is to do primitive checks on the data pages of critical system tables.</span></span> <span data-ttu-id="98e07-120">Si se encuentra algún error, no puede repararse; por tanto, DBCC CHECKDB termina inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="98e07-120">If any errors are found, they cannot be repaired; therefore, the DBCC CHECKDB terminates immediately.</span></span>  
  
 <span data-ttu-id="98e07-121">El puntero de página siguiente de la página *P_ID1* apunta a la página *P_ID2*; sin embargo, el puntero de página anterior de la página *P_ID2* apunta a la página *P_ID3*, no hacia atrás a la página *P_ID1*, como debería.</span><span class="sxs-lookup"><span data-stu-id="98e07-121">The next page pointer of page *P_ID1* points to page *P_ID2*; however, the previous page pointer of page *P_ID2* points to page *P_ID3* but not back to page *P_ID1*, as it should.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="98e07-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="98e07-122">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="98e07-123">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="98e07-123">Look for Hardware Failure</span></span>  
 <span data-ttu-id="98e07-124">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="98e07-124">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="98e07-125">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="98e07-125">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="98e07-126">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="98e07-126">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="98e07-127">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="98e07-127">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="98e07-128">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="98e07-128">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="98e07-129">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="98e07-129">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="98e07-130">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="98e07-130">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="98e07-131">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="98e07-131">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="98e07-132">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="98e07-132">Restore from Backup</span></span>  
 <span data-ttu-id="98e07-133">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="98e07-133">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="98e07-134">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="98e07-134">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="98e07-135">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="98e07-135">Not applicable.</span></span> <span data-ttu-id="98e07-136">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="98e07-136">This error cannot be repaired automatically.</span></span> <span data-ttu-id="98e07-137">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el Servicio de atención al cliente y soporte técnico (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98e07-137">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Service and Support (CSS).</span></span>  
  
  
