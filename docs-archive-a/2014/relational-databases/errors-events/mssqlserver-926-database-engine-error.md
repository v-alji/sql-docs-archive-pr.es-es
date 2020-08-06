---
title: MSSQLSERVER_926 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 926 (Database Engine error)
ms.assetid: 57e01668-883b-4be4-84a8-a111caaf0486
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae6796c9f4869d45223ab1283a68fc2bfe78aa11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672035"
---
# <a name="mssqlserver_926"></a><span data-ttu-id="069ca-102">MSSQLSERVER_926</span><span class="sxs-lookup"><span data-stu-id="069ca-102">MSSQLSERVER_926</span></span>
    
## <a name="details"></a><span data-ttu-id="069ca-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="069ca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="069ca-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="069ca-104">Product Name</span></span>|<span data-ttu-id="069ca-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="069ca-105">SQL Server</span></span>|  
|<span data-ttu-id="069ca-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="069ca-106">Event ID</span></span>|<span data-ttu-id="069ca-107">926</span><span class="sxs-lookup"><span data-stu-id="069ca-107">926</span></span>|  
|<span data-ttu-id="069ca-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="069ca-108">Event Source</span></span>|<span data-ttu-id="069ca-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="069ca-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="069ca-110">Componente</span><span class="sxs-lookup"><span data-stu-id="069ca-110">Component</span></span>|<span data-ttu-id="069ca-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="069ca-111">SQLEngine</span></span>|  
|<span data-ttu-id="069ca-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="069ca-112">Symbolic Name</span></span>|<span data-ttu-id="069ca-113">DB_SUSPECT</span><span class="sxs-lookup"><span data-stu-id="069ca-113">DB_SUSPECT</span></span>|  
|<span data-ttu-id="069ca-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="069ca-114">Message Text</span></span>|<span data-ttu-id="069ca-115">No se puede abrir la base de datos '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="069ca-115">Database '%.\*ls' cannot be opened.</span></span> <span data-ttu-id="069ca-116">Tiene la marca SUSPECT para recuperación.</span><span class="sxs-lookup"><span data-stu-id="069ca-116">It has been marked SUSPECT by recovery.</span></span> <span data-ttu-id="069ca-117">Para obtener más información, vea el registro de errores de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="069ca-117">See the SQL Server errorlog for more information.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="069ca-118">Explicación</span><span class="sxs-lookup"><span data-stu-id="069ca-118">Explanation</span></span>  
 <span data-ttu-id="069ca-119">La base de datos se marca como sospechosa porque el proceso de recuperación generó errores que ponen la base de datos en un estado transaccional coherente.</span><span class="sxs-lookup"><span data-stu-id="069ca-119">The database is marked as suspect because it failed the recovery process that brings a database to a consistent transactional state.</span></span> <span data-ttu-id="069ca-120">Esto puede suceder durante las operaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="069ca-120">This can occur during the following operations:</span></span>  
  
-   <span data-ttu-id="069ca-121">Al iniciar una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="069ca-121">Starting up an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="069ca-122">Al adjuntar una base de datos.</span><span class="sxs-lookup"><span data-stu-id="069ca-122">Attaching a database.</span></span>  
  
-   <span data-ttu-id="069ca-123">Al usar los procedimientos RESTORE base de datos o RESTORE LOG.</span><span class="sxs-lookup"><span data-stu-id="069ca-123">Using the RESTORE database or RESTORE LOG procedures.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="069ca-124">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="069ca-124">User Action</span></span>  
 <span data-ttu-id="069ca-125">Examine el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y determine la causa del error.</span><span class="sxs-lookup"><span data-stu-id="069ca-125">Inspect the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and determine the cause of the error.</span></span> <span data-ttu-id="069ca-126">Si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se ha reiniciado desde que la recuperación generó errores, busque en los registros de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anteriores para ver la razón de los errores de la recuperación.</span><span class="sxs-lookup"><span data-stu-id="069ca-126">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been restarted since the failed recovery, look at previous [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs to see the reason why recovery failed.</span></span>  
  
 <span data-ttu-id="069ca-127">Si la recuperación no tiene éxito debido a un error de E/S persistente, una página rasgada u otro posible problema de hardware, solucione el problema de hardware subyacente y restaure la base de datos a partir de una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="069ca-127">If the recovery failed because of a persistent I/O error, a torn page, or other possible hardware problem, resolve the underlying hardware problem and restore the database by using a backup.</span></span> <span data-ttu-id="069ca-128">Si no hay disponible ninguna copia de seguridad, considere las opciones de reparación de DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="069ca-128">If no backups are available, consider the repair options of DBCC CHECKDB.</span></span>  
  
 <span data-ttu-id="069ca-129">Si no puede resolver este problema, póngase en contacto con su proveedor principal de soporte.</span><span class="sxs-lookup"><span data-stu-id="069ca-129">If you are unable to resolve this problem, contact your primary support provider.</span></span> <span data-ttu-id="069ca-130">Tenga disponible el registro de errores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para revisarlo.</span><span class="sxs-lookup"><span data-stu-id="069ca-130">Have the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log available for review.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="069ca-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="069ca-131">See Also</span></span>  
 <span data-ttu-id="069ca-132">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="069ca-132">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="069ca-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="069ca-133">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="069ca-134">[Bases de datos desys.sys&#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="069ca-134">[sys.sysdatabases &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysdatabases-transact-sql) </span></span>  
 [<span data-ttu-id="069ca-135">Adjuntar y separar bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="069ca-135">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../../relational-databases/databases/database-detach-and-attach-sql-server.md)  
  
  
