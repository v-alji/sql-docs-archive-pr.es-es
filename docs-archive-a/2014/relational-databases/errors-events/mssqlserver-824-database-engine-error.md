---
title: MSSQLSERVER_824 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 824 (Database Engine error)
ms.assetid: 2aa22246-2712-4fdb-9744-36e7e6f3175e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d57b19bc8c837b92b65728fbb0046039b862d31a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672986"
---
# <a name="mssqlserver_824"></a><span data-ttu-id="7d589-102">MSSQLSERVER_824</span><span class="sxs-lookup"><span data-stu-id="7d589-102">MSSQLSERVER_824</span></span>
    
## <a name="details"></a><span data-ttu-id="7d589-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="7d589-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7d589-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="7d589-104">Product Name</span></span>|<span data-ttu-id="7d589-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7d589-105">SQL Server</span></span>|  
|<span data-ttu-id="7d589-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="7d589-106">Event ID</span></span>|<span data-ttu-id="7d589-107">824</span><span class="sxs-lookup"><span data-stu-id="7d589-107">824</span></span>|  
|<span data-ttu-id="7d589-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="7d589-108">Event Source</span></span>|<span data-ttu-id="7d589-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7d589-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7d589-110">Componente</span><span class="sxs-lookup"><span data-stu-id="7d589-110">Component</span></span>|<span data-ttu-id="7d589-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7d589-111">SQLEngine</span></span>|  
|<span data-ttu-id="7d589-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="7d589-112">Symbolic Name</span></span>|<span data-ttu-id="7d589-113">B_HARDSSERR</span><span class="sxs-lookup"><span data-stu-id="7d589-113">B_HARDSSERR</span></span>|  
|<span data-ttu-id="7d589-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="7d589-114">Message Text</span></span>|<span data-ttu-id="7d589-115">SQL Server detectó un error de E/S de coherencia lógico: %ls.</span><span class="sxs-lookup"><span data-stu-id="7d589-115">SQL Server detected a logical consistency-based I/O error: %ls.</span></span> <span data-ttu-id="7d589-116">Ocurrió durante %S_MSG de la página %S_PGID en la base de datos con id. %d, desplazamiento %#016I64x, archivo '%ls'.</span><span class="sxs-lookup"><span data-stu-id="7d589-116">It occurred during a %S_MSG of page %S_PGID in database ID %d at offset %#016I64x in file '%ls'.</span></span>  <span data-ttu-id="7d589-117">El registro de errores de SQL Server o el registro de eventos del sistema pueden contener mensajes adicionales con más detalles.</span><span class="sxs-lookup"><span data-stu-id="7d589-117">Additional messages in the SQL Server error log or system event log may provide more detail.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7d589-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="7d589-118">Explanation</span></span>  
 <span data-ttu-id="7d589-119">Este error indica que Windows informa de que la página se lee correctamente desde el disco, pero [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ha detectado algún problema en ella.</span><span class="sxs-lookup"><span data-stu-id="7d589-119">This error indicates that Windows reports that the page is successfully read from disk, but [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has discovered something wrong with the page.</span></span> <span data-ttu-id="7d589-120">Este error es similar al error 823, solo que Windows no detectó el error.</span><span class="sxs-lookup"><span data-stu-id="7d589-120">This error is similar to error 823 except that Windows did not detect the error.</span></span> <span data-ttu-id="7d589-121">Normalmente, suele indicar un problema en el subsistema de E/S, como errores en la unidad de disco, problemas de firmware, un controlador de dispositivo defectuoso, etc.</span><span class="sxs-lookup"><span data-stu-id="7d589-121">This usually indicates a problem in the I/O subsystem, such as a failing disk drive, disk firmware problems, faulty device driver, and so on.</span></span> <span data-ttu-id="7d589-122">Para obtener más información sobre los errores de E/S, vea el [capítulo 2 del documento sobre conceptos básicos de E/S de Microsoft SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="7d589-122">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7d589-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="7d589-123">User Action</span></span>  
  
### <a name="look-for-hardware-failure"></a><span data-ttu-id="7d589-124">Busque un error de hardware</span><span class="sxs-lookup"><span data-stu-id="7d589-124">Look for Hardware Failure</span></span>  
 <span data-ttu-id="7d589-125">Ejecute un diagnóstico de hardware y corrija cualquier problema.</span><span class="sxs-lookup"><span data-stu-id="7d589-125">Run hardware diagnostics and correct any problems.</span></span> <span data-ttu-id="7d589-126">Examine también los registros del sistema y de aplicación de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, así como el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para ver si el error se produjo como resultado de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="7d589-126">Also examine the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows system and application logs and the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to see whether the error occurred because of hardware failure.</span></span> <span data-ttu-id="7d589-127">Arregle cualquier problema relacionado con el hardware que encuentre en estos registros.</span><span class="sxs-lookup"><span data-stu-id="7d589-127">Fix any hardware-related problems that are contained in the logs.</span></span>  
  
 <span data-ttu-id="7d589-128">Si sigue teniendo problemas de datos dañados, intente intercambiar diferentes componentes de hardware para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="7d589-128">If you have persistent data corruption problems, try to swap out different hardware components to isolate the problem.</span></span> <span data-ttu-id="7d589-129">Asegúrese de que el sistema no tiene habilitada la memoria caché de escritura en el controlador de disco.</span><span class="sxs-lookup"><span data-stu-id="7d589-129">Check to make sure that the system does not have write-caching enabled on the disk controller.</span></span> <span data-ttu-id="7d589-130">Si cree que el problema se debe a la caché de escritura, póngase en contacto con su proveedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="7d589-130">If you suspect write-caching to be the problem, contact your hardware vendor.</span></span>  
  
 <span data-ttu-id="7d589-131">Finalmente, puede resultarle útil cambiar a un nuevo sistema de hardware.</span><span class="sxs-lookup"><span data-stu-id="7d589-131">Finally, you might find it useful to switch to a new hardware system.</span></span> <span data-ttu-id="7d589-132">Este cambio puede incluir volver a formatear las unidades de disco y volver a instalar el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7d589-132">This switch may include reformatting the disk drives and reinstalling the operating system.</span></span>  
  
### <a name="restore-from-backup"></a><span data-ttu-id="7d589-133">Restaure mediante la copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="7d589-133">Restore from Backup</span></span>  
 <span data-ttu-id="7d589-134">Si el problema no está relacionado con el hardware y tiene una copia de seguridad limpia disponible, úsela para restaurar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d589-134">If the problem is not hardware-related and a known clean backup is available, restore the database from the backup.</span></span>  
  
 <span data-ttu-id="7d589-135">Pruebe a cambiar las bases de datos para utilizar la opción PAGE_VERIFY CHECKSUM.</span><span class="sxs-lookup"><span data-stu-id="7d589-135">Consider changing the databases to use the PAGE_VERIFY CHECKSUM option.</span></span> <span data-ttu-id="7d589-136">Para obtener más información sobre cómo habilitar PAGE_VERIFY, vea [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7d589-136">For information about PAGE_VERIFY, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d589-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d589-137">See Also</span></span>  
 [<span data-ttu-id="7d589-138">Administrar la tabla suspect_pages &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7d589-138">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
