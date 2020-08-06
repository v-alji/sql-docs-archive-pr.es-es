---
title: MSSQLSERVER_7908 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7908 (Database Engine error)
ms.assetid: 470045b0-ebe9-44a7-b456-480e7a516a2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b80812e0e36e5bed542f7193b7422f2de37720f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672994"
---
# <a name="mssqlserver_7908"></a><span data-ttu-id="62087-102">MSSQLSERVER_7908</span><span class="sxs-lookup"><span data-stu-id="62087-102">MSSQLSERVER_7908</span></span>
    
## <a name="details"></a><span data-ttu-id="62087-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="62087-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62087-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="62087-104">Product Name</span></span>|<span data-ttu-id="62087-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="62087-105">SQL Server</span></span>|  
|<span data-ttu-id="62087-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="62087-106">Event ID</span></span>|<span data-ttu-id="62087-107">7908</span><span class="sxs-lookup"><span data-stu-id="62087-107">7908</span></span>|  
|<span data-ttu-id="62087-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="62087-108">Event Source</span></span>|<span data-ttu-id="62087-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="62087-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="62087-110">Componente</span><span class="sxs-lookup"><span data-stu-id="62087-110">Component</span></span>|<span data-ttu-id="62087-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="62087-111">SQLEngine</span></span>|  
|<span data-ttu-id="62087-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="62087-112">Symbolic Name</span></span>|<span data-ttu-id="62087-113">DBCC2_FS_INVALID_COLUMN_LEVEL_FILE</span><span class="sxs-lookup"><span data-stu-id="62087-113">DBCC2_FS_INVALID_COLUMN_LEVEL_FILE</span></span>|  
|<span data-ttu-id="62087-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="62087-114">Message Text</span></span>|<span data-ttu-id="62087-115">Error de tabla: el archivo "FILE" de la partición con id. PN_ID no es un archivo de FileStream válido.</span><span class="sxs-lookup"><span data-stu-id="62087-115">Table error: The file 'FILE' in partition ID PN_ID is not a valid Filestream file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="62087-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="62087-116">Explanation</span></span>  
 <span data-ttu-id="62087-117">El nombre de un archivo de Filestream en un directorio de columna es un ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="62087-117">The name of a FILESTREAM file in a column directory is a ROWGUID.</span></span> <span data-ttu-id="62087-118">Si el nombre de un archivo en un directorio de columna no puede convertirse en un ROWGUID, el archivo no será válido.</span><span class="sxs-lookup"><span data-stu-id="62087-118">If a file name in a column directory cannot be converted to a ROWGUID, the file is not a valid file.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62087-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="62087-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="62087-120">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="62087-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="62087-121">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="62087-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="62087-122">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="62087-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="62087-123">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="62087-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="62087-124">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="62087-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="62087-125">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="62087-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="62087-126">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="62087-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="62087-127">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="62087-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="62087-128">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="62087-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="62087-129">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="62087-129">Restore from Backup</span></span>  
 <span data-ttu-id="62087-130">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="62087-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="62087-131">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="62087-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="62087-132">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="62087-132">Not applicable.</span></span> <span data-ttu-id="62087-133">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="62087-133">This error cannot be repaired.</span></span> <span data-ttu-id="62087-134">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="62087-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
