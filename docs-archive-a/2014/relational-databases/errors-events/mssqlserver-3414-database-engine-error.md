---
title: MSSQLSERVER_3414 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3414 (Database Engine error)
ms.assetid: f25852f9-b91c-4356-b817-78bec9ec8db4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: aecaf2a920552b8ea66804600fa8bd4168175e53
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675894"
---
# <a name="mssqlserver_3414"></a><span data-ttu-id="fd5fb-102">MSSQLSERVER_3414</span><span class="sxs-lookup"><span data-stu-id="fd5fb-102">MSSQLSERVER_3414</span></span>
    
## <a name="details"></a><span data-ttu-id="fd5fb-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="fd5fb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd5fb-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="fd5fb-104">Product Name</span></span>|<span data-ttu-id="fd5fb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd5fb-105">SQL Server</span></span>|  
|<span data-ttu-id="fd5fb-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="fd5fb-106">Event ID</span></span>|<span data-ttu-id="fd5fb-107">3414</span><span class="sxs-lookup"><span data-stu-id="fd5fb-107">3414</span></span>|  
|<span data-ttu-id="fd5fb-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="fd5fb-108">Event Source</span></span>|<span data-ttu-id="fd5fb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="fd5fb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="fd5fb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="fd5fb-110">Component</span></span>|<span data-ttu-id="fd5fb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="fd5fb-111">SQLEngine</span></span>|  
|<span data-ttu-id="fd5fb-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="fd5fb-112">Symbolic Name</span></span>|<span data-ttu-id="fd5fb-113">REC_GIVEUP</span><span class="sxs-lookup"><span data-stu-id="fd5fb-113">REC_GIVEUP</span></span>|  
|<span data-ttu-id="fd5fb-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="fd5fb-114">Message Text</span></span>|<span data-ttu-id="fd5fb-115">Se ha producido un error durante la recuperación que impide reiniciar la base de datos '%.\*ls' (id. de base de datos %d).</span><span class="sxs-lookup"><span data-stu-id="fd5fb-115">An error occurred during recovery, preventing the database '%.\*ls' (database ID %d) from restarting.</span></span> <span data-ttu-id="fd5fb-116">Diagnostique los errores de recuperación y corríjalos, o restaure desde una copia de seguridad en buen estado.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-116">Diagnose the recovery errors and fix them, or restore from a known good backup.</span></span> <span data-ttu-id="fd5fb-117">Si los errores no se han corregido o se espera que haya errores, póngase en contacto con el soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-117">If errors are not corrected or expected, contact Technical Support.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fd5fb-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="fd5fb-118">Explanation</span></span>  
 <span data-ttu-id="fd5fb-119">Se recuperó la base de datos especificada, pero no se inició porque se produjeron errores durante la recuperación.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-119">The specified database was recovered, but failed to start, because errors occurred during recovery.</span></span> <span data-ttu-id="fd5fb-120">Este error ha colocado la base de datos en el estado SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="fd5fb-121">El grupo de archivos principal, y posiblemente otros grupos de archivos, es sospechoso y puede estar dañado.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="fd5fb-122">La base de datos no se puede recuperar durante el inicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, por consiguiente, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="fd5fb-123">Se requiere una acción por parte del usuario para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="fd5fb-124">Tenga en cuenta que si este error se produce para **tempdb**, la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se cierra.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fd5fb-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="fd5fb-125">User Action</span></span>  
 <span data-ttu-id="fd5fb-126">Una condición transitoria que se dio en el sistema durante un intento determinado de iniciar la instancia del servidor o recuperar una base de datos puede producir este error.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="fd5fb-127">También puede deberse a un error permanente que se produce cada vez que se intenta iniciar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="fd5fb-128">Para obtener información acerca de la causa, examine el registro de eventos de Windows para ver si contiene un error anterior que indique el error concreto.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="fd5fb-129">Para obtener información sobre la causa de esta repetición del error 3414, busque en el registro de eventos de Windows un error anterior que indique el error específico.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-129">For information about the cause of this occurrence of error 3414, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="fd5fb-130">La acción del usuario adecuada depende de si la información del registro de eventos de Windows indica que el error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lo causó una condición transitoria o un error permanente.</span><span class="sxs-lookup"><span data-stu-id="fd5fb-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="fd5fb-131">Para obtener información sobre las acciones del usuario para solucionar el error 3414, consulte los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd5fb-131">For information about the user actions for troubleshooting error 3414, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd5fb-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd5fb-132">See Also</span></span>  
 <span data-ttu-id="fd5fb-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd5fb-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="fd5fb-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fd5fb-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="fd5fb-135">[Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="fd5fb-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="fd5fb-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="fd5fb-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="fd5fb-137">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="fd5fb-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
