---
title: Eliminar una instantánea de base de datos (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- removing database snapshots
- deleting database snapshots
- database snapshots [SQL Server], deleting
ms.assetid: ad70ec97-d5fb-41aa-b72a-915e74b61b76
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0d9d912a092e581fad7d3d53504309f63ba1806
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662083"
---
# <a name="drop-a-database-snapshot-transact-sql"></a><span data-ttu-id="e229e-102">Eliminar una instantánea de base de datos (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e229e-102">Drop a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="e229e-103">Al quitar una instantánea de base de datos, ésta se elimina de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y se eliminan también los archivos dispersos que utiliza.</span><span class="sxs-lookup"><span data-stu-id="e229e-103">Dropping a database snapshot deletes the database snapshot from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and deletes the sparse files that are used by the snapshot.</span></span> <span data-ttu-id="e229e-104">Cuando se quita una instantánea de base de datos, se terminan también todas sus conexiones de usuario.</span><span class="sxs-lookup"><span data-stu-id="e229e-104">When you drop a database snapshot, all user connections to it are terminated.</span></span>  
  
## <a name="security"></a><span data-ttu-id="e229e-105">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e229e-105">Security</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e229e-106">Permisos</span><span class="sxs-lookup"><span data-stu-id="e229e-106">Permissions</span></span>  
 <span data-ttu-id="e229e-107">Cualquier usuario con permisos DROP DATABASE puede quitar una instantánea de base de datos.</span><span class="sxs-lookup"><span data-stu-id="e229e-107">Any user with DROP DATABASE permissions can drop a database snapshot.</span></span>  
  
##  <a name="how-to-drop-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e229e-108">Quitar una instantánea de base de datos (mediante Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e229e-108">How to Drop a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="e229e-109">**Para quitar una instantánea de base de datos**</span><span class="sxs-lookup"><span data-stu-id="e229e-109">**To drop a database snapshot**</span></span>  
  
1.  <span data-ttu-id="e229e-110">Identifique la instantánea de base de datos que desee quitar.</span><span class="sxs-lookup"><span data-stu-id="e229e-110">Identify the database snapshot that you want to drop.</span></span> <span data-ttu-id="e229e-111">Puede ver las instantáneas de una base de datos en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e229e-111">You can view the snapshots on a database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="e229e-112">Para obtener más información, vea [Ver una instantánea de base de datos &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e229e-112">For more information, see [View a Database Snapshot &#40;SQL Server&#41;](view-a-database-snapshot-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="e229e-113">Ejecute una instrucción [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) especificando el nombre de la instantánea de base de datos que se quitará.</span><span class="sxs-lookup"><span data-stu-id="e229e-113">Issue a [DROP DATABASE](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) statement, specifying the name of the database snapshot to be dropped.</span></span> <span data-ttu-id="e229e-114">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="e229e-114">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="e229e-115">DROP DATABASE *nombre_de_instantánea_de_base_de_datos* [ **,** ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="e229e-115">DROP DATABASE *database_snapshot_name* [ **,**...*n* ]</span></span>  
  
     <span data-ttu-id="e229e-116">Donde *nombre_de_instantánea_de_base_de_datos* es el nombre de la instantánea de base de datos que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="e229e-116">Where *database_snapshot_name* is the name of the database snapshot to be dropped.</span></span>  
  
####  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="e229e-117">Ejemplo (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="e229e-117">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="e229e-118">En este ejemplo se quita una instantánea de base de datos, denominada SalesSnapshot0600, sin que la base de datos de origen se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="e229e-118">This example drops a database snapshot named SalesSnapshot0600, without affecting the source database.</span></span>  
  
```  
DROP DATABASE SalesSnapshot0600 ;  
```  
  
 <span data-ttu-id="e229e-119">Finalizan todas las conexiones de usuario a SalesSnapshot0600 y se eliminan todos los archivos dispersos del sistema de archivos NTFS que utiliza la instantánea.</span><span class="sxs-lookup"><span data-stu-id="e229e-119">Any user connections to SalesSnapshot0600 are terminated, and all of the NTFS file system sparse files used by the snapshot are deleted.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e229e-120">Para obtener más información sobre cómo las instantáneas de base de datos usan archivos dispersos, vea [Instantáneas de base de datos &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e229e-120">For information about the use of sparse files by database snapshots, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e229e-121">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="e229e-121">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e229e-122">Crear una instantánea de base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e229e-122">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="e229e-123">Ver una instantánea de base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e229e-123">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="e229e-124">Revertir una base de datos a una instantánea de base de datos</span><span class="sxs-lookup"><span data-stu-id="e229e-124">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="e229e-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e229e-125">See Also</span></span>  
 <span data-ttu-id="e229e-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e229e-126">[DROP DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-database-audit-specification-transact-sql) </span></span>  
 [<span data-ttu-id="e229e-127">Instantáneas de bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e229e-127">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
