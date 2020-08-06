---
title: MSSQLSERVER_7903 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7903 (Database Engine error)
ms.assetid: 991a86df-42cd-435e-85b3-f42e4cb13039
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e30247c5c858cf8ce6dcd75e41f1fb567e974201
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673002"
---
# <a name="mssqlserver_7903"></a><span data-ttu-id="b8f90-102">MSSQLSERVER_7903</span><span class="sxs-lookup"><span data-stu-id="b8f90-102">MSSQLSERVER_7903</span></span>
    
## <a name="details"></a><span data-ttu-id="b8f90-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b8f90-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b8f90-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="b8f90-104">Product Name</span></span>|<span data-ttu-id="b8f90-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8f90-105">SQL Server</span></span>|  
|<span data-ttu-id="b8f90-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="b8f90-106">Event ID</span></span>|<span data-ttu-id="b8f90-107">7903</span><span class="sxs-lookup"><span data-stu-id="b8f90-107">7903</span></span>|  
|<span data-ttu-id="b8f90-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="b8f90-108">Event Source</span></span>|<span data-ttu-id="b8f90-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b8f90-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b8f90-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b8f90-110">Component</span></span>|<span data-ttu-id="b8f90-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b8f90-111">SQLEngine</span></span>|  
|<span data-ttu-id="b8f90-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b8f90-112">Symbolic Name</span></span>|<span data-ttu-id="b8f90-113">DBCC2_FS_ORPHANED_FILE</span><span class="sxs-lookup"><span data-stu-id="b8f90-113">DBCC2_FS_ORPHANED_FILE</span></span>|  
|<span data-ttu-id="b8f90-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b8f90-114">Message Text</span></span>|<span data-ttu-id="b8f90-115">Error de tabla: se encontró el archivo huérfano "FILE" en el id. de directorio FileStream para el id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID e id. de columna C_ID.</span><span class="sxs-lookup"><span data-stu-id="b8f90-115">Table error: The orphaned file 'FILE' was found in the Filestream directory for object ID O_ID, index ID I_ID, partition ID PN_ID, column ID C_ID.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b8f90-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="b8f90-116">Explanation</span></span>  
 <span data-ttu-id="b8f90-117">Había un archivo de FILESTREAM en el directorio de columna de FILESTREAM, pero falta el valor de columna correspondiente en la partición.</span><span class="sxs-lookup"><span data-stu-id="b8f90-117">A FILESTREAM file was found in a FILESTREAM column directory; however, the corresponding column value in the partition is missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b8f90-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b8f90-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="b8f90-119">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="b8f90-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="b8f90-120">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="b8f90-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="b8f90-121">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="b8f90-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="b8f90-122">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="b8f90-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="b8f90-123">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="b8f90-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="b8f90-124">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="b8f90-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="b8f90-125">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="b8f90-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="b8f90-126">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="b8f90-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="b8f90-127">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b8f90-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="b8f90-128">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="b8f90-128">Restore from Backup</span></span>  
 <span data-ttu-id="b8f90-129">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="b8f90-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="b8f90-130">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="b8f90-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="b8f90-131">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="b8f90-131">Not applicable.</span></span> <span data-ttu-id="b8f90-132">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="b8f90-132">This error cannot be repaired.</span></span> <span data-ttu-id="b8f90-133">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8f90-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
