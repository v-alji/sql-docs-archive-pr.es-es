---
title: Separar una base de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.detachdatabase.f1
helpviewer_keywords:
- database detaching [SQL Server]
- detaching databases [SQL Server]
ms.assetid: f63d4107-13e4-4bfe-922d-5e4f712e472d
author: stevestein
ms.author: sstein
ms.openlocfilehash: b8acc809b881012d18f78995bb8e521337fb02ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677663"
---
# <a name="detach-a-database"></a><span data-ttu-id="3da0f-102">Separar una base de datos</span><span class="sxs-lookup"><span data-stu-id="3da0f-102">Detach a Database</span></span>
  <span data-ttu-id="3da0f-103">En este tema se describe cómo separar una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3da0f-103">This topic describes how to detach a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3da0f-104">Los archivos separados permanecen y se pueden volver a adjuntar utilizando CREATE DATABASE con la opción FOR ATTACH o FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="3da0f-104">The detached files remain and can be reattached by using CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="3da0f-105">Los archivos se pueden mover a otro servidor y adjuntarse allí.</span><span class="sxs-lookup"><span data-stu-id="3da0f-105">The files can be moved to another server and attached there.</span></span>  
  
 <span data-ttu-id="3da0f-106">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="3da0f-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="3da0f-107">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="3da0f-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="3da0f-108">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="3da0f-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="3da0f-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3da0f-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="3da0f-110">**Para separar una base de datos, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="3da0f-110">**To detach a database, using:**</span></span>  
  
     [<span data-ttu-id="3da0f-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3da0f-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="3da0f-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3da0f-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3da0f-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="3da0f-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3da0f-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="3da0f-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="3da0f-115">Para obtener una lista de las limitaciones y restricciones, vea [Adjuntar y separar bases de datos &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3da0f-115">For a list of limitations and restrictions, see [Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3da0f-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="3da0f-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3da0f-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="3da0f-117">Permissions</span></span>  
 <span data-ttu-id="3da0f-118">Requiere pertenencia al rol fijo de base de datos db_owner.</span><span class="sxs-lookup"><span data-stu-id="3da0f-118">Requires membership in the db_owner fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3da0f-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3da0f-119">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="3da0f-120">Para separar una base de datos</span><span class="sxs-lookup"><span data-stu-id="3da0f-120">To detach a database</span></span>  
  
1.  <span data-ttu-id="3da0f-121">En el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , conéctese a la instancia del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] y expándala.</span><span class="sxs-lookup"><span data-stu-id="3da0f-121">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and then expand the instance.</span></span>  
  
2.  <span data-ttu-id="3da0f-122">Expanda **Bases de datos**y seleccione el nombre de la base de datos de usuarios que desee separar.</span><span class="sxs-lookup"><span data-stu-id="3da0f-122">Expand **Databases**, and select the name of the user database you want to detach.</span></span>  
  
3.  <span data-ttu-id="3da0f-123">Haga clic con el botón derecho en el nombre de la base de datos, seleccione **Tareas**y haga clic en **Separar**.</span><span class="sxs-lookup"><span data-stu-id="3da0f-123">Right-click the database name, point to **Tasks**, and then click **Detach**.</span></span> <span data-ttu-id="3da0f-124">Aparecerá el cuadro de diálogo **Separar base de datos** .</span><span class="sxs-lookup"><span data-stu-id="3da0f-124">The **Detach Database** dialog box appears.</span></span>  
  
     <span data-ttu-id="3da0f-125">**Bases de datos que se van a separar**</span><span class="sxs-lookup"><span data-stu-id="3da0f-125">**Databases to detach**</span></span>  
     <span data-ttu-id="3da0f-126">Enumera las bases de datos que se van a separar.</span><span class="sxs-lookup"><span data-stu-id="3da0f-126">Lists the databases to detach.</span></span>  
  
     <span data-ttu-id="3da0f-127">**Nombre de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="3da0f-127">**Database Name**</span></span>  
     <span data-ttu-id="3da0f-128">Muestra el nombre de la base de datos que se va a separar.</span><span class="sxs-lookup"><span data-stu-id="3da0f-128">Displays the name of the database to be detached.</span></span>  
  
     <span data-ttu-id="3da0f-129">**Quitar conexiones**</span><span class="sxs-lookup"><span data-stu-id="3da0f-129">**Drop Connections**</span></span>  
     <span data-ttu-id="3da0f-130">Desconecta las conexiones a la base de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="3da0f-130">Disconnect connections to the specified database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3da0f-131">No puede separar una base de datos con conexiones activas.</span><span class="sxs-lookup"><span data-stu-id="3da0f-131">You cannot detach a database with active connections.</span></span>  
  
     <span data-ttu-id="3da0f-132">**Actualizar estadísticas**</span><span class="sxs-lookup"><span data-stu-id="3da0f-132">**Update Statistics**</span></span>  
     <span data-ttu-id="3da0f-133">De forma predeterminada, la operación de separación conserva las estadísticas de optimización obsoletas al separar la base de datos; para actualizar las estadísticas de optimización existentes, haga clic en esta casilla.</span><span class="sxs-lookup"><span data-stu-id="3da0f-133">By default, the detach operation retains any out-of-date optimization statistics when detaching the database; to update the existing optimization statistics, click this check box.</span></span>  
  
     <span data-ttu-id="3da0f-134">**Mantener catálogos de texto completo**</span><span class="sxs-lookup"><span data-stu-id="3da0f-134">**Keep Full-Text Catalogs**</span></span>  
     <span data-ttu-id="3da0f-135">De forma predeterminada, la operación de separación conserva los catálogos de texto completo asociados a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="3da0f-135">By default, the detach operation keeps any full-text catalogs that are associated with the database.</span></span> <span data-ttu-id="3da0f-136">Para quitarlos, desactive la casilla **Mantener catálogos de texto completo** .</span><span class="sxs-lookup"><span data-stu-id="3da0f-136">To remove them, clear the **Keep Full-Text Catalogs** check box.</span></span> <span data-ttu-id="3da0f-137">Esta opción solo aparece cuando se está actualizando una base de datos desde [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3da0f-137">This option appears only when you are upgrading a database from [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
     <span data-ttu-id="3da0f-138">**Estado**</span><span class="sxs-lookup"><span data-stu-id="3da0f-138">**Status**</span></span>  
     <span data-ttu-id="3da0f-139">Muestra uno de los siguientes estados: **Listo** o **No está listo**.</span><span class="sxs-lookup"><span data-stu-id="3da0f-139">Displays one of the following states: **Ready** or **Not ready**.</span></span>  
  
     <span data-ttu-id="3da0f-140">**Mensaje**</span><span class="sxs-lookup"><span data-stu-id="3da0f-140">**Message**</span></span>  
     <span data-ttu-id="3da0f-141">En la columna **Mensaje** puede aparecer información sobre la base de datos, tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="3da0f-141">The **Message** column may display information about the database, as follows:</span></span>  
  
    -   <span data-ttu-id="3da0f-142">Cuando una base de datos está implicada en una replicación, el **Estado** es **No está listo** y la columna **Mensaje** muestra **Base de datos replicada**.</span><span class="sxs-lookup"><span data-stu-id="3da0f-142">When a database is involved with replication, the **Status** is **Not ready** and the **Message** column displays **Database replicated**.</span></span>  
  
    -   <span data-ttu-id="3da0f-143">Cuando una base de datos tiene una o varias conexiones activas, el valor de **Estado** es **No está listo** y en la columna **Mensaje** se muestra _<número_de_conexiones_activas>_ **Conexiones activas** (por ejemplo: **1 conexión activa**).</span><span class="sxs-lookup"><span data-stu-id="3da0f-143">When a database has one or more active connections, the **Status** is **Not ready** and the **Message** column displays _<number_of_active_connections>_**Active connection(s)** - for example: **1 Active connection(s)**.</span></span> <span data-ttu-id="3da0f-144">Antes de separar la base de datos, debe desconectar todas las conexiones activas seleccionando **Quitar conexiones**.</span><span class="sxs-lookup"><span data-stu-id="3da0f-144">Before you can detach the database, you need to disconnect any active connections by selecting **Drop Connections**.</span></span>  
  
     <span data-ttu-id="3da0f-145">Para obtener más información acerca de un mensaje, haga clic en el texto con hipervínculo para abrir el Monitor de actividad.</span><span class="sxs-lookup"><span data-stu-id="3da0f-145">To obtain more information about a message, click the hyperlinked text to open Activity Monitor.</span></span>  
  
4.  <span data-ttu-id="3da0f-146">Cuando esté listo para separar la base de datos, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3da0f-146">When you are ready to detach the database, click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3da0f-147">La base de datos recién separada permanecerá visible en el nodo **Bases de datos** del Explorador de objetos hasta que se actualice la vista.</span><span class="sxs-lookup"><span data-stu-id="3da0f-147">The newly detached database will remain visible in the **Databases** node of Object Explorer until the view is refreshed.</span></span> <span data-ttu-id="3da0f-148">Puede actualizar la vista en cualquier momento: haga clic en el panel del Explorador de objetos y en la barra de menús seleccione **Ver** y, a continuación, **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="3da0f-148">You can refresh the view at any time: Click in the Object Explorer pane, and from the menu bar select **View** and then **Refresh**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3da0f-149">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3da0f-149">Using Transact-SQL</span></span>  
  
#### <a name="to-detach-a-database"></a><span data-ttu-id="3da0f-150">Para separar una base de datos</span><span class="sxs-lookup"><span data-stu-id="3da0f-150">To detach a database</span></span>  
  
1.  <span data-ttu-id="3da0f-151">Conéctese con el [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3da0f-151">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3da0f-152">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="3da0f-152">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3da0f-153">Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="3da0f-153">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3da0f-154">En este ejemplo se separa la base de datos AdventureWorks2012 con el valor de skipchecks establecido en true.</span><span class="sxs-lookup"><span data-stu-id="3da0f-154">This example detaches the AdventureWorks2012 database with skipchecks set to true.</span></span>  
  
```  
EXEC sp_detach_db 'AdventureWorks2012', 'true';  
```  
  
## <a name="see-also"></a><span data-ttu-id="3da0f-155">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3da0f-155">See Also</span></span>  
 <span data-ttu-id="3da0f-156">[Adjuntar y separar bases de datos &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3da0f-156">[Database Detach and Attach &#40;SQL Server&#41;](database-detach-and-attach-sql-server.md) </span></span>  
 [<span data-ttu-id="3da0f-157">sp_detach_db &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3da0f-157">sp_detach_db &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-detach-db-transact-sql)  
  
  
