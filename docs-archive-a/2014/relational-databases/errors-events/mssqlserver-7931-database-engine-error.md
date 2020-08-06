---
title: MSSQLSERVER_7931 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7931 (Database Engine error)
ms.assetid: 18e7a3dc-7d8a-41b9-8724-d2a8587b6903
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a93cc56869448d1dbcf95c1d9e1ffe1fe023e7e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673701"
---
# <a name="mssqlserver_7931"></a><span data-ttu-id="b865e-102">MSSQLSERVER_7931</span><span class="sxs-lookup"><span data-stu-id="b865e-102">MSSQLSERVER_7931</span></span>
    
## <a name="details"></a><span data-ttu-id="b865e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b865e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b865e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b865e-104">Product Name</span></span>|<span data-ttu-id="b865e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b865e-105">SQL Server</span></span>|  
|<span data-ttu-id="b865e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b865e-106">Event ID</span></span>|<span data-ttu-id="b865e-107">7931</span><span class="sxs-lookup"><span data-stu-id="b865e-107">7931</span></span>|  
|<span data-ttu-id="b865e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b865e-108">Event Source</span></span>|<span data-ttu-id="b865e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b865e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b865e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b865e-110">Component</span></span>|<span data-ttu-id="b865e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b865e-111">SQLEngine</span></span>|  
|<span data-ttu-id="b865e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b865e-112">Symbolic Name</span></span>|<span data-ttu-id="b865e-113">DBCC2_FS_DOUBLE_ROWSET_ACTUAL_FACT</span><span class="sxs-lookup"><span data-stu-id="b865e-113">DBCC2_FS_DOUBLE_ROWSET_ACTUAL_FACT</span></span>|  
|<span data-ttu-id="b865e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b865e-114">Message Text</span></span>|<span data-ttu-id="b865e-115">Error de base de datos: el id. de directorio FILESTREAM F_ID para una partición se ha visto dos veces.</span><span class="sxs-lookup"><span data-stu-id="b865e-115">Database error: The FileStream directory ID F_ID for a partition was seen twice.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b865e-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b865e-116">Explanation</span></span>  
 <span data-ttu-id="b865e-117">Se ha encontrado en los metadatos el mismo identificador de partición para un directorio FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="b865e-117">The same partition ID for a Filestream directory was found in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b865e-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b865e-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b865e-119">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="b865e-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b865e-120">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="b865e-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b865e-121">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="b865e-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b865e-122">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="b865e-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b865e-123">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="b865e-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b865e-124">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="b865e-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b865e-125">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="b865e-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b865e-126">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="b865e-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b865e-127">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b865e-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b865e-128">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b865e-128">Restore from Backup</span></span>  
 <span data-ttu-id="b865e-129">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b865e-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b865e-130">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b865e-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b865e-131">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="b865e-131">Not applicable.</span></span> <span data-ttu-id="b865e-132">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b865e-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="b865e-133">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b865e-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
