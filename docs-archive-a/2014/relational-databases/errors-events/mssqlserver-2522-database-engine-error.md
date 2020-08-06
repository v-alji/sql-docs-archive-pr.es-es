---
title: MSSQLSERVER_2522 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2522 (Database Engine error)
ms.assetid: 19b9b00c-330f-4dd3-9052-9d88bce83849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 60446c21599c02ee9c4bc96789b106b49b71582a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662993"
---
# <a name="mssqlserver_2522"></a><span data-ttu-id="27b75-102">MSSQLSERVER_2522</span><span class="sxs-lookup"><span data-stu-id="27b75-102">MSSQLSERVER_2522</span></span>
    
## <a name="details"></a><span data-ttu-id="27b75-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="27b75-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="27b75-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="27b75-104">Product Name</span></span>|<span data-ttu-id="27b75-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="27b75-105">SQL Server</span></span>|  
|<span data-ttu-id="27b75-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="27b75-106">Event ID</span></span>|<span data-ttu-id="27b75-107">2522</span><span class="sxs-lookup"><span data-stu-id="27b75-107">2522</span></span>|  
|<span data-ttu-id="27b75-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="27b75-108">Event Source</span></span>|<span data-ttu-id="27b75-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="27b75-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="27b75-110">Componente</span><span class="sxs-lookup"><span data-stu-id="27b75-110">Component</span></span>|<span data-ttu-id="27b75-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="27b75-111">SQLEngine</span></span>|  
|<span data-ttu-id="27b75-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="27b75-112">Symbolic Name</span></span>|<span data-ttu-id="27b75-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="27b75-113">DBCC_INDEX_FILEGROUP_IS_INVALID</span></span>|  
|<span data-ttu-id="27b75-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="27b75-114">Message Text</span></span>|<span data-ttu-id="27b75-115">No se puede procesar el índice I_NAME de la tabla O_NAME porque el grupo de archivos F_NAME no es válido.</span><span class="sxs-lookup"><span data-stu-id="27b75-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is invalid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="27b75-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="27b75-116">Explanation</span></span>  
 <span data-ttu-id="27b75-117">Este mensaje informativo indica que no se puede comprobar el índice porque uno de los identificadores del grupo de archivos que está almacenado en los metadatos del índice no existe.</span><span class="sxs-lookup"><span data-stu-id="27b75-117">This informational message indicates that the index cannot be checked because one of the filegroup IDs that is stored in the metadata of the index does not exist.</span></span> <span data-ttu-id="27b75-118">El Id. del grupo de archivos que no es válido puede pertenecer a los propios datos, a los datos de objetos grandes (LOB) o a los datos de desbordamiento de fila.</span><span class="sxs-lookup"><span data-stu-id="27b75-118">The filegroup ID that is not valid might pertain to the data itself, or to the large object (LOB) data, or to the row-overflow data.</span></span>  
  
 <span data-ttu-id="27b75-119">Si no hay ningún problema, todos los demás índices del mismo objeto se comprobarán.</span><span class="sxs-lookup"><span data-stu-id="27b75-119">If there are no problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="27b75-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="27b75-120">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="27b75-121">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="27b75-121">Look for Hardware Failure</span></span>  
 <span data-ttu-id="27b75-122">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="27b75-122">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="27b75-123">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="27b75-123">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="27b75-124">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="27b75-124">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="27b75-125">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="27b75-125">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="27b75-126">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="27b75-126">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="27b75-127">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="27b75-127">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="27b75-128">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="27b75-128">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="27b75-129">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="27b75-129">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="27b75-130">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="27b75-130">Restore from Backup</span></span>  
 <span data-ttu-id="27b75-131">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="27b75-131">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="27b75-132">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="27b75-132">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="27b75-133">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="27b75-133">Not applicable.</span></span> <span data-ttu-id="27b75-134">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="27b75-134">This error cannot be repaired automatically.</span></span>  
  
  
