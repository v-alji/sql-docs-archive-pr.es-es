---
title: MSSQLSERVER_2540 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2540 (Database Engine error)
ms.assetid: eb5ee2be-acbb-4fb7-9b45-dc6200bde06e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4a49abeadcd49263ea7d0701ee468a36882179cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744715"
---
# <a name="mssqlserver_2540"></a><span data-ttu-id="b782c-102">MSSQLSERVER_2540</span><span class="sxs-lookup"><span data-stu-id="b782c-102">MSSQLSERVER_2540</span></span>
    
## <a name="details"></a><span data-ttu-id="b782c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b782c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b782c-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b782c-104">Product Name</span></span>|<span data-ttu-id="b782c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b782c-105">SQL Server</span></span>|  
|<span data-ttu-id="b782c-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b782c-106">Event ID</span></span>|<span data-ttu-id="b782c-107">2540</span><span class="sxs-lookup"><span data-stu-id="b782c-107">2540</span></span>|  
|<span data-ttu-id="b782c-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b782c-108">Event Source</span></span>|<span data-ttu-id="b782c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b782c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b782c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b782c-110">Component</span></span>|<span data-ttu-id="b782c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b782c-111">SQLEngine</span></span>|  
|<span data-ttu-id="b782c-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b782c-112">Symbolic Name</span></span>|<span data-ttu-id="b782c-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span><span class="sxs-lookup"><span data-stu-id="b782c-113">DBCC_REPAIR_ERROR_NOT_REPAIRABLE</span></span>|  
|<span data-ttu-id="b782c-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b782c-114">Message Text</span></span>|<span data-ttu-id="b782c-115">El sistema no puede reparar el error por sí solo.</span><span class="sxs-lookup"><span data-stu-id="b782c-115">The system cannot self repair this error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b782c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b782c-116">Explanation</span></span>  
 <span data-ttu-id="b782c-117">Este mensaje de error indica problemas que no se pueden reparar automáticamente, como daños en metadatos, daños en páginas PFS (Espacio disponible de página) o daños en determinadas tablas base críticas del sistema.</span><span class="sxs-lookup"><span data-stu-id="b782c-117">This error message indicates problems that cannot be repaired automatically, such as corrupt metadata, Page Free Space (PFS) page corruptions, or corruptions in certain critical system base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b782c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b782c-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b782c-119">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="b782c-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b782c-120">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="b782c-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b782c-121">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="b782c-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b782c-122">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="b782c-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b782c-123">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="b782c-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b782c-124">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="b782c-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b782c-125">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="b782c-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b782c-126">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="b782c-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b782c-127">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b782c-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b782c-128">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b782c-128">Restore from Backup</span></span>  
 <span data-ttu-id="b782c-129">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b782c-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b782c-130">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b782c-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b782c-131">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="b782c-131">Not applicable.</span></span> <span data-ttu-id="b782c-132">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b782c-132">This error cannot be repaired automatically.</span></span>  
  
  
