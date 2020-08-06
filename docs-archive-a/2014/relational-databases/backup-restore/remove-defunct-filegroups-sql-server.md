---
title: Eliminación de grupos de archivos inactivos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- piecemeal restores [SQL Server], defunct filegroups
- defunct filegroups
- restoring filegroups [SQL Server]
- deferred transactions
- filegroups [SQL Server], defunct
- unrestored filegroups
ms.assetid: 055f9c6a-5c18-4942-98e7-ec918f0ff975
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2bcba095d668c5c1ab317269a18af4dc996f63b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748140"
---
# <a name="remove-defunct-filegroups-sql-server"></a><span data-ttu-id="0a733-102">Quitar grupos de archivos inactivos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0a733-102">Remove Defunct Filegroups (SQL Server)</span></span>
  <span data-ttu-id="0a733-103">En este tema se describe cómo quitar grupos de archivos inactivos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a733-103">This topic describes how to remove defunct filegroups in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0a733-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="0a733-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0a733-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="0a733-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0a733-106">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="0a733-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="0a733-107">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="0a733-107">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="0a733-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0a733-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0a733-109">**Para quitar grupos de archivos inactivos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="0a733-109">**To remove defunct filegroups, using:**</span></span>  
  
     [<span data-ttu-id="0a733-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a733-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0a733-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a733-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0a733-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="0a733-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="0a733-113">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="0a733-113">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="0a733-114">Este tema es pertinente para las bases de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que incluyen varios archivos o grupos de archivos y, en el modelo simple, solo para grupos de archivos de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="0a733-114">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases that contain multiple files or filegroups; and, under the simple model, only for read-only filegroups.</span></span>  
  
-   <span data-ttu-id="0a733-115">Todos los archivos de un grupo de archivos pasan a estar inactivos cuando se quita un grupo de archivos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="0a733-115">All files in a filegroup become defunct when an offline filegroup is removed.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="0a733-116">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="0a733-116">Recommendations</span></span>  
  
-   <span data-ttu-id="0a733-117">Si no se va a restaurar nunca un grupo de archivos sin restaurar, se puede convertir en *inactivo* quitándolo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0a733-117">If an unrestored filegroup will never have to be restored, you can make the filegroup *defunct* by removing it from the database.</span></span> <span data-ttu-id="0a733-118">El grupo de archivos inactivo no se podrá restaurar nunca en esta base de datos, aunque los metadatos permanecen en ella.</span><span class="sxs-lookup"><span data-stu-id="0a733-118">The defunct filegroup can never be restored to this database, but its metadata remains.</span></span> <span data-ttu-id="0a733-119">Una vez inactivo el grupo de archivos, la base de datos se puede reiniciar y la recuperación hará que la base de datos sea coherente en todos los grupos de archivos restaurados.</span><span class="sxs-lookup"><span data-stu-id="0a733-119">After the filegroup is defunct, the database can be restarted, and recovery will make the database consistent across the restored filegroups.</span></span>  
  
     <span data-ttu-id="0a733-120">Por ejemplo, establecer un grupo de archivos como inactivo es una opción para resolver transacciones diferidas generadas por un grupo de archivos sin conexión que ya no es necesario en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0a733-120">For example, making a filegroup defunct is an option for resolving deferred transactions that were caused by an offline filegroup that you no longer want in the database.</span></span> <span data-ttu-id="0a733-121">Las transacciones que estaban diferidas porque el grupo de archivos estaba sin conexión salen del estado diferido una vez que el grupo de archivos queda inactivo.</span><span class="sxs-lookup"><span data-stu-id="0a733-121">Transactions that were deferred because the filegroup was offline are moved out of the deferred state after the filegroup becomes defunct.</span></span> <span data-ttu-id="0a733-122">Para obtener más información, vea [Transacciones diferidas &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0a733-122">For more information, see [Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0a733-123">Seguridad</span><span class="sxs-lookup"><span data-stu-id="0a733-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0a733-124">Permisos</span><span class="sxs-lookup"><span data-stu-id="0a733-124">Permissions</span></span>  
 <span data-ttu-id="0a733-125">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0a733-125">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0a733-126">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0a733-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="0a733-127">Para quitar grupos de archivos inactivos</span><span class="sxs-lookup"><span data-stu-id="0a733-127">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="0a733-128">En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="0a733-128">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0a733-129">Expanda **Bases de datos**, haga clic con el botón derecho en la base de datos de la que quiera eliminar el archivo y, después, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0a733-129">Expand **Databases**, right-click the database from which to delete the file, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0a733-130">Seleccione la página **Archivos** .</span><span class="sxs-lookup"><span data-stu-id="0a733-130">Select the **Files** page.</span></span>  
  
4.  <span data-ttu-id="0a733-131">En la cuadrícula **Archivos de base de datos** , seleccione los archivos que desee eliminar, haga clic en **Quitar**y, a continuación en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a733-131">In the **Database files** grid, select the files to delete, click **Remove**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="0a733-132">Seleccione la página **Grupos de archivos** .</span><span class="sxs-lookup"><span data-stu-id="0a733-132">Select the **Filegroups** page.</span></span>  
  
6.  <span data-ttu-id="0a733-133">En la cuadrícula **Filas** , seleccione el grupo de archivos que desee eliminar, haga clic en **Quitar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a733-133">In the **Rows** grid, select the filegroup to delete, click **Remove**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0a733-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0a733-134">Using Transact-SQL</span></span>  
  
#### <a name="to-remove-defunct-filegroups"></a><span data-ttu-id="0a733-135">Para quitar grupos de archivos inactivos</span><span class="sxs-lookup"><span data-stu-id="0a733-135">To remove defunct filegroups</span></span>  
  
1.  <span data-ttu-id="0a733-136">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a733-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0a733-137">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="0a733-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0a733-138">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="0a733-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0a733-139">(**Nota:** En este ejemplo se supone que ya existen los archivos y el grupo de archivos.</span><span class="sxs-lookup"><span data-stu-id="0a733-139">(**Note:** This example assumes that the files and filegroup already exist.</span></span> <span data-ttu-id="0a733-140">Para crear estos objetos, vea el ejemplo B del tema [Opciones File y Filegroup de ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options)). En el primer ejemplo se quitan los archivos `test1dat3` y `test1dat4` del grupo de archivos inactivo utilizando la instrucción `ALTER DATABASE` con la cláusula `REMOVE FILE`.</span><span class="sxs-lookup"><span data-stu-id="0a733-140">To create these objects, see example B in the [ALTER DATABASE File and Filegroup Options](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) topic.) The first example removes the `test1dat3` and `test1dat4` files from the defunct filegroup by using the `ALTER DATABASE` statement with the `REMOVE FILE` clause.</span></span> <span data-ttu-id="0a733-141">En el segundo ejemplo se quita el grupo de archivos inactivo `Test1FG1`utilizando la cláusula `REMOVE FILEGROUP` .</span><span class="sxs-lookup"><span data-stu-id="0a733-141">The second example removes the defunct filegroup `Test1FG1`by using the `REMOVE FILEGROUP` clause.</span></span>  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat3 ;  
ALTER DATABASE AdventureWorks2012  
REMOVE FILE test1dat4 ;  
GO  
  
```  
  
```sql  
USE master;  
GO  
ALTER DATABASE AdventureWorks2012  
REMOVE FILEGROUP Test1FG1 ;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a733-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a733-142">See Also</span></span>  
 <span data-ttu-id="0a733-143">[Opciones File y Filegroup de ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span><span class="sxs-lookup"><span data-stu-id="0a733-143">[ALTER DATABASE File and Filegroup Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-file-and-filegroup-options) </span></span>  
 <span data-ttu-id="0a733-144">[Transacciones diferidas &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a733-144">[Deferred Transactions &#40;SQL Server&#41;](deferred-transactions-sql-server.md) </span></span>  
 <span data-ttu-id="0a733-145">[Restauraciones de archivos &#40;modelo de recuperación completa&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="0a733-145">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="0a733-146">[Restauraciones de archivos &#40;modelo de recuperación simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="0a733-146">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="0a733-147">[Restauración con conexión &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a733-147">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="0a733-148">[Restaurar páginas &#40;SQL Server&#41;](restore-pages-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0a733-148">[Restore Pages &#40;SQL Server&#41;](restore-pages-sql-server.md) </span></span>  
 [<span data-ttu-id="0a733-149">Restauraciones por etapas &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0a733-149">Piecemeal Restores &#40;SQL Server&#41;</span></span>](piecemeal-restores-sql-server.md)  
  
  
