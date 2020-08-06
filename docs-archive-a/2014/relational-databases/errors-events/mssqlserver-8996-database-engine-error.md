---
title: MSSQLSERVER_8996 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8996 (Database Engine error)
ms.assetid: 4e655cdc-945a-4a18-95dd-75f050563d26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6d0cb5f0294ea471a6e300adbabc0f7b55632994
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675872"
---
# <a name="mssqlserver_8996"></a><span data-ttu-id="a7a64-102">MSSQLSERVER_8996</span><span class="sxs-lookup"><span data-stu-id="a7a64-102">MSSQLSERVER_8996</span></span>
    
## <a name="details"></a><span data-ttu-id="a7a64-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="a7a64-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7a64-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a7a64-104">Product Name</span></span>|<span data-ttu-id="a7a64-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a7a64-105">SQL Server</span></span>|  
|<span data-ttu-id="a7a64-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a7a64-106">Event ID</span></span>|<span data-ttu-id="a7a64-107">8996</span><span class="sxs-lookup"><span data-stu-id="a7a64-107">8996</span></span>|  
|<span data-ttu-id="a7a64-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a7a64-108">Event Source</span></span>|<span data-ttu-id="a7a64-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a7a64-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a7a64-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a7a64-110">Component</span></span>|<span data-ttu-id="a7a64-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a7a64-111">SQLEngine</span></span>|  
|<span data-ttu-id="a7a64-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a7a64-112">Symbolic Name</span></span>|<span data-ttu-id="a7a64-113">DBCC3_IAM_PAGE_RANGE_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="a7a64-113">DBCC3_IAM_PAGE_RANGE_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="a7a64-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a7a64-114">Message Text</span></span>|<span data-ttu-id="a7a64-115">La página IAM P_ID del Id. de objeto O_ID, Id. de índice I_ID, Id. de partición PN_ID, Id. de unidad de asignación A_ID (tipo TYPE) controla las páginas del grupo de archivos FG_ID1 que deberían estar en el grupo de archivos FG_ID2.</span><span class="sxs-lookup"><span data-stu-id="a7a64-115">IAM page P_ID for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE) controls pages in filegroup FG_ID1, that should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a7a64-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a7a64-116">Explanation</span></span>  
 <span data-ttu-id="a7a64-117">La página del Mapa de asignación de índices (IAM) *P_ID* del grupo de archivos *FG_ID1* incluye incorrectamente extensiones del grupo de archivos *FG_ID2*.</span><span class="sxs-lookup"><span data-stu-id="a7a64-117">The index allocation map (IAM) page *P_ID* in filegroup *FG_ID1* incorrectly includes extents from filegroup *FG_ID2*.</span></span> <span data-ttu-id="a7a64-118">Todas las extensiones de una página IAM deben estar en el mismo grupo de archivos que la página IAM.</span><span class="sxs-lookup"><span data-stu-id="a7a64-118">All extents for an IAM page should be in the same filegroup as the IAM page itself.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a7a64-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a7a64-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="a7a64-120">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="a7a64-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="a7a64-121">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="a7a64-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="a7a64-122">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="a7a64-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="a7a64-123">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="a7a64-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="a7a64-124">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="a7a64-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="a7a64-125">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="a7a64-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="a7a64-126">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="a7a64-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="a7a64-127">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="a7a64-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="a7a64-128">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a7a64-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="a7a64-129">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="a7a64-129">Restore from Backup</span></span>  
 <span data-ttu-id="a7a64-130">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="a7a64-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="a7a64-131">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="a7a64-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="a7a64-132">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="a7a64-132">Not applicable.</span></span> <span data-ttu-id="a7a64-133">Este error no se puede reparar.</span><span class="sxs-lookup"><span data-stu-id="a7a64-133">This error cannot be repaired.</span></span> <span data-ttu-id="a7a64-134">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7a64-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
