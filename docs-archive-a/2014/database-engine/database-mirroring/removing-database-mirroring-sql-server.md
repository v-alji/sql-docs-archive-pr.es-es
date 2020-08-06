---
title: Quitar la creación de reflejo de la base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- stopping database mirroring [SQL Server]
- removing database mirroring [SQL Server]
ms.assetid: 40c72091-8f03-4037-8b55-5e95309fe145
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8044fcef9d9f9bfc1fb41c1faa17b76c827da5a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746493"
---
# <a name="removing-database-mirroring-sql-server"></a><span data-ttu-id="3e908-102">Quitar la creación de reflejo de la base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3e908-102">Removing Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="3e908-103">El propietario de una base de datos puede detener manualmente una sesión de creación de reflejo de la base de datos en cualquier momento y en cualquier asociado.</span><span class="sxs-lookup"><span data-stu-id="3e908-103">The database owner can manually stop a database mirroring session at any time, at either partner.</span></span>  
  
## <a name="impact-of-removing-mirroring"></a><span data-ttu-id="3e908-104">Impacto de quitar la creación de reflejo</span><span class="sxs-lookup"><span data-stu-id="3e908-104">Impact of Removing Mirroring</span></span>  
 <span data-ttu-id="3e908-105">Cuando se quita la creación del reflejo, sucede lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3e908-105">When mirroring is removed, the following occurs:</span></span>  
  
-   <span data-ttu-id="3e908-106">La relación entre los asociados y entre cada asociado y el testigo se interrumpe permanentemente, de existir alguna.</span><span class="sxs-lookup"><span data-stu-id="3e908-106">The relationship between the partners and between each partner and the witness breaks permanently, if any relationship exists.</span></span>  
  
     <span data-ttu-id="3e908-107">Si los asociados se estaban comunicando entre sí al detenerse la sesión, su relación se interrumpe inmediatamente en los dos equipos.</span><span class="sxs-lookup"><span data-stu-id="3e908-107">If the partners are communicating with each other when the session is stopped, their relationship is immediately broken on both computers.</span></span> <span data-ttu-id="3e908-108">Si los asociados no se estaban comunicando (la base de datos tiene estado DISCONNECTED en el momento de la detención de la sesión), la relación se interrumpe inmediatamente en el asociado en el que se detiene la creación de reflejo; cuando el otro asociado intente volver a conectarse, descubrirá que la sesión de creación de reflejo de la base de datos ha terminado.</span><span class="sxs-lookup"><span data-stu-id="3e908-108">If the partners are not communicating (the database is in a DISCONNECTED state at the time of stopping), the relationship is broken immediately on the partner from which mirroring is stopped; when the other partner tries to reconnect, it discovers that the database mirroring session has ended.</span></span>  
  
-   <span data-ttu-id="3e908-109">Se elimina la información sobre la sesión de creación de reflejo, a diferencia de lo que ocurre cuando se pausa una sesión.</span><span class="sxs-lookup"><span data-stu-id="3e908-109">Information about the mirroring session is dropped, unlike when pausing a session.</span></span> <span data-ttu-id="3e908-110">La creación de reflejo se elimina de la base de datos principal y de la base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="3e908-110">Mirroring is removed on both the principal database and the mirror database.</span></span> <span data-ttu-id="3e908-111">En **sys.databases**, la columna **mirroring_state** y todas las otras columnas de reflejos se establecen en NULL.</span><span class="sxs-lookup"><span data-stu-id="3e908-111">In **sys.databases**, the **mirroring_state** column and all other mirroring columns are set to NULL.</span></span> <span data-ttu-id="3e908-112">Para obtener más información, vea [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3e908-112">For more information, see [sys.database_mirroring &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-transact-sql).</span></span>  
  
-   <span data-ttu-id="3e908-113">Cada instancia de servidor asociado se queda con una copia independiente de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3e908-113">Each partner server instance is left with a separate copy of the database.</span></span>  
  
-   <span data-ttu-id="3e908-114">La base de datos reflejada se queda con el estado RESTORING (vea la columna **state** de **sys.databases**), porque la base de datos reflejada se creó mediante RESTORE WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="3e908-114">The mirror database is left in the RESTORING state (see the **state** column of **sys.databases**), because the mirror database was created by using RESTORE WITH NORECOVERY.</span></span> <span data-ttu-id="3e908-115">En este punto, puede quitar la primera base de datos reflejada o restaurarla mediante WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="3e908-115">At this point, you can drop the former mirror database or restore it using WITH RECOVERY.</span></span> <span data-ttu-id="3e908-116">Al recuperar la base de datos, ésta será diferente de la primera base de datos principal porque la recuperación se inicia con una nueva bifurcación de recuperación.</span><span class="sxs-lookup"><span data-stu-id="3e908-116">When you recover the database, it will have diverged from the former principal database because the recovery starts a new recovery fork.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3e908-117">Para continuar la creación de reflejo después de detener una sesión, debe establecerse una nueva sesión de creación de reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3e908-117">To continue mirroring after stopping a session, you must establish a new database mirroring session.</span></span> <span data-ttu-id="3e908-118">Si crea una copia de seguridad de registros después de detener la creación de reflejo, debe aplicarla a la base de datos reflejada antes de reiniciar la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="3e908-118">If you create a log backup after stopping mirroring, you must apply it to the mirror database before restarting mirroring.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3e908-119">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3e908-119">Related Tasks</span></span>  
 <span data-ttu-id="3e908-120">**Para quitar la creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="3e908-120">**To remove database mirroring**</span></span>  
  
-   [<span data-ttu-id="3e908-121">Quitar la creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3e908-121">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
 <span data-ttu-id="3e908-122">**Para iniciar la creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="3e908-122">**To start database mirroring**</span></span>  
  
-   [<span data-ttu-id="3e908-123">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3e908-123">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="3e908-124">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e908-124">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="3e908-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e908-125">See Also</span></span>  
 <span data-ttu-id="3e908-126">[Reflejo de la base de datos ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span><span class="sxs-lookup"><span data-stu-id="3e908-126">[ALTER DATABASE Database Mirroring &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-database-mirroring) </span></span>  
 <span data-ttu-id="3e908-127">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e908-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="3e908-128">[Pausar y reanudar la creación de reflejo de la base de datos &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3e908-128">[Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](pausing-and-resuming-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="3e908-129">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3e908-129">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
