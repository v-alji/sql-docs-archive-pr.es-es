---
title: MSSQLSERVER_2527 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2527 (Database Engine error)
ms.assetid: 1cef90ef-9c39-44e6-bc7f-316c8f53c10c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 900707634a016ecfd29f9f676e68b4d2f557ccea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87671080"
---
# <a name="mssqlserver_2527"></a><span data-ttu-id="1ff7e-102">MSSQLSERVER_2527</span><span class="sxs-lookup"><span data-stu-id="1ff7e-102">MSSQLSERVER_2527</span></span>
    
## <a name="details"></a><span data-ttu-id="1ff7e-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1ff7e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ff7e-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1ff7e-104">Product Name</span></span>|<span data-ttu-id="1ff7e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ff7e-105">SQL Server</span></span>|  
|<span data-ttu-id="1ff7e-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1ff7e-106">Event ID</span></span>|<span data-ttu-id="1ff7e-107">2527</span><span class="sxs-lookup"><span data-stu-id="1ff7e-107">2527</span></span>|  
|<span data-ttu-id="1ff7e-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1ff7e-108">Event Source</span></span>|<span data-ttu-id="1ff7e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1ff7e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1ff7e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1ff7e-110">Component</span></span>|<span data-ttu-id="1ff7e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1ff7e-111">SQLEngine</span></span>|  
|<span data-ttu-id="1ff7e-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1ff7e-112">Symbolic Name</span></span>|<span data-ttu-id="1ff7e-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span><span class="sxs-lookup"><span data-stu-id="1ff7e-113">DBCC_INDEX_FILEGROUP_IS_OFFLINE</span></span>|  
|<span data-ttu-id="1ff7e-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1ff7e-114">Message Text</span></span>|<span data-ttu-id="1ff7e-115">No se puede procesar el índice I_NAME de la tabla O_NAME porque el grupo de archivos F_NAME se encuentra en modo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="1ff7e-115">Unable to process index I_NAME of table O_NAME because filegroup F_NAME is offline.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ff7e-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="1ff7e-116">Explanation</span></span>  
 <span data-ttu-id="1ff7e-117">Este mensaje informativo indica que no se puede comprobar el índice porque uno de los grupos de archivos que almacena datos para él se encuentra en modo sin conexión.</span><span class="sxs-lookup"><span data-stu-id="1ff7e-117">This informational message indicates that the index cannot be checked because one of the filegroups that stores data for the index is offline.</span></span> <span data-ttu-id="1ff7e-118">El estado de los archivos en un grupo de archivos determina la disponibilidad de todo el grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="1ff7e-118">The state of the files in a filegroup determines the availability of the whole filegroup.</span></span> <span data-ttu-id="1ff7e-119">Para que un grupo de archivos esté disponible, todos los archivos del grupo de archivos deben estar en línea.</span><span class="sxs-lookup"><span data-stu-id="1ff7e-119">For a filegroup to be available, all files within the filegroup must be online.</span></span> <span data-ttu-id="1ff7e-120">Si no hay ningún otro problema, todos los demás índices del mismo objeto se comprobarán.</span><span class="sxs-lookup"><span data-stu-id="1ff7e-120">If there are no other problems, all other indexes of the same object will be checked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ff7e-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1ff7e-121">User Action</span></span>  
 <span data-ttu-id="1ff7e-122">Para ver el estado de los archivos correspondientes al grupo de archivos especificado, consulte la vista de catálogo **sys.database_files** o **sys.master_files**.</span><span class="sxs-lookup"><span data-stu-id="1ff7e-122">To view the state of the files for the specified filegroup, query either the **sys.database_files** or **sys.master_files** catalog view.</span></span>  
  
 <span data-ttu-id="1ff7e-123">Restaure el archivo sin conexión a partir de una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1ff7e-123">Restore the offline file from a backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff7e-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ff7e-124">See Also</span></span>  
 <span data-ttu-id="1ff7e-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ff7e-125">[sys.database_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-files-transact-sql) </span></span>  
 <span data-ttu-id="1ff7e-126">[Sys. master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ff7e-126">[sys.master_files &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-master-files-transact-sql) </span></span>  
 [<span data-ttu-id="1ff7e-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1ff7e-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
