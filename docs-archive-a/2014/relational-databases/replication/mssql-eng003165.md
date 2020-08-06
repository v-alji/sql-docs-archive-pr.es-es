---
title: MSSQL_ENG003165 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG003165 error
ms.assetid: 707d33dd-644e-4cc9-ac51-dddd49031530
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1702588ba6ac1beeb33b87a7afc7fc330271559
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87661945"
---
# <a name="mssql_eng003165"></a><span data-ttu-id="a3ecf-102">MSSQL_ENG003165</span><span class="sxs-lookup"><span data-stu-id="a3ecf-102">MSSQL_ENG003165</span></span>
    
## <a name="message-details"></a><span data-ttu-id="a3ecf-103">Detalles del mensaje</span><span class="sxs-lookup"><span data-stu-id="a3ecf-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a3ecf-104">Nombre de producto</span><span class="sxs-lookup"><span data-stu-id="a3ecf-104">Product Name</span></span>|<span data-ttu-id="a3ecf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a3ecf-105">SQL Server</span></span>|  
|<span data-ttu-id="a3ecf-106">Id. de evento</span><span class="sxs-lookup"><span data-stu-id="a3ecf-106">Event ID</span></span>|<span data-ttu-id="a3ecf-107">3165</span><span class="sxs-lookup"><span data-stu-id="a3ecf-107">3165</span></span>|  
|<span data-ttu-id="a3ecf-108">Origen de eventos</span><span class="sxs-lookup"><span data-stu-id="a3ecf-108">Event Source</span></span>|<span data-ttu-id="a3ecf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a3ecf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a3ecf-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a3ecf-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="a3ecf-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="a3ecf-111">Symbolic Name</span></span>||  
|<span data-ttu-id="a3ecf-112">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="a3ecf-112">Message Text</span></span>|<span data-ttu-id="a3ecf-113">La base de datos '%ls' se restauró. Sin embargo, se encontró un error al restaurar o quitar la replicación.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-113">Database '%ls' was restored; however, an error was encountered while replication was being restored/removed.</span></span> <span data-ttu-id="a3ecf-114">Se ha dejado la base de datos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-114">The database has been left offline.</span></span> <span data-ttu-id="a3ecf-115">Vea el tema MSSQL_ENG003165 en los Libros en pantalla de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-115">See the topic MSSQL_ENG003165 in SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a3ecf-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="a3ecf-116">Explanation</span></span>  
 <span data-ttu-id="a3ecf-117">Este error aparece si se produce un problema al restaurar una copia de seguridad de una base de datos replicada:</span><span class="sxs-lookup"><span data-stu-id="a3ecf-117">This error is raised if a problem occurs restoring a backup of a replicated database:</span></span>  
  
-   <span data-ttu-id="a3ecf-118">Si la copia de seguridad se restaura en la misma base de datos y el mismo servidor en los que se realizó, el error indica que no se ha podido restaurar correctamente la configuración de la replicación.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-118">If the backup is being restored to the same database and server on which it was taken, the error indicates that replication settings could not be restored properly.</span></span>  
  
-   <span data-ttu-id="a3ecf-119">Si la copia de seguridad se restaura en una base de datos o un servidor distintos, el error indica que no se ha podido quitar correctamente la configuración de la replicación (de forma predeterminada, la configuración de la replicación se quita si la base de datos o el servidor son distintos).</span><span class="sxs-lookup"><span data-stu-id="a3ecf-119">If the backup is being restored to a different database or server, the error indicates that replication settings could not be removed properly (by default, replication settings are removed if the database or server is different).</span></span>  
  
 <span data-ttu-id="a3ecf-120">Este error probablemente se debe a una discrepancia entre el estado de la base de datos restaurada y una o más bases de datos del sistema que contienen metadatos de replicación: **msdb**, **maestra**o la base de datos de distribución.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-120">The error is probably the result of a mismatch between the state of the restored database and one or more system databases that contain replication metadata: **msdb**, **master**, or the distribution database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a3ecf-121">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="a3ecf-121">User Action</span></span>  
 <span data-ttu-id="a3ecf-122">Para solucionar este problema:</span><span class="sxs-lookup"><span data-stu-id="a3ecf-122">To resolve this issue:</span></span>  
  
1.  <span data-ttu-id="a3ecf-123">Ejecute ALTER DATABASE para conectar la base de datos en línea; por ejemplo: `ALTER DATABASE AdventureWorks SET ONLINE`.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-123">Execute ALTER DATABASE to bring the database online; for example: `ALTER DATABASE AdventureWorks SET ONLINE`.</span></span> <span data-ttu-id="a3ecf-124">Para obtener más información, vea [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a3ecf-124">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span> <span data-ttu-id="a3ecf-125">Si desea conservar la configuración de la réplica, vaya al paso 2.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-125">If you want to preserve replication settings, go to step 2.</span></span> <span data-ttu-id="a3ecf-126">En caso contrario, continúe en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-126">If not, go to step 3.</span></span>  
  
2.  <span data-ttu-id="a3ecf-127">Ejecute [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a3ecf-127">Execute [sp_restoredbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-restoredbreplication-transact-sql).</span></span> <span data-ttu-id="a3ecf-128">Si este procedimiento almacenado se ejecuta correctamente, la restauración ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-128">If this stored procedure executes successfully, the restore is complete.</span></span> <span data-ttu-id="a3ecf-129">Si no se ejecuta correctamente, vaya al paso 3.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-129">If it does not execute successfully, go to step 3.</span></span>  
  
3.  <span data-ttu-id="a3ecf-130">Ejecute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) para eliminar la configuración de replicación completa.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-130">Execute [sp_removedbreplication &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-removedbreplication-transact-sql) to remove all replication settings.</span></span>  
  
     <span data-ttu-id="a3ecf-131">Si es necesario, vuelva a configurar la replicación.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-131">Reconfigure replication if necessary.</span></span> <span data-ttu-id="a3ecf-132">Si, tal y como se recomienda, ha creado scripts para la topología de replicación, utilícelos para volver a configurar la topología.</span><span class="sxs-lookup"><span data-stu-id="a3ecf-132">If you have scripted the replication topology as recommended, use scripts to reconfigure the topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ecf-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a3ecf-133">See Also</span></span>  
 <span data-ttu-id="a3ecf-134">[Realizar copias de seguridad y restaurar bases de datos de SQL Server](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a3ecf-134">[Back Up and Restore of SQL Server Databases](../backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="a3ecf-135">[Hacer copias de seguridad y restaurar bases de datos replicadas](administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a3ecf-135">[Back Up and Restore Replicated Databases](administration/back-up-and-restore-replicated-databases.md) </span></span>  
 [<span data-ttu-id="a3ecf-136">Referencia de errores y eventos &#40;replicación&#41;</span><span class="sxs-lookup"><span data-stu-id="a3ecf-136">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
