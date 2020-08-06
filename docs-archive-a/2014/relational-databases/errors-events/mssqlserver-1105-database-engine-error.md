---
title: MSSQLSERVER_1105 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dea326fab7edd6a5c155c8f0182bffc044505eb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663007"
---
# <a name="mssqlserver_1105"></a><span data-ttu-id="813e4-102">MSSQLSERVER_1105</span><span class="sxs-lookup"><span data-stu-id="813e4-102">MSSQLSERVER_1105</span></span>
    
## <a name="details"></a><span data-ttu-id="813e4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="813e4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="813e4-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="813e4-104">Product Name</span></span>|<span data-ttu-id="813e4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="813e4-105">SQL Server</span></span>|  
|<span data-ttu-id="813e4-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="813e4-106">Event ID</span></span>|<span data-ttu-id="813e4-107">1105</span><span class="sxs-lookup"><span data-stu-id="813e4-107">1105</span></span>|  
|<span data-ttu-id="813e4-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="813e4-108">Event Source</span></span>|<span data-ttu-id="813e4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="813e4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="813e4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="813e4-110">Component</span></span>|<span data-ttu-id="813e4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="813e4-111">SQLEngine</span></span>|  
|<span data-ttu-id="813e4-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="813e4-112">Symbolic Name</span></span>|<span data-ttu-id="813e4-113">NO_MORE_SPACE_IN_FG</span><span class="sxs-lookup"><span data-stu-id="813e4-113">NO_MORE_SPACE_IN_FG</span></span>|  
|<span data-ttu-id="813e4-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="813e4-114">Message Text</span></span>|<span data-ttu-id="813e4-115">No se pudo asignar espacio para el objeto '%.\*ls'%.\*ls de la base de datos '%.\*ls' porque el grupo de archivos '%.\*ls' está lleno.</span><span class="sxs-lookup"><span data-stu-id="813e4-115">Could not allocate space for object '%.\*ls'%.\*ls in database '%.\*ls' because the '%.\*ls' filegroup is full.</span></span> <span data-ttu-id="813e4-116">Elimine archivos innecesarios, quite objetos del grupo de archivos, agregue archivos adicionales al grupo de archivos o establezca la opción de crecimiento automático para los archivos existentes en el grupo de archivos con el fin de crear espacio en el disco.</span><span class="sxs-lookup"><span data-stu-id="813e4-116">Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="813e4-117">Explicación</span><span class="sxs-lookup"><span data-stu-id="813e4-117">Explanation</span></span>  
 <span data-ttu-id="813e4-118">No hay espacio en disco disponible en un grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="813e4-118">No disk space is available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="813e4-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="813e4-119">User Action</span></span>  
 <span data-ttu-id="813e4-120">Las siguientes acciones pueden crear espacio disponible en el grupo de archivos:</span><span class="sxs-lookup"><span data-stu-id="813e4-120">The following actions may make space available in the filegroup:</span></span>  
  
-   <span data-ttu-id="813e4-121">Active el crecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="813e4-121">Turn on autogrow.</span></span>  
  
-   <span data-ttu-id="813e4-122">Agregue más archivos al grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="813e4-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="813e4-123">Libere espacio en disco quitando índices o tablas que ya no sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="813e4-123">Free disk space by dropping index or tables that are no longer needed.</span></span>  
  
-   <span data-ttu-id="813e4-124">Para obtener más información, vea el tema "Solucionar problemas de espacio en disco insuficiente para datos" en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="813e4-124">For more information, see "Troubleshooting Insufficient Data Disk Space" in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="813e4-125">Cuando un índice se encuentra en varios archivos, `ALTER INDEX REORGANIZE` puede devolver el error 1105 si uno de los archivos está lleno.</span><span class="sxs-lookup"><span data-stu-id="813e4-125">When an index is located on several files, `ALTER INDEX REORGANIZE` can return error 1105 when one of the files is full.</span></span> <span data-ttu-id="813e4-126">El proceso de reorganización se bloquea cuando el proceso trata de mover filas al archivo que está lleno.</span><span class="sxs-lookup"><span data-stu-id="813e4-126">The reorganization process is blocked when the process tries to move rows to the full file.</span></span> <span data-ttu-id="813e4-127">Para solucionar esta limitación, realice una operación `ALTER INDEX REBUILD` en lugar de `ALTER INDEX REORGANIZE`, o incremente el límite de crecimiento de los archivos que estén llenos.</span><span class="sxs-lookup"><span data-stu-id="813e4-127">To work around this limitation perform an `ALTER INDEX REBUILD` instead of `ALTER INDEX REORGANIZE` or increase the file growth limit of any files that are full.</span></span>  
  
  
