---
title: MSSQLSERVER_5229 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5229 (Database Engine error)
ms.assetid: 0d9e50da-4f42-4b3a-bc84-daf05cf0e0e5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 12cc4631dec430b9c4ad63f06fa20819ba3d82ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744710"
---
# <a name="mssqlserver_5229"></a><span data-ttu-id="21092-102">MSSQLSERVER_5229</span><span class="sxs-lookup"><span data-stu-id="21092-102">MSSQLSERVER_5229</span></span>
    
## <a name="details"></a><span data-ttu-id="21092-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="21092-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21092-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="21092-104">Product Name</span></span>|<span data-ttu-id="21092-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="21092-105">SQL Server</span></span>|  
|<span data-ttu-id="21092-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="21092-106">Event ID</span></span>|<span data-ttu-id="21092-107">5229</span><span class="sxs-lookup"><span data-stu-id="21092-107">5229</span></span>|  
|<span data-ttu-id="21092-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="21092-108">Event Source</span></span>|<span data-ttu-id="21092-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="21092-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="21092-110">Componente</span><span class="sxs-lookup"><span data-stu-id="21092-110">Component</span></span>|<span data-ttu-id="21092-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="21092-111">SQLEngine</span></span>|  
|<span data-ttu-id="21092-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="21092-112">Symbolic Name</span></span>|<span data-ttu-id="21092-113">DBCC4_ANTIMATTER_IN_HEAP_OR_CLUSTERED_INDEX</span><span class="sxs-lookup"><span data-stu-id="21092-113">DBCC4_ANTIMATTER_IN_HEAP_OR_CLUSTERED_INDEX</span></span>|  
|<span data-ttu-id="21092-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="21092-114">Message Text</span></span>|<span data-ttu-id="21092-115">Error de tabla: el id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, id. de unidad de asignación A_ID (tipo TYPE) contiene una columna antimateria, pero no es un índice no clúster.</span><span class="sxs-lookup"><span data-stu-id="21092-115">Table error: Object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) contains an anti-matter column, but is not a nonclustered index.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="21092-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="21092-116">Explanation</span></span>  
 <span data-ttu-id="21092-117">Un montón o índice clúster contiene una columna antimateria, aunque no debería.</span><span class="sxs-lookup"><span data-stu-id="21092-117">A heap or clustered index contains an antimatter column, but should not.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21092-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="21092-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="21092-119">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="21092-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="21092-120">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="21092-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="21092-121">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="21092-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="21092-122">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="21092-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="21092-123">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="21092-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="21092-124">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="21092-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="21092-125">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="21092-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="21092-126">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="21092-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="21092-127">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="21092-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="21092-128">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="21092-128">Restore from Backup</span></span>  
 <span data-ttu-id="21092-129">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="21092-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="21092-130">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="21092-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="21092-131">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="21092-131">Not applicable.</span></span> <span data-ttu-id="21092-132">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="21092-132">This error cannot be repaired.</span></span> <span data-ttu-id="21092-133">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="21092-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
