---
title: MSSQLSERVER_7936 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7936 (Database Engine error)
ms.assetid: d78fc8a9-d173-4801-bb32-ed6a29257f08
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c478e998b6185b0a8e22cd99caf2be4fc2fdee33
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675424"
---
# <a name="mssqlserver_7936"></a><span data-ttu-id="7e15e-102">MSSQLSERVER_7936</span><span class="sxs-lookup"><span data-stu-id="7e15e-102">MSSQLSERVER_7936</span></span>
    
## <a name="details"></a><span data-ttu-id="7e15e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7e15e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e15e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7e15e-104">Product Name</span></span>|<span data-ttu-id="7e15e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e15e-105">SQL Server</span></span>|  
|<span data-ttu-id="7e15e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7e15e-106">Event ID</span></span>|<span data-ttu-id="7e15e-107">7936</span><span class="sxs-lookup"><span data-stu-id="7e15e-107">7936</span></span>|  
|<span data-ttu-id="7e15e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7e15e-108">Event Source</span></span>|<span data-ttu-id="7e15e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7e15e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7e15e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7e15e-110">Component</span></span>|<span data-ttu-id="7e15e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7e15e-111">SQLEngine</span></span>|  
|<span data-ttu-id="7e15e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7e15e-112">Symbolic Name</span></span>|<span data-ttu-id="7e15e-113">DBCC2_FS_ORPHANED_COLUMN_DIRECTORY</span><span class="sxs-lookup"><span data-stu-id="7e15e-113">DBCC2_FS_ORPHANED_COLUMN_DIRECTORY</span></span>|  
|<span data-ttu-id="7e15e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7e15e-114">Message Text</span></span>|<span data-ttu-id="7e15e-115">Error de tabla: el id. de directorio FILESTREAM existe para el id. de columna C_ID del id. de objeto O_ID, id. de índice I_ID, id. de partición PN_ID, pero esa columna no es una columna FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="7e15e-115">Table error: Filestream directory exists for column ID C_ID of object ID O_ID, index ID I_ID, partition ID PN_ID, but that column is not a Filestream column.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7e15e-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="7e15e-116">Explanation</span></span>  
 <span data-ttu-id="7e15e-117">Durante DBCC CHECKDB, se encontró un directorio FILESTREAM para la columna especificada; sin embargo, la columna no es una columna `FILESTREAM`.</span><span class="sxs-lookup"><span data-stu-id="7e15e-117">During DBCC CHECKDB, a FILESTREAM directory was found for the specified column; however, the column is not a `FILESTREAM` column.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7e15e-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7e15e-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="7e15e-119">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="7e15e-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="7e15e-120">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="7e15e-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="7e15e-121">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="7e15e-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="7e15e-122">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="7e15e-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="7e15e-123">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="7e15e-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="7e15e-124">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="7e15e-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="7e15e-125">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="7e15e-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="7e15e-126">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="7e15e-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="7e15e-127">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7e15e-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="7e15e-128">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="7e15e-128">Restore from Backup</span></span>  
 <span data-ttu-id="7e15e-129">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7e15e-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="7e15e-130">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="7e15e-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="7e15e-131">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="7e15e-131">Not applicable.</span></span> <span data-ttu-id="7e15e-132">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7e15e-132">This error cannot be repaired automatically.</span></span> <span data-ttu-id="7e15e-133">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e15e-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
