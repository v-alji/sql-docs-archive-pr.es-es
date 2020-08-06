---
title: MSSQLSERVER_7907 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7907 (Database Engine error)
ms.assetid: a1c94e4a-7e91-46e0-9fac-07bbbf6dd018
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e09e95d9a2416ae54c40f5c8e57d9444497c579f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672997"
---
# <a name="mssqlserver_7907"></a><span data-ttu-id="4b67e-102">MSSQLSERVER_7907</span><span class="sxs-lookup"><span data-stu-id="4b67e-102">MSSQLSERVER_7907</span></span>
    
## <a name="details"></a><span data-ttu-id="4b67e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="4b67e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b67e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="4b67e-104">Product Name</span></span>|<span data-ttu-id="4b67e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="4b67e-105">SQL Server</span></span>|  
|<span data-ttu-id="4b67e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="4b67e-106">Event ID</span></span>|<span data-ttu-id="4b67e-107">7907</span><span class="sxs-lookup"><span data-stu-id="4b67e-107">7907</span></span>|  
|<span data-ttu-id="4b67e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="4b67e-108">Event Source</span></span>|<span data-ttu-id="4b67e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="4b67e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="4b67e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="4b67e-110">Component</span></span>|<span data-ttu-id="4b67e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="4b67e-111">SQLEngine</span></span>|  
|<span data-ttu-id="4b67e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="4b67e-112">Symbolic Name</span></span>|<span data-ttu-id="4b67e-113">DBCC2_FS_INVALID_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="4b67e-113">DBCC2_FS_INVALID_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="4b67e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="4b67e-114">Message Text</span></span>|<span data-ttu-id="4b67e-115">Error de tabla: el directorio "DIRECTORY" de la partición con id. PN_ID no es un directorio de Filestream válido.</span><span class="sxs-lookup"><span data-stu-id="4b67e-115">Table error: The directory 'DIRECTORY' in partition ID PN_ID is not a valid Filestream directory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b67e-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="4b67e-116">Explanation</span></span>  
 <span data-ttu-id="4b67e-117">El nombre de un directorio de columna es el Id. de columna del motor relacional de la partición.</span><span class="sxs-lookup"><span data-stu-id="4b67e-117">The name of a column directory is the relational engine column ID of the partition.</span></span> <span data-ttu-id="4b67e-118">Si un nombre de directorio de columna no se puede convertir en un Id. de columna, el directorio no es un directorio de columna válido.</span><span class="sxs-lookup"><span data-stu-id="4b67e-118">If a column directory name cannot be converted to a column ID, the directory is not a valid column directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b67e-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="4b67e-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="4b67e-120">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="4b67e-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="4b67e-121">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="4b67e-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="4b67e-122">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="4b67e-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="4b67e-123">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="4b67e-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="4b67e-124">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="4b67e-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="4b67e-125">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="4b67e-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="4b67e-126">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="4b67e-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="4b67e-127">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="4b67e-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="4b67e-128">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4b67e-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="4b67e-129">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="4b67e-129">Restore from Backup</span></span>  
 <span data-ttu-id="4b67e-130">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b67e-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="4b67e-131">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="4b67e-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="4b67e-132">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="4b67e-132">Not applicable.</span></span> <span data-ttu-id="4b67e-133">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="4b67e-133">This error cannot be repaired.</span></span> <span data-ttu-id="4b67e-134">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b67e-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
