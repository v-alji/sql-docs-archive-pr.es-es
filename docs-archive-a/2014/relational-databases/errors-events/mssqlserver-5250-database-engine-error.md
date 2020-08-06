---
title: MSSQLSERVER_5250 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5250 (Database Engine error)
ms.assetid: f4a1d0e8-f27f-4cb8-a25d-040b40555dcc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ace26b88aca5b00c23aff3fe48f7c1d04ef35245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747002"
---
# <a name="mssqlserver_5250"></a><span data-ttu-id="b8c51-102">MSSQLSERVER_5250</span><span class="sxs-lookup"><span data-stu-id="b8c51-102">MSSQLSERVER_5250</span></span>
    
## <a name="details"></a><span data-ttu-id="b8c51-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b8c51-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8c51-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b8c51-104">Product Name</span></span>|<span data-ttu-id="b8c51-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8c51-105">SQL Server</span></span>|  
|<span data-ttu-id="b8c51-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b8c51-106">Event ID</span></span>|<span data-ttu-id="b8c51-107">5250</span><span class="sxs-lookup"><span data-stu-id="b8c51-107">5250</span></span>|  
|<span data-ttu-id="b8c51-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b8c51-108">Event Source</span></span>|<span data-ttu-id="b8c51-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b8c51-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b8c51-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b8c51-110">Component</span></span>|<span data-ttu-id="b8c51-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b8c51-111">SQLEngine</span></span>|  
|<span data-ttu-id="b8c51-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b8c51-112">Symbolic Name</span></span>|<span data-ttu-id="b8c51-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="b8c51-113">DBCC4_CRITICAL_DATABASE_PAGE_CORRUPT</span></span>|  
|<span data-ttu-id="b8c51-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b8c51-114">Message Text</span></span>|<span data-ttu-id="b8c51-115">Error de base de datos: PAGE_TYPE página P_ID de la base de datos 'NAME' (id. de base de datos DB_ID) no válido.</span><span class="sxs-lookup"><span data-stu-id="b8c51-115">Database error: PAGE_TYPE page P_ID for database 'NAME' (database ID DB_ID) is invalid.</span></span> <span data-ttu-id="b8c51-116">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="b8c51-116">This error cannot be repaired.</span></span> <span data-ttu-id="b8c51-117">Debe restaurar una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="b8c51-117">You must restore from backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b8c51-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="b8c51-118">Explanation</span></span>  
 <span data-ttu-id="b8c51-119">Hay una página de encabezado de archivo o página de arranque dañada en la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="b8c51-119">A file header page or boot page in the specified database is corrupted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8c51-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b8c51-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b8c51-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="b8c51-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b8c51-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="b8c51-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b8c51-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="b8c51-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b8c51-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="b8c51-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b8c51-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="b8c51-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b8c51-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="b8c51-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b8c51-127">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="b8c51-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b8c51-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="b8c51-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b8c51-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b8c51-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b8c51-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b8c51-130">Restore from Backup</span></span>  
 <span data-ttu-id="b8c51-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8c51-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b8c51-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b8c51-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b8c51-133">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="b8c51-133">Not applicable.</span></span> <span data-ttu-id="b8c51-134">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="b8c51-134">This error cannot be repaired.</span></span> <span data-ttu-id="b8c51-135">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8c51-135">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
