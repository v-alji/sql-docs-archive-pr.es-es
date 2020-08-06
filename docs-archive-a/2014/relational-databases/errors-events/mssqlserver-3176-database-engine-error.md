---
title: MSSQLSERVER_3176 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3176 (Database Engine error)
ms.assetid: 4be24c64-2d52-4cb4-b4d7-36efbe4555b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 64e1a836995fe8738bb5c2ff0cb4de10d84d1f29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673015"
---
# <a name="mssqlserver_3176"></a><span data-ttu-id="84445-102">MSSQLSERVER_3176</span><span class="sxs-lookup"><span data-stu-id="84445-102">MSSQLSERVER_3176</span></span>
    
## <a name="details"></a><span data-ttu-id="84445-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="84445-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84445-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="84445-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="84445-105">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="84445-105">Event ID</span></span>|<span data-ttu-id="84445-106">3176</span><span class="sxs-lookup"><span data-stu-id="84445-106">3176</span></span>|  
|<span data-ttu-id="84445-107">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="84445-107">Event Source</span></span>|<span data-ttu-id="84445-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="84445-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="84445-109">Componente</span><span class="sxs-lookup"><span data-stu-id="84445-109">Component</span></span>|<span data-ttu-id="84445-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="84445-110">SQLEngine</span></span>|  
|<span data-ttu-id="84445-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="84445-111">Symbolic Name</span></span>|<span data-ttu-id="84445-112">LDDB_FILE_CLAIM</span><span class="sxs-lookup"><span data-stu-id="84445-112">LDDB_FILE_CLAIM</span></span>|  
|<span data-ttu-id="84445-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="84445-113">Message Text</span></span>|<span data-ttu-id="84445-114">El archivo '%ls' fue reclamado por '%ls'(%d) y '%ls'(%d).</span><span class="sxs-lookup"><span data-stu-id="84445-114">File '%ls' is claimed by '%ls'(%d) and '%ls'(%d).</span></span> <span data-ttu-id="84445-115">Se puede utilizar la cláusula WITH MOVE para cambiar la ubicación de uno o más archivos.</span><span class="sxs-lookup"><span data-stu-id="84445-115">The WITH MOVE clause can be used to relocate one or more files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="84445-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="84445-116">Explanation</span></span>  
 <span data-ttu-id="84445-117">Se ha intentado utilizar un archivo para más de un propósito.</span><span class="sxs-lookup"><span data-stu-id="84445-117">Attempting to use a file for more than one purpose.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="84445-118">Causas posibles</span><span class="sxs-lookup"><span data-stu-id="84445-118">Possible Causes</span></span>  
 <span data-ttu-id="84445-119">Otra base de datos ya está utilizando el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="84445-119">Another database is already using the file name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="84445-120">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="84445-120">User Action</span></span>  
 <span data-ttu-id="84445-121">Restaure los archivos de la base de datos en otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="84445-121">Restore the database files to a different location.</span></span> <span data-ttu-id="84445-122">En una instrucción RESTORE, utilice una cláusula WITH MOVE para mover cada archivo.</span><span class="sxs-lookup"><span data-stu-id="84445-122">In a RESTORE statement, use a WITH MOVE clause to move each file.</span></span> <span data-ttu-id="84445-123">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cambie las ubicaciones de los archivos en la cuadrícula **Restaurar los archivos de base de datos como** del cuadro de diálogo **Opciones de Restaurar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="84445-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], change the file locations in the **Restore the database files as** grid of the **Restore Database Options** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84445-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="84445-124">See Also</span></span>  
 <span data-ttu-id="84445-125">[Restaurar una base de datos a una nueva ubicación &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84445-125">[Restore a Database to a New Location &#40;SQL Server&#41;](../backup-restore/restore-a-database-to-a-new-location-sql-server.md) </span></span>  
 <span data-ttu-id="84445-126">[Restaurar archivos en una nueva ubicación &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="84445-126">[Restore Files to a New Location &#40;SQL Server&#41;](../backup-restore/restore-files-to-a-new-location-sql-server.md) </span></span>  
 [<span data-ttu-id="84445-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="84445-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
