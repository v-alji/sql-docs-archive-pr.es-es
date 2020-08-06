---
title: MSSQLSERVER_7932 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7932 (Database Engine error)
ms.assetid: e2ad218a-3249-4f18-8b32-09f0030765a5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 237d9be3e0f22664adb061d3bba526c9878d3bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673700"
---
# <a name="mssqlserver_7932"></a><span data-ttu-id="71f37-102">MSSQLSERVER_7932</span><span class="sxs-lookup"><span data-stu-id="71f37-102">MSSQLSERVER_7932</span></span>
    
## <a name="details"></a><span data-ttu-id="71f37-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="71f37-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="71f37-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="71f37-104">Product Name</span></span>|<span data-ttu-id="71f37-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="71f37-105">SQL Server</span></span>|  
|<span data-ttu-id="71f37-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="71f37-106">Event ID</span></span>|<span data-ttu-id="71f37-107">7932</span><span class="sxs-lookup"><span data-stu-id="71f37-107">7932</span></span>|  
|<span data-ttu-id="71f37-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="71f37-108">Event Source</span></span>|<span data-ttu-id="71f37-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="71f37-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="71f37-110">Componente</span><span class="sxs-lookup"><span data-stu-id="71f37-110">Component</span></span>|<span data-ttu-id="71f37-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="71f37-111">SQLEngine</span></span>|  
|<span data-ttu-id="71f37-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="71f37-112">Symbolic Name</span></span>|<span data-ttu-id="71f37-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span><span class="sxs-lookup"><span data-stu-id="71f37-113">DBCC2_FS_ROWSET_IN_WRONG_FILEGROUP</span></span>|  
|<span data-ttu-id="71f37-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="71f37-114">Message Text</span></span>|<span data-ttu-id="71f37-115">Error de tabla: el id. de directorio FILESTREAM para el id. de objeto O_ID, id. de índice I_ID e id. de partición PN_ID está en el grupo de archivos FG_ID1, pero debería estar en el grupo de archivos FG_ID2.</span><span class="sxs-lookup"><span data-stu-id="71f37-115">Table error: The FileStream directory ID F_ID for object ID O_ID, index ID I_ID, partition ID PN_ID is in filegroup FG_ID1, but should be in filegroup FG_ID2.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="71f37-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="71f37-116">Explanation</span></span>  
 <span data-ttu-id="71f37-117">Durante DBCC CHECKDB, se detectó que el almacenamiento FILESTREAM para el objeto especificado estaba en un grupo de archivos incorrecto.</span><span class="sxs-lookup"><span data-stu-id="71f37-117">During DBCC CHECKDB, the FILESTREAM storage for the specified object was detected in the wrong filegroup.</span></span> <span data-ttu-id="71f37-118">Los metadatos del objeto podrían haberse dañado.</span><span class="sxs-lookup"><span data-stu-id="71f37-118">This could be a corruption in the metadata of the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="71f37-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="71f37-119">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="71f37-120">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="71f37-120">Look for Hardware Failure</span></span>  
 <span data-ttu-id="71f37-121">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="71f37-121">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="71f37-122">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="71f37-122">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred as the result of hardware failure.</span></span> <span data-ttu-id="71f37-123">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="71f37-123">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="71f37-124">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="71f37-124">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="71f37-125">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="71f37-125">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="71f37-126">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="71f37-126">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="71f37-127">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="71f37-127">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="71f37-128">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="71f37-128">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="71f37-129">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="71f37-129">Restore from Backup</span></span>  
 <span data-ttu-id="71f37-130">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="71f37-130">If the problem is not hardware related and a known clean backup is available, restore the database from the backup.</span></span>  
  
### <a name="run-dbcc-checkdb"></a><span data-ttu-id="71f37-131">Ejecute DBCC CHECKDB</span><span class="sxs-lookup"><span data-stu-id="71f37-131">Run DBCC CHECKDB</span></span>  
 <span data-ttu-id="71f37-132">No aplicable.</span><span class="sxs-lookup"><span data-stu-id="71f37-132">Not applicable.</span></span> <span data-ttu-id="71f37-133">Este error no puede repararse automáticamente.</span><span class="sxs-lookup"><span data-stu-id="71f37-133">This error cannot be repaired automatically.</span></span> <span data-ttu-id="71f37-134">Si no puede restaurar la base de datos a partir de una copia de seguridad, póngase en contacto con el servicio de soporte técnico y atención al cliente (CSS) de [!INCLUDE[msCoName](../../includes/msconame-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71f37-134">If you cannot restore the database from a backup, contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support (CSS).</span></span>  
  
  
