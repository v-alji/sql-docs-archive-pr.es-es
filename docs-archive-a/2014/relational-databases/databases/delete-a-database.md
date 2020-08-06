---
title: Eliminación de una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- database removal [SQL Server], SQL Server Management Studio
- removing databases
- deleting databases
- dropping databases
- databases [SQL Server], dropping
- database removal [SQL Server]
ms.assetid: 1fd8c0f5-03e1-449a-af45-b8cacb479d9c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 633d97815cf69da12f1aa67fd8ef626a2d46e0b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751097"
---
# <a name="delete-a-database"></a><span data-ttu-id="45c8f-102">Eliminar una base de datos</span><span class="sxs-lookup"><span data-stu-id="45c8f-102">Delete a Database</span></span>
  <span data-ttu-id="45c8f-103">En este tema se describe cómo eliminar una base de datos definida por el usuario en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45c8f-103">This topic describes how to delete a user-defined database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="45c8f-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="45c8f-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="45c8f-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="45c8f-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="45c8f-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="45c8f-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="45c8f-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="45c8f-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="45c8f-108">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="45c8f-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="45c8f-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="45c8f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="45c8f-110">**Para eliminar una base de datos, use:**</span><span class="sxs-lookup"><span data-stu-id="45c8f-110">**To delete a database, using:**</span></span>  
  
     [<span data-ttu-id="45c8f-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="45c8f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="45c8f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="45c8f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="45c8f-113">**Seguimiento:**  [tras eliminar una base de datos](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="45c8f-113">**Follow Up:**  [After deleting a database](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="45c8f-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="45c8f-114">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="45c8f-115">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="45c8f-115">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="45c8f-116">Las bases de datos del sistema no se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="45c8f-116">System databases cannot be deleted.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="45c8f-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="45c8f-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="45c8f-118">Elimine las instantáneas de bases de datos que existan en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="45c8f-118">Delete any database snapshots that exist on the database.</span></span> <span data-ttu-id="45c8f-119">Para obtener más información, vea [Eliminar una instantánea de base de datos &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="45c8f-119">For more information, see [Drop a Database Snapshot &#40;Transact-SQL&#41;](drop-a-database-snapshot-transact-sql.md).</span></span>  
  
-   <span data-ttu-id="45c8f-120">Si la base de datos interviene en el trasvase de registros, elimínelo.</span><span class="sxs-lookup"><span data-stu-id="45c8f-120">If the database is involved in log shipping, remove log shipping.</span></span>  
  
-   <span data-ttu-id="45c8f-121">Si la base de datos se publica para la replicación transaccional, o se publica o suscribe para la replicación de mezcla, elimine la replicación de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="45c8f-121">If the database is published for transactional replication, or published or subscribed to merge replication, remove replication from the database.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="45c8f-122">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="45c8f-122">Recommendations</span></span>  
  
-   <span data-ttu-id="45c8f-123">Tenga en cuenta la posibilidad de realizar una copia de seguridad completa de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="45c8f-123">Consider taking a full backup of the database.</span></span> <span data-ttu-id="45c8f-124">Una base de datos eliminada solo puede volver a crearse si se restaura una copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="45c8f-124">A deleted database can be re-created only by restoring a backup.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="45c8f-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="45c8f-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="45c8f-126">Permisos</span><span class="sxs-lookup"><span data-stu-id="45c8f-126">Permissions</span></span>  
 <span data-ttu-id="45c8f-127">Para ejecutar DROP DATABASE, el usuario debe tener, como mínimo, el permiso CONTROL en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="45c8f-127">To execute DROP DATABASE, at a minimum, a user must have CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="45c8f-128">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="45c8f-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="45c8f-129">Para eliminar una base de datos</span><span class="sxs-lookup"><span data-stu-id="45c8f-129">To delete a database</span></span>  
  
1.  <span data-ttu-id="45c8f-130">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]y, a continuación, expándala.</span><span class="sxs-lookup"><span data-stu-id="45c8f-130">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="45c8f-131">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos que quiera eliminar y, luego, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="45c8f-131">Expand **Databases**, right-click the database to delete, and then click **Delete**.</span></span>  
  
3.  <span data-ttu-id="45c8f-132">Confirme que ha seleccionado la base de datos correcta y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="45c8f-132">Confirm the correct database is selected, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="45c8f-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="45c8f-133">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-database"></a><span data-ttu-id="45c8f-134">Para eliminar una base de datos</span><span class="sxs-lookup"><span data-stu-id="45c8f-134">To delete a database</span></span>  
  
1.  <span data-ttu-id="45c8f-135">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45c8f-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="45c8f-136">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="45c8f-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="45c8f-137">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="45c8f-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="45c8f-138">El ejemplo quita las bases de datos `Sales` y `NewSales` .</span><span class="sxs-lookup"><span data-stu-id="45c8f-138">The example removes the `Sales` and `NewSales` databases.</span></span>  
  
```sql  
USE master ;  
GO  
DROP DATABASE Sales, NewSales ;  
GO  
```  
  
##  <a name="follow-up-after-deleting-a-database"></a><a name="FollowUp"></a> <span data-ttu-id="45c8f-139">Seguimiento: tras eliminar una base de datos</span><span class="sxs-lookup"><span data-stu-id="45c8f-139">Follow Up: After deleting a database</span></span>  
 <span data-ttu-id="45c8f-140">Hacer una copia de seguridad de la base de datos **maestra** .</span><span class="sxs-lookup"><span data-stu-id="45c8f-140">Back up the **master** database.</span></span> <span data-ttu-id="45c8f-141">Si es necesario restaurar la base de datos **maestra** , cualquier base de datos que se haya eliminado después de la última copia de seguridad **maestra** seguirá teniendo referencias en las vistas del catálogo del sistema y puede dar lugar a la aparición de mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="45c8f-141">If **master** must be restored, any database that has been deleted since the last backup of **master** will still have references in the system catalog views and may cause error messages to be raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c8f-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="45c8f-142">See Also</span></span>  
 <span data-ttu-id="45c8f-143">[CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="45c8f-143">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="45c8f-144">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="45c8f-144">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
