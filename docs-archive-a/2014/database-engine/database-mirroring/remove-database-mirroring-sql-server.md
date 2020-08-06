---
title: Quitar la creación de reflejo de la base de datos (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], removing
- removing database mirroring [SQL Server]
ms.assetid: bbc4d7f7-3bc7-40d6-a822-af195fe7f8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19c1d0449fa1c7434aeaf9c51e3b2dc7bc6b68c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746495"
---
# <a name="remove-database-mirroring-sql-server"></a><span data-ttu-id="e5d07-102">Quitar la creación de reflejo de la base de datos (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e5d07-102">Remove Database Mirroring (SQL Server)</span></span>
  <span data-ttu-id="e5d07-103">En este tema se describe cómo quitar la creación de reflejo de una base de datos en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5d07-103">This topic describes how to remove database mirroring from a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  <span data-ttu-id="e5d07-104">El propietario de la base de datos puede detener manualmente en cualquier momento una sesión de creación de reflejo de la base de datos quitando el reflejo de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d07-104">At any time, the database owner can manually stop a database mirroring session by removing mirroring from the database.</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e5d07-105">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="e5d07-105">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e5d07-106">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e5d07-106">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="e5d07-107">Permisos</span><span class="sxs-lookup"><span data-stu-id="e5d07-107">Permissions</span></span>  
 <span data-ttu-id="e5d07-108">Requiere el permiso ALTER en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d07-108">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="e5d07-109">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e5d07-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="e5d07-110">Para quitar la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="e5d07-110">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="e5d07-111">Durante una sesión de creación de reflejo de la base de datos, conéctese a la instancia de servidor principal y, en el Explorador de objetos, haga clic en el nombre del servidor para expandir el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="e5d07-111">During a database mirroring session, connect to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="e5d07-112">Expanda **Bases de datos**y seleccione la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d07-112">Expand **Databases**, and select the database.</span></span>  
  
3.  <span data-ttu-id="e5d07-113">Haga clic con el botón derecho en la base de datos, seleccione **Tareas**y, luego, haga clic en **Reflejado**.</span><span class="sxs-lookup"><span data-stu-id="e5d07-113">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="e5d07-114">Así se abre la página **Creación de reflejo** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="e5d07-114">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="e5d07-115">En el panel **Seleccionar una página** , haga clic en **Creación de reflejos**.</span><span class="sxs-lookup"><span data-stu-id="e5d07-115">In the **Select a Page** pane, click **Mirroring**.</span></span>  
  
5.  <span data-ttu-id="e5d07-116">Para quitar la creación de reflejo, haga clic en **Quitar creación de reflejo**.</span><span class="sxs-lookup"><span data-stu-id="e5d07-116">To remove mirroring, click **Remove Mirroring**.</span></span> <span data-ttu-id="e5d07-117">Aparecerá un mensaje de confirmación.</span><span class="sxs-lookup"><span data-stu-id="e5d07-117">A prompt asks for confirmation.</span></span> <span data-ttu-id="e5d07-118">Si hace clic en **Sí**, se detendrá la sesión y la creación de reflejo se quitará de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e5d07-118">If you click **Yes**, the session is stopped and mirroring is removed from the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="e5d07-119">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e5d07-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="e5d07-120">Para quitar la creación de reflejo de la base de datos, use las **Propiedades de la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="e5d07-120">To remove database mirroring, use the **Database Properties**.</span></span> <span data-ttu-id="e5d07-121">Use la página **Creación de reflejo** del cuadro de diálogo **Propiedades de la base de datos** .</span><span class="sxs-lookup"><span data-stu-id="e5d07-121">use the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
#### <a name="to-remove-database-mirroring"></a><span data-ttu-id="e5d07-122">Para quitar la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="e5d07-122">To remove database mirroring</span></span>  
  
1.  <span data-ttu-id="e5d07-123">Conéctese al [!INCLUDE[ssDE](../../includes/ssde-md.md)] de algún asociado de creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="e5d07-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] of either mirroring partner.</span></span>  
  
2.  <span data-ttu-id="e5d07-124">En la barra Estándar, haga clic en **Nueva consulta**.</span><span class="sxs-lookup"><span data-stu-id="e5d07-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="e5d07-125">Escriba la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5d07-125">Issue the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    ALTER DATABASE database_name SET PARTNER OFF  
    ```  
  
     <span data-ttu-id="e5d07-126">Donde *database_name* es la base de datos reflejada cuya sesión quiere quitar.</span><span class="sxs-lookup"><span data-stu-id="e5d07-126">where *database_name* is the mirrored database whose session you want to remove.</span></span>  
  
     <span data-ttu-id="e5d07-127">En el ejemplo siguiente se quita la creación de reflejo de la base de datos de ejemplo [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e5d07-127">The following example removes database mirroring from the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks2012 SET PARTNER OFF;  
    ```  
  
##  <a name="follow-up-removing-database-mirroring"></a><a name="FollowUp"></a> <span data-ttu-id="e5d07-128">Seguimiento: Quitar la creación de reflejo de la base de datos</span><span class="sxs-lookup"><span data-stu-id="e5d07-128">Follow Up: Removing Database Mirroring</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5d07-129">Para obtener más información sobre las repercusiones de quitar la creación de reflejo, vea [Quitar la creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e5d07-129">For information about the impact of removing mirroring, see [Removing Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="e5d07-130">**Si piensa reiniciar la creación de reflejo de la base de datos**</span><span class="sxs-lookup"><span data-stu-id="e5d07-130">**If you intend to restart mirroring on the database**</span></span>  
  
     <span data-ttu-id="e5d07-131">Debe aplicar a la base de datos reflejada las copias de seguridad de registros realizadas en la base de datos principal después de quitar la creación de reflejo antes de poder reiniciar la creación de reflejo.</span><span class="sxs-lookup"><span data-stu-id="e5d07-131">Any log backups taken on the principal database after mirroring was removed must all be applied to the mirror database before you can restart mirroring.</span></span>  
  
-   <span data-ttu-id="e5d07-132">**Si no piensa reiniciar la creación de reflejo**</span><span class="sxs-lookup"><span data-stu-id="e5d07-132">**If you do not intent to restart mirroring**</span></span>  
  
     <span data-ttu-id="e5d07-133">Opcionalmente, puede recuperar la base de datos reflejada anterior.</span><span class="sxs-lookup"><span data-stu-id="e5d07-133">Optionally, you can recover the former mirror database.</span></span> <span data-ttu-id="e5d07-134">En la instancia de servidor que era el servidor reflejado, puede usar la instrucción [!INCLUDE[tsql](../../includes/tsql-md.md)] siguiente:</span><span class="sxs-lookup"><span data-stu-id="e5d07-134">On the server instance that was the mirror server, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    RESTORE DATABASE database_name WITH RECOVERY;  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e5d07-135">Si recupera esta base de datos, habrá dos bases de datos divergentes en línea con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="e5d07-135">If you recover this database, two divergent databases with the same name are online.</span></span> <span data-ttu-id="e5d07-136">Por tanto, debe garantizar que los clientes solo puedan acceder a una de ellas, generalmente la base de datos principal más reciente.</span><span class="sxs-lookup"><span data-stu-id="e5d07-136">Therefore, you need to ensure that clients can access only one of them-typically the most recent principal database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e5d07-137">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="e5d07-137">Related Tasks</span></span>  
  
-   [<span data-ttu-id="e5d07-138">Pausar o reanudar una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5d07-138">Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;</span></span>](pause-or-resume-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="e5d07-139">Quitar el testigo de una sesión de creación de reflejo de la base de datos &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e5d07-139">Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;</span></span>](remove-the-witness-from-a-database-mirroring-session-sql-server.md)  
  
-   [<span data-ttu-id="e5d07-140">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="e5d07-140">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="e5d07-141">Establecer una sesión de creación de reflejo de la base de datos mediante la autenticación de Windows &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5d07-141">Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;</span></span>](database-mirroring-establish-session-windows-authentication.md)  
  
-   [<span data-ttu-id="e5d07-142">Ejemplo: Configurar la creación de reflejo de la base de datos con certificados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5d07-142">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="e5d07-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5d07-143">See Also</span></span>  
 <span data-ttu-id="e5d07-144">[Creación de reflejo de la base de datos &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e5d07-144">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="e5d07-145">[Configurar la creación de reflejo de la base de datos &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="e5d07-145">[Setting Up Database Mirroring &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="e5d07-146">Grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e5d07-146">AlwaysOn Availability Groups (SQL Server)</span></span>](../availability-groups/windows/always-on-availability-groups-sql-server.md)  
  
  
