---
title: MSSQLSERVER_1457 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1457 (Database Engine error)
ms.assetid: 28434ba1-b033-4866-ab41-111fccef45a2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c30ee6149c95d93bdaf1d2877f5fe1871a575ec1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675952"
---
# <a name="mssqlserver_1457"></a><span data-ttu-id="992ca-102">MSSQLSERVER_1457</span><span class="sxs-lookup"><span data-stu-id="992ca-102">MSSQLSERVER_1457</span></span>
    
## <a name="details"></a><span data-ttu-id="992ca-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="992ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="992ca-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="992ca-104">Product Name</span></span>|<span data-ttu-id="992ca-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="992ca-105">SQL Server</span></span>|  
|<span data-ttu-id="992ca-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="992ca-106">Event ID</span></span>|<span data-ttu-id="992ca-107">1457</span><span class="sxs-lookup"><span data-stu-id="992ca-107">1457</span></span>|  
|<span data-ttu-id="992ca-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="992ca-108">Event Source</span></span>|<span data-ttu-id="992ca-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="992ca-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="992ca-110">Componente</span><span class="sxs-lookup"><span data-stu-id="992ca-110">Component</span></span>|<span data-ttu-id="992ca-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="992ca-111">SQLEngine</span></span>|  
|<span data-ttu-id="992ca-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="992ca-112">Symbolic Name</span></span>|<span data-ttu-id="992ca-113">DBM_PAGE_UNDO_PENDING</span><span class="sxs-lookup"><span data-stu-id="992ca-113">DBM_PAGE_UNDO_PENDING</span></span>|  
|<span data-ttu-id="992ca-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="992ca-114">Message Text</span></span>|<span data-ttu-id="992ca-115">Se interrumpió la sincronización de la base de datos reflejada, '%.\*ls' y ésta quedó en un estado incoherente.</span><span class="sxs-lookup"><span data-stu-id="992ca-115">Synchronization of the mirror database, '%.\*ls', was interrupted, leaving the database in an inconsistent state.</span></span> <span data-ttu-id="992ca-116">Error del comando ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="992ca-116">The ALTER DATABASE command failed.</span></span> <span data-ttu-id="992ca-117">Asegúrese de que hay una copia de seguridad la base de datos reflejada y de que la base de datos está en línea, y vuelva a conectar la instancia del servidor reflejado y permita que la base de datos reflejada finalice la sincronización.</span><span class="sxs-lookup"><span data-stu-id="992ca-117">Ensure that the mirror database is back up and online, and then reconnect the mirror server instance and allow the mirror database to finish synchronizing.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="992ca-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="992ca-118">Explanation</span></span>  
 <span data-ttu-id="992ca-119">Este mensaje indica un error en la instrucción ALTER DATABASE *nombreDeBaseDeDatos* SET PARTNER OFF.</span><span class="sxs-lookup"><span data-stu-id="992ca-119">This messages indicates that the ALTER DATABASE *database_name* SET PARTNER OFF statement has failed.</span></span> <span data-ttu-id="992ca-120">El error al intentar quitar el reflejo de la base de datos ha interrumpido la sincronización de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="992ca-120">The failed attempt to remove database mirroring interrupted synchronization of the mirror database.</span></span> <span data-ttu-id="992ca-121">La base de datos se encuentra en un estado incoherente.</span><span class="sxs-lookup"><span data-stu-id="992ca-121">The database is in an inconsistent state.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="992ca-122">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="992ca-122">User Action</span></span>  
 <span data-ttu-id="992ca-123">Para solucionar este error, puede realizar una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="992ca-123">To resolve this error, you can take either of the following actions:</span></span>  
  
-   <span data-ttu-id="992ca-124">Restaure el contacto entre el servidor reflejado y el principal para permitir la sincronización de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="992ca-124">Restore contact between the mirror server and the principal server to allow for the mirror database to synchronize.</span></span>  
  
-   <span data-ttu-id="992ca-125">Quite la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="992ca-125">Drop the mirror database.</span></span>  
  
     <span data-ttu-id="992ca-126">Después de quitar la base de datos reflejada, puede crear una nueva base de datos reflejada a partir de las copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="992ca-126">After you drop the mirror database, you can create a new mirror database from backups.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="992ca-127">Puede quitar la base de datos reflejada cuando está todavía habilitada la creación de reflejo solo después de un error de instrucción SET PARTNER OFF.</span><span class="sxs-lookup"><span data-stu-id="992ca-127">You can drop the mirror database when mirroring is still enabled only after a failed SET PARTNER OFF statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="992ca-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="992ca-128">See Also</span></span>  
 <span data-ttu-id="992ca-129">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="992ca-129">[Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="992ca-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="992ca-130">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="992ca-131">[Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="992ca-131">[Setting Up Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/setting-up-database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="992ca-132">[Quitar la creación de reflejo de la base de datos &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="992ca-132">[Removing Database Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/removing-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="992ca-133">Preparar una base de datos reflejada para la creación de reflejo &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="992ca-133">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
  
