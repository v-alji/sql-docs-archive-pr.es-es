---
title: Pausar o reanudar una sesión de creación de reflejo de la base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- resuming database mirroring
- database mirroring [SQL Server], sessions
- database mirroring [SQL Server], pausing
- database mirroring [SQL Server], resuming
- pausing database mirroring
ms.assetid: 05ede3b4-6abe-4442-abb7-9f5aee1d6bc0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b8a9e30bed3ff268fcfdc6e352ad15ebedfe4e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746515"
---
# <a name="pause-or-resume-a-database-mirroring-session-sql-server"></a><span data-ttu-id="daeb7-102">Pausar o reanudar una sesión de creación de reflejo de la base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="daeb7-102">Pause or Resume a Database Mirroring Session (SQL Server)</span></span>
  <span data-ttu-id="daeb7-103">En este tema se describe cómo pausar o reanudar la creación de reflejo de la base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="daeb7-103">This topic describes how to pause or resume database mirroring in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="daeb7-104">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="daeb7-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="daeb7-105">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="daeb7-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="daeb7-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="daeb7-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="daeb7-107">**Para ReplaceThisText con:**</span><span class="sxs-lookup"><span data-stu-id="daeb7-107">**To ReplaceThisText, using:**</span></span>  
  
     [<span data-ttu-id="daeb7-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daeb7-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="daeb7-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daeb7-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="daeb7-110">**Seguimiento:**  [después de pausar o reanudar la creación de reflejo de la base de datos](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="daeb7-110">**Follow Up:**  [After Pausing or Resuming Database Mirroring](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="daeb7-111">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="daeb7-111">Before You Begin</span></span>  
 <span data-ttu-id="daeb7-112">En cualquier momento, puede suspender una sesión de creación de reflejo de la base de datos, lo que puede mejorar el rendimiento durante los cuellos de botella, y puede reanudar una sesión suspendida.</span><span class="sxs-lookup"><span data-stu-id="daeb7-112">At any time, you can suspend a database mirroring session, which might improve performance during bottlenecks, and you can resume a suspended session at any time.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="daeb7-113">Después de un servicio forzado, cuando el servidor principal original se vuelve a conectar, se suspende la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="daeb7-113">After a forced service, when the original principal server reconnects, mirroring is suspended.</span></span> <span data-ttu-id="daeb7-114">Reanudar la creación de reflejo en esta situación puede dar lugar a una pérdida de datos en el servidor principal original.</span><span class="sxs-lookup"><span data-stu-id="daeb7-114">Resuming mirroring in this situation could possibly cause data loss on the original principal server.</span></span> <span data-ttu-id="daeb7-115">Para obtener información sobre la administración de la posible pérdida de datos, vea [Conmutación de roles durante una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="daeb7-115">For information about managing the potential data loss, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="daeb7-116">Seguridad</span><span class="sxs-lookup"><span data-stu-id="daeb7-116">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="daeb7-117">Permisos</span><span class="sxs-lookup"><span data-stu-id="daeb7-117">Permissions</span></span>  
 <span data-ttu-id="daeb7-118">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="daeb7-118">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="daeb7-119">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="daeb7-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="daeb7-120">Para pausar o reanudar una sesión de creación de reflejo de la base de datos, use la página **Creación de reflejo de Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="daeb7-120">To pause or resume a database mirroring session use the **Database Properties Mirroring** page.</span></span>  
  
#### <a name="to-pause-or-resume-database-mirroring"></a><span data-ttu-id="daeb7-121">Para pausar o reanudar la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="daeb7-121">To pause or resume database mirroring</span></span>  
  
1.  <span data-ttu-id="daeb7-122">Durante una sesión de creación de reflejo de la base de datos, conéctese a la instancia de servidor principal y, en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="daeb7-122">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="daeb7-123">Expanda **Bases de datos**y seleccione la base de datos.</span><span class="sxs-lookup"><span data-stu-id="daeb7-123">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="daeb7-124">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, luego, haga clic en **Reflejado**.</span><span class="sxs-lookup"><span data-stu-id="daeb7-124">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="daeb7-125">Así se abre la página **Creación de reflejo** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="daeb7-125">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="daeb7-126">Para pausar la sesión, haga clic en **Pausar**.</span><span class="sxs-lookup"><span data-stu-id="daeb7-126">To pause the session, click **Pause**.</span></span>  
  
     <span data-ttu-id="daeb7-127">Aparecerá un mensaje de confirmación. Si hace clic en **Sí**, se pausará la sesión y el botón cambiará a **Reanudar**.</span><span class="sxs-lookup"><span data-stu-id="daeb7-127">A prompt asks for confirmation; if you click **Yes**, the session is paused, and the button changes to **Resume**.</span></span>  
  
     <span data-ttu-id="daeb7-128">Para obtener más información sobre las repercusiones de pausar una sesión, vea [Pausar y reanudar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="daeb7-128">For more information about the impact of pausing a session, see [Pausing and Resuming Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="daeb7-129">Para reanudar la sesión, haga clic en **Reanudar**.</span><span class="sxs-lookup"><span data-stu-id="daeb7-129">To resume the session, click **Resume**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="daeb7-130">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="daeb7-130">Using Transact-SQL</span></span>  
  
#### <a name="to-pause-database-mirroring"></a><span data-ttu-id="daeb7-131">Para pausar la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="daeb7-131">To pause database mirroring</span></span>  
  
1.  <span data-ttu-id="daeb7-132">Conéctese al [!INCLUDE[ssDE](../../includes/ssde-md.md)] para cualquier asociado.</span><span class="sxs-lookup"><span data-stu-id="daeb7-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="daeb7-133">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="daeb7-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="daeb7-134">Escriba la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] siguiente:</span><span class="sxs-lookup"><span data-stu-id="daeb7-134">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
     <span data-ttu-id="daeb7-135">ALTER DATABASE *nombre_de_base_de_datos* SET PARTNER SUSPEND</span><span class="sxs-lookup"><span data-stu-id="daeb7-135">ALTER DATABASE *database_name* SET PARTNER SUSPEND</span></span>  
  
     <span data-ttu-id="daeb7-136">donde *nombre_de_base_de_datos* es la base de datos reflejada cuya sesión se quiere suspender.</span><span class="sxs-lookup"><span data-stu-id="daeb7-136">where *database_name* is the mirrored database whose session you want to you want to suspend.</span></span>  
  
     <span data-ttu-id="daeb7-137">En el ejemplo siguiente se pausa la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="daeb7-137">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER SUSPEND;  
    ```  
  
##### <a name="to-resume-database-mirroring"></a><span data-ttu-id="daeb7-138">Para reanudar la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="daeb7-138">To resume database mirroring</span></span>  
  
1.  <span data-ttu-id="daeb7-139">Conéctese al [!INCLUDE[ssDE](../../includes/ssde-md.md)] para cualquier asociado.</span><span class="sxs-lookup"><span data-stu-id="daeb7-139">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for either partner.</span></span>  
  
2.  <span data-ttu-id="daeb7-140">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="daeb7-140">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="daeb7-141">Escriba la instrucción Transact-SQL siguiente:</span><span class="sxs-lookup"><span data-stu-id="daeb7-141">Issue the following Transact-SQL statement:</span></span>  
  
     <span data-ttu-id="daeb7-142">ALTER DATABASE *nombre_de_base_de_datos* SET PARTNER RESUME</span><span class="sxs-lookup"><span data-stu-id="daeb7-142">ALTER DATABASE *database_name* SET PARTNER RESUME</span></span>  
  
     <span data-ttu-id="daeb7-143">donde *nombre_de_base_de_datos* es la base de datos reflejada cuya sesión se quiere reanudar.</span><span class="sxs-lookup"><span data-stu-id="daeb7-143">where *database_name* is the mirrored database whose session you want to resume.</span></span>  
  
     <span data-ttu-id="daeb7-144">En el ejemplo siguiente se pausa la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="daeb7-144">The following example pauses the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER RESUME;  
    ```  
  
##  <a name="follow-up-after-pausing-or-resuming-database-mirroring"></a><a name="FollowUp"></a><span data-ttu-id="daeb7-145">Seguimiento: después de pausar o reanudar la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="daeb7-145">Follow Up: After Pausing or Resuming Database Mirroring</span></span>  
  
-   <span data-ttu-id="daeb7-146">**Después de pausar la creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="daeb7-146">**After pausing database mirroring**</span></span>  
  
     <span data-ttu-id="daeb7-147">En la base de datos principal, tome precauciones para evitar que se llene el registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="daeb7-147">On the primary database, take precautions to avoid a full transaction log.</span></span> <span data-ttu-id="daeb7-148">Para más información, consulte [El registro de transacciones &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="daeb7-148">For more information, see [The Transaction Log &#40;SQL Server&#41;](../../relational-databases/logs/the-transaction-log-sql-server.md).</span></span>  
  
-   <span data-ttu-id="daeb7-149">**Después de reanudar la creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="daeb7-149">**After resuming database mirroring**</span></span>  
  
     <span data-ttu-id="daeb7-150">La reanudación del reflejo de una base de datos pone a la base de datos reflejada en el estado SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="daeb7-150">Resuming database mirroring places the mirror database in the SYNCHRONIZING state.</span></span> <span data-ttu-id="daeb7-151">Si el nivel de seguridad es FULL, el reflejo se pone al nivel de la principal y la base de datos reflejada toma el estado SYNCHRONIZED.</span><span class="sxs-lookup"><span data-stu-id="daeb7-151">If the safety level is FULL, the mirror catches up with the principal and the mirror database enters the SYNCHRONIZED state.</span></span> <span data-ttu-id="daeb7-152">En este punto, es posible una conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="daeb7-152">At this point, failover becomes possible.</span></span> <span data-ttu-id="daeb7-153">Si el testigo está presente y activo, es posible la conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="daeb7-153">If the witness is present and ON, automatic failover is possible.</span></span> <span data-ttu-id="daeb7-154">Si no hay un testigo, es posible la conmutación por error manual.</span><span class="sxs-lookup"><span data-stu-id="daeb7-154">In the absence of a witness, manual failover is possible.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="daeb7-155">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="daeb7-155">Related Tasks</span></span>  
  
-   [<span data-ttu-id="daeb7-156">Quitar la creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="daeb7-156">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="daeb7-157">Consulte también</span><span class="sxs-lookup"><span data-stu-id="daeb7-157">See Also</span></span>  
 [<span data-ttu-id="daeb7-158">Creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="daeb7-158">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
