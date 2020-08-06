---
title: MSSQLSERVER_7906 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7906 (Database Engine error)
ms.assetid: 9638a764-4ac1-40ae-a614-2726ebcc6ba4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 57485a8f330f186a4abd83182c6035168ed38e0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672998"
---
# <a name="mssqlserver_7906"></a><span data-ttu-id="a3d4b-102">MSSQLSERVER_7906</span><span class="sxs-lookup"><span data-stu-id="a3d4b-102">MSSQLSERVER_7906</span></span>
    
## <a name="details"></a><span data-ttu-id="a3d4b-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a3d4b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3d4b-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a3d4b-104">Product Name</span></span>|<span data-ttu-id="a3d4b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3d4b-105">SQL Server</span></span>|  
|<span data-ttu-id="a3d4b-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a3d4b-106">Event ID</span></span>|<span data-ttu-id="a3d4b-107">7906</span><span class="sxs-lookup"><span data-stu-id="a3d4b-107">7906</span></span>|  
|<span data-ttu-id="a3d4b-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a3d4b-108">Event Source</span></span>|<span data-ttu-id="a3d4b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3d4b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3d4b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3d4b-110">Component</span></span>|<span data-ttu-id="a3d4b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a3d4b-111">SQLEngine</span></span>|  
|<span data-ttu-id="a3d4b-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a3d4b-112">Symbolic Name</span></span>|<span data-ttu-id="a3d4b-113">DBCC2_FS_INVALID_TOP_LEVEL_FILE</span><span class="sxs-lookup"><span data-stu-id="a3d4b-113">DBCC2_FS_INVALID_TOP_LEVEL_FILE</span></span>|  
|<span data-ttu-id="a3d4b-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a3d4b-114">Message Text</span></span>|<span data-ttu-id="a3d4b-115">Error de base de datos: el archivo "File" no es un archivo de Filestream válido.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-115">Database error: The file 'FILE' is not a valid Filestream file.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3d4b-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a3d4b-116">Explanation</span></span>  
 <span data-ttu-id="a3d4b-117">Con la excepción de algunos archivos especiales, como "filestream.hdr", no debería haber ningún archivo directamente en el espacio de datos de Filestream.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-117">Except for some special files such as, 'filestream.hdr', no files should be found directly under the Filestream dataspace.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3d4b-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a3d4b-118">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a3d4b-119">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="a3d4b-119">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a3d4b-120">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-120">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a3d4b-121">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-121">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a3d4b-122">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-122">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a3d4b-123">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-123">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a3d4b-124">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-124">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a3d4b-125">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-125">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a3d4b-126">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-126">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a3d4b-127">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-127">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a3d4b-128">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="a3d4b-128">Restore from Backup</span></span>  
 <span data-ttu-id="a3d4b-129">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-129">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a3d4b-130">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a3d4b-130">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a3d4b-131">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-131">Not applicable.</span></span> <span data-ttu-id="a3d4b-132">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="a3d4b-132">This error cannot be repaired.</span></span> <span data-ttu-id="a3d4b-133">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3d4b-133">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
