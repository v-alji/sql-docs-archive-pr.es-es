---
title: MSSQLSERVER_3456 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3456 (Database Engine error)
ms.assetid: d11b2b2c-3ae4-4023-b82f-05b561bfacce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f13316bdd3147bb0ad63c8d4a2fb18f1fce74006
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746310"
---
# <a name="mssqlserver_3456"></a><span data-ttu-id="9fd2d-102">MSSQLSERVER_3456</span><span class="sxs-lookup"><span data-stu-id="9fd2d-102">MSSQLSERVER_3456</span></span>
    
## <a name="details"></a><span data-ttu-id="9fd2d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="9fd2d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9fd2d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="9fd2d-104">Product Name</span></span>|<span data-ttu-id="9fd2d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9fd2d-105">SQL Server</span></span>|  
|<span data-ttu-id="9fd2d-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="9fd2d-106">Event ID</span></span>|<span data-ttu-id="9fd2d-107">3456</span><span class="sxs-lookup"><span data-stu-id="9fd2d-107">3456</span></span>|  
|<span data-ttu-id="9fd2d-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="9fd2d-108">Event Source</span></span>|<span data-ttu-id="9fd2d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9fd2d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9fd2d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9fd2d-110">Component</span></span>|<span data-ttu-id="9fd2d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9fd2d-111">SQLEngine</span></span>|  
|<span data-ttu-id="9fd2d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="9fd2d-112">Symbolic Name</span></span>|<span data-ttu-id="9fd2d-113">REC_REDOLSNMISMATCH</span><span class="sxs-lookup"><span data-stu-id="9fd2d-113">REC_REDOLSNMISMATCH</span></span>|  
|<span data-ttu-id="9fd2d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="9fd2d-114">Message Text</span></span>|<span data-ttu-id="9fd2d-115">No se pudo rehacer la entrada de registro %S_LSN para el identificador de transacción %S_XID de la página %S_PGID, base de datos '%.\*ls' (identificador de base de datos %d).</span><span class="sxs-lookup"><span data-stu-id="9fd2d-115">Could not redo log record %S_LSN, for transaction ID %S_XID, on page %S_PGID, database '%.\*ls' (database ID %d).</span></span> <span data-ttu-id="9fd2d-116">Página: LSN = %S_LSN, tipo = %ld.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-116">Page: LSN = %S_LSN, type = %ld.</span></span> <span data-ttu-id="9fd2d-117">Log: OpCode = %ld, contexto %ld, PrevPageLSN: %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-117">Log: OpCode = %ld, context %ld, PrevPageLSN: %S_LSN.</span></span> <span data-ttu-id="9fd2d-118">Restaure la base de datos desde una copia de seguridad o repárela.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-118">Restore from a backup of the database, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9fd2d-119">Explicación</span><span class="sxs-lookup"><span data-stu-id="9fd2d-119">Explanation</span></span>  
 <span data-ttu-id="9fd2d-120">La operación de restauración no pudo rehacer el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-120">The restore operation was unable to redo the transaction log.</span></span> <span data-ttu-id="9fd2d-121">Este error ha colocado la base de datos en el estado SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-121">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="9fd2d-122">El grupo de archivos principal, y posiblemente otros grupos de archivos, es sospechoso y puede estar dañado.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-122">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="9fd2d-123">La base de datos no se puede recuperar durante el inicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, por consiguiente, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-123">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="9fd2d-124">Se requiere una acción por parte del usuario para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-124">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="9fd2d-125">Tenga en cuenta que si este error se produce para **tempdb**, la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se cierra.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-125">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9fd2d-126">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="9fd2d-126">User Action</span></span>  
 <span data-ttu-id="9fd2d-127">Una condición transitoria que se dio en el sistema durante un intento determinado de iniciar la instancia del servidor o recuperar una base de datos puede producir este error.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-127">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="9fd2d-128">También puede deberse a un error permanente que se produce cada vez que se intenta iniciar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-128">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="9fd2d-129">Para obtener información acerca de la causa, examine el registro de eventos de Windows para ver si contiene un error anterior que indique el error concreto.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-129">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="9fd2d-130">Para obtener información sobre la causa de esta repetición del error 3456, busque en el registro de eventos de Windows un error anterior que indique el error específico.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-130">For information about the cause of this occurrence of error 3456, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="9fd2d-131">La acción del usuario adecuada depende de si la información del registro de eventos de Windows indica que el error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lo causó una condición transitoria o un error permanente.</span><span class="sxs-lookup"><span data-stu-id="9fd2d-131">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="9fd2d-132">Para obtener información sobre las acciones del usuario para solucionar el error 3456, consulte los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9fd2d-132">For information about the user actions for troubleshooting error 3456, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd2d-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9fd2d-133">See Also</span></span>  
 <span data-ttu-id="9fd2d-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9fd2d-134">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="9fd2d-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9fd2d-135">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="9fd2d-136">[Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="9fd2d-136">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="9fd2d-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="9fd2d-137">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="9fd2d-138">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9fd2d-138">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
