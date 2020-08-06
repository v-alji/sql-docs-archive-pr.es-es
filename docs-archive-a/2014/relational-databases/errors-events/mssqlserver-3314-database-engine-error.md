---
title: MSSQLSERVER_3314 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3314 (Database Engine error)
ms.assetid: f3a5ca6a-b502-4cab-b3b1-4bc753763fa9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff3b891b438f71d70f5dd62174eae2c5a07d29a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675901"
---
# <a name="mssqlserver_3314"></a><span data-ttu-id="1265d-102">MSSQLSERVER_3314</span><span class="sxs-lookup"><span data-stu-id="1265d-102">MSSQLSERVER_3314</span></span>
    
## <a name="details"></a><span data-ttu-id="1265d-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="1265d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1265d-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="1265d-104">Product Name</span></span>|<span data-ttu-id="1265d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1265d-105">SQL Server</span></span>|  
|<span data-ttu-id="1265d-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="1265d-106">Event ID</span></span>|<span data-ttu-id="1265d-107">3314</span><span class="sxs-lookup"><span data-stu-id="1265d-107">3314</span></span>|  
|<span data-ttu-id="1265d-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="1265d-108">Event Source</span></span>|<span data-ttu-id="1265d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1265d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1265d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1265d-110">Component</span></span>|<span data-ttu-id="1265d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1265d-111">SQLEngine</span></span>|  
|<span data-ttu-id="1265d-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="1265d-112">Symbolic Name</span></span>|<span data-ttu-id="1265d-113">ERR_LOG_RID2</span><span class="sxs-lookup"><span data-stu-id="1265d-113">ERR_LOG_RID2</span></span>|  
|<span data-ttu-id="1265d-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="1265d-114">Message Text</span></span>|<span data-ttu-id="1265d-115">Durante la puesta al día de una operación registrada en la base de datos '%.\*ls', se produjo un error en la entrada de registro con id. %S_LSN.</span><span class="sxs-lookup"><span data-stu-id="1265d-115">During undoing of a logged operation in database '%.\*ls', an error occurred at log record ID %S_LSN.</span></span> <span data-ttu-id="1265d-116">Normalmente, el error específico se registra antes como un error en el servicio Registro de eventos de Windows.</span><span class="sxs-lookup"><span data-stu-id="1265d-116">Typically, the specific failure is logged previously as an error in the Windows Event Log service.</span></span> <span data-ttu-id="1265d-117">Restaure la base de datos o el archivo a partir de una copia de seguridad completa o repare la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1265d-117">Restore the database or file from a backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1265d-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="1265d-118">Explanation</span></span>  
 <span data-ttu-id="1265d-119">Este es un error de acumulación de la recuperación de una operación de deshacer.</span><span class="sxs-lookup"><span data-stu-id="1265d-119">This is a rollup error for undo recovery.</span></span> <span data-ttu-id="1265d-120">Este error ha colocado la base de datos en el estado SUSPECT.</span><span class="sxs-lookup"><span data-stu-id="1265d-120">This error has placed the database into the SUSPECT state.</span></span> <span data-ttu-id="1265d-121">El grupo de archivos principal, y posiblemente otros grupos de archivos, es sospechoso y puede estar dañado.</span><span class="sxs-lookup"><span data-stu-id="1265d-121">The primary filegroup, and possibly other filegroups, are suspect and may be damaged.</span></span> <span data-ttu-id="1265d-122">La base de datos no se puede recuperar durante el inicio de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y, por consiguiente, no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1265d-122">The database cannot be recovered during startup of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is therefore unavailable.</span></span> <span data-ttu-id="1265d-123">Se requiere una acción por parte del usuario para resolver el problema.</span><span class="sxs-lookup"><span data-stu-id="1265d-123">User action is required to resolve the problem.</span></span>  
  
 <span data-ttu-id="1265d-124">Tenga en cuenta que si este error se produce para **tempdb**, la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se cierra.</span><span class="sxs-lookup"><span data-stu-id="1265d-124">Note that if this error occurs for **tempdb**, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance shuts down.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1265d-125">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="1265d-125">User Action</span></span>  
 <span data-ttu-id="1265d-126">Una condición transitoria que se dio en el sistema durante un intento determinado de iniciar la instancia del servidor o recuperar una base de datos puede producir este error.</span><span class="sxs-lookup"><span data-stu-id="1265d-126">This error can be caused by a transient condition that existed on the system during a given attempt to start up the server instance or to recover a database.</span></span> <span data-ttu-id="1265d-127">También puede deberse a un error permanente que se produce cada vez que se intenta iniciar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1265d-127">This error can also be caused by a permanent failure that occurs every time that you attempt to start the database.</span></span> <span data-ttu-id="1265d-128">Para obtener información acerca de la causa, examine el registro de eventos de Windows para ver si contiene un error anterior que indique el error concreto.</span><span class="sxs-lookup"><span data-stu-id="1265d-128">For information about the cause, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span>  
  
 <span data-ttu-id="1265d-129">Para obtener información sobre la causa de esta repetición del error 3314, busque en el registro de eventos de Windows un error anterior que indique el error específico.</span><span class="sxs-lookup"><span data-stu-id="1265d-129">For information about the cause of this occurrence of error 3314, examine the Windows Event Log for a previous error that indicates the specific failure.</span></span> <span data-ttu-id="1265d-130">La acción del usuario adecuada depende de si la información del registro de eventos de Windows indica que el error de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lo causó una condición transitoria o un error permanente.</span><span class="sxs-lookup"><span data-stu-id="1265d-130">The appropriate user action depends on whether the information in the Windows Event Log indicates that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error was caused by a transient condition or a permanent failure.</span></span> <span data-ttu-id="1265d-131">Para obtener información sobre las acciones del usuario para solucionar el error 3314, vea los Libros en pantalla de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1265d-131">For information about the user actions for troubleshooting error 3314, see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1265d-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1265d-132">See Also</span></span>  
 <span data-ttu-id="1265d-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1265d-133">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="1265d-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1265d-134">[DBCC CHECKDB &#40;Transact-SQL&#41;](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) </span></span>  
 <span data-ttu-id="1265d-135">[Restauraciones de base de datos completas &#40;modelo de recuperación simple&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="1265d-135">[Complete Database Restores &#40;Simple Recovery Model&#41;](../backup-restore/complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="1265d-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span><span class="sxs-lookup"><span data-stu-id="1265d-136">[MSSQLSERVER_824](mssqlserver-824-database-engine-error.md) </span></span>  
 [<span data-ttu-id="1265d-137">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1265d-137">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
