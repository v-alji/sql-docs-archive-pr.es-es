---
title: MSSQLSERVER_5256 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5256 (Database Engine error)
ms.assetid: 6fe254b4-2926-446f-8b20-0f1d921a4615
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9146b7744e78550463cbec4c05df5fd75a049898
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747000"
---
# <a name="mssqlserver_5256"></a><span data-ttu-id="1d8ab-102">MSSQLSERVER_5256</span><span class="sxs-lookup"><span data-stu-id="1d8ab-102">MSSQLSERVER_5256</span></span>
    
## <a name="details"></a><span data-ttu-id="1d8ab-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1d8ab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d8ab-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1d8ab-104">Product Name</span></span>|<span data-ttu-id="1d8ab-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1d8ab-105">SQL Server</span></span>|  
|<span data-ttu-id="1d8ab-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1d8ab-106">Event ID</span></span>|<span data-ttu-id="1d8ab-107">5256</span><span class="sxs-lookup"><span data-stu-id="1d8ab-107">5256</span></span>|  
|<span data-ttu-id="1d8ab-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1d8ab-108">Event Source</span></span>|<span data-ttu-id="1d8ab-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1d8ab-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1d8ab-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1d8ab-110">Component</span></span>|<span data-ttu-id="1d8ab-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1d8ab-111">SQLEngine</span></span>|  
|<span data-ttu-id="1d8ab-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1d8ab-112">Symbolic Name</span></span>|<span data-ttu-id="1d8ab-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span><span class="sxs-lookup"><span data-stu-id="1d8ab-113">DBCC4_INCORRECT_PAGE_ID_IN_HEADER_NO_METADATA</span></span>|  
|<span data-ttu-id="1d8ab-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1d8ab-114">Message Text</span></span>|<span data-ttu-id="1d8ab-115">Error de tabla: Id. de unidad de asignación A_ID. En el encabezado de la página P_ID1 hay un Id. de página incorrecto.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-115">Table error: alloc unit ID A_ID, page P_ID1 contains an incorrect page ID in its page header.</span></span> <span data-ttu-id="1d8ab-116">PageId del encabezado de página = P_ID2.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-116">The PageId in the page header = P_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1d8ab-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="1d8ab-117">Explanation</span></span>  
 <span data-ttu-id="1d8ab-118">El encabezado de página de la página *P_ID1* contiene un Id. de página incorrecto, *P_ID2*.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-118">The page header of page *P_ID1* contains an incorrect page ID, *P_ID2*.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d8ab-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1d8ab-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="1d8ab-120">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="1d8ab-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="1d8ab-121">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="1d8ab-122">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="1d8ab-123">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="1d8ab-124">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="1d8ab-125">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="1d8ab-126">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="1d8ab-127">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="1d8ab-128">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="1d8ab-129">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="1d8ab-129">Restore from Backup</span></span>  
 <span data-ttu-id="1d8ab-130">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="1d8ab-131">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="1d8ab-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="1d8ab-132">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-132">Not applicable.</span></span> <span data-ttu-id="1d8ab-133">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="1d8ab-133">This error cannot be repaired.</span></span> <span data-ttu-id="1d8ab-134">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1d8ab-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
