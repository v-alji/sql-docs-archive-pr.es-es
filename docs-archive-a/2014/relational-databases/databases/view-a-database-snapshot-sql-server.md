---
title: Ver una instantánea de base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], viewing
- displaying database snapshots
- viewing database snapshots
ms.assetid: 123f19b2-0850-4033-8507-59ebdfb368ee
author: stevestein
ms.author: sstein
ms.openlocfilehash: 92c5c557656e87be562e9d5477f14f66b2c39e7b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749973"
---
# <a name="view-a-database-snapshot-sql-server"></a><span data-ttu-id="d236d-102">Ver una instantánea de base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d236d-102">View a Database Snapshot (SQL Server)</span></span>
  <span data-ttu-id="d236d-103">En este tema se explica cómo ver una instantánea de base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d236d-103">This topic explains how to view a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d236d-104">Para crear, volver a una versión anterior o eliminar una instantánea de base de datos, se debe usar [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d236d-104">To create, revert to, or delete a database snapshot, you must use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d236d-105">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="d236d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d236d-106">**Para ver una instantánea de base de datos mediante:**</span><span class="sxs-lookup"><span data-stu-id="d236d-106">**To view a database snapshot, using:**</span></span>  
  
     [<span data-ttu-id="d236d-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d236d-107">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d236d-108">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d236d-108">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d236d-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d236d-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d236d-110">**Para ver una instantánea de base de datos**</span><span class="sxs-lookup"><span data-stu-id="d236d-110">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="d236d-111">En el Explorador de objetos, conéctese a la instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="d236d-111">In Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d236d-112">Expanda **Bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="d236d-112">Expand **Databases.**</span></span>  
  
3.  <span data-ttu-id="d236d-113">Expanda **Instantáneas de base de datos**y, a continuación, seleccione la instantánea que desee ver.</span><span class="sxs-lookup"><span data-stu-id="d236d-113">Expand **Database Snapshots**, and select the snapshot you want to view.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d236d-114">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d236d-114">Using Transact-SQL</span></span>  
 <span data-ttu-id="d236d-115">**Para ver una instantánea de base de datos**</span><span class="sxs-lookup"><span data-stu-id="d236d-115">**To view a database snapshot**</span></span>  
  
1.  <span data-ttu-id="d236d-116">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d236d-116">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d236d-117">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="d236d-117">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d236d-118">Para enumerar las instantáneas de base de datos de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte la columna **source_database_id** de la vista de catálogo [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) para ver si hay valores distintos de NULL.</span><span class="sxs-lookup"><span data-stu-id="d236d-118">To list the database snapshots of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], query the **source_database_id** column of the [sys.databases](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql) catalog view for non-NULL values.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d236d-119">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d236d-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d236d-120">Crear una instantánea de base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d236d-120">Create a Database Snapshot &#40;Transact-SQL&#41;</span></span>](create-a-database-snapshot-transact-sql.md)  
  
-   [<span data-ttu-id="d236d-121">Revertir una base de datos a una instantánea de base de datos</span><span class="sxs-lookup"><span data-stu-id="d236d-121">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="d236d-122">Eliminar una instantánea de base de datos &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d236d-122">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="d236d-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d236d-123">See Also</span></span>  
 [<span data-ttu-id="d236d-124">Instantáneas de bases de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d236d-124">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
