---
title: Combinar una base de datos secundaria con un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.joindbs.f1
helpviewer_keywords:
- secondary databases [SQL Server], in availability group
- secondary databases [SQL Server]
- Availability Groups [SQL Server], joining
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], databases
ms.assetid: fd7efe79-c1f9-497d-bfe7-b2a2b2321cf5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b0d79325bcde33d13688003de079a42a9601cc41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87672263"
---
# <a name="join-a-secondary-database-to-an-availability-group-sql-server"></a><span data-ttu-id="4c7f4-102">Combinar una base de datos secundaria con un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="4c7f4-102">Join a Secondary Database to an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="4c7f4-103">En este tema se explica cómo combinar una base de datos secundaria con un grupo de disponibilidad de AlwaysOn mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c7f4-103">This topic explains how to join a secondary database to an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="4c7f4-104">Después de preparar una base de datos secundaria para una réplica de disponibilidad secundaria, debe combinar la base de datos con el grupo de disponibilidad lo antes posible.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-104">After you prepare a secondary database for a secondary replica, you need to join the database to the availability group as soon as possible.</span></span> <span data-ttu-id="4c7f4-105">Se iniciará el movimiento de datos de la base de datos principal correspondiente a la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-105">This will start data movement from the corresponding primary database to the secondary database.</span></span>  
  
-   <span data-ttu-id="4c7f4-106">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="4c7f4-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4c7f4-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4c7f4-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="4c7f4-108">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4c7f4-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4c7f4-109">**Para preparar una base de datos secundaria, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="4c7f4-109">**To prepare a secondary database, using:**</span></span>  
  
     [<span data-ttu-id="4c7f4-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c7f4-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4c7f4-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c7f4-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="4c7f4-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c7f4-112">PowerShell</span></span>](#PowerShellProcedure)  
  
> [!NOTE]  
>  <span data-ttu-id="4c7f4-113">Para obtener información acerca de lo que sucede después de que una base de datos secundaria se une al grupo, consulte [información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c7f4-113">For information about what happens after a secondary database joins the group, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4c7f4-114">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="4c7f4-114">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4c7f4-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4c7f4-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="4c7f4-116">Debe estar conectado a la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-116">You must be connected to the server instance that hosts the secondary replica.</span></span>  
  
-   <span data-ttu-id="4c7f4-117">La réplica secundaria ya debe estar unida al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-117">The secondary replica must already be joined to the availability group.</span></span> <span data-ttu-id="4c7f4-118">Para obtener más información, vea [Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c7f4-118">For more information, see [Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;](join-a-secondary-replica-to-an-availability-group-sql-server.md).</span></span>  
  
-   <span data-ttu-id="4c7f4-119">La base de datos secundaria debe haberse preparado recientemente.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-119">The secondary database must have been prepared recently.</span></span> <span data-ttu-id="4c7f4-120">Para obtener más información, vea [Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4c7f4-120">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4c7f4-121">Seguridad</span><span class="sxs-lookup"><span data-stu-id="4c7f4-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4c7f4-122">Permisos</span><span class="sxs-lookup"><span data-stu-id="4c7f4-122">Permissions</span></span>  
 <span data-ttu-id="4c7f4-123">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-123">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4c7f4-124">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4c7f4-124">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="4c7f4-125">**Para combinar una base de datos secundaria con un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="4c7f4-125">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="4c7f4-126">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica secundaria y expanda el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-126">In Object Explorer, connect to the server instance that hosts the secondary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="4c7f4-127">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="4c7f4-127">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="4c7f4-128">Expanda el grupo de disponibilidad que desea cambiar y expanda el nodo **Bases de datos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="4c7f4-128">Expand the availability group that you want to change, and expand the **Availability Databases** node.</span></span>  
  
4.  <span data-ttu-id="4c7f4-129">Haga clic con el botón derecho en la base de datos y haga clic en **Combinar con grupo de disponibilidad**.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-129">Right-click the database, and click **Join to Availability Group**.</span></span>  
  
5.  <span data-ttu-id="4c7f4-130">Se abrirá el cuadro de diálogo **Combinar bases de datos con el grupo de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="4c7f4-130">This opens the **Join Databases to Availability Group** dialog box.</span></span> <span data-ttu-id="4c7f4-131">Compruebe el nombre del grupo de disponibilidad, que se muestra en la barra de título, y el nombre o nombres de base de datos mostrados en la cuadrícula, y haga clic en **Aceptar**o en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-131">Verify the availability group name, which is displayed on the title bar, and database name or names displayed in the grid, and click **OK**, or click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4c7f4-132">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4c7f4-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="4c7f4-133">**Para combinar una base de datos secundaria con un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="4c7f4-133">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="4c7f4-134">Conéctese a la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-134">Connect to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="4c7f4-135">Utilice la cláusula [SET HADR de la instrucción ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="4c7f4-135">Use the [SET HADR clause of the ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql-set-hadr) statement, as follows:</span></span>  
  
     <span data-ttu-id="4c7f4-136">ALTER DATABASE *nombre_baseDeDatos* SET HADR AVAILABILITY GROUP = *nombre_grupo*</span><span class="sxs-lookup"><span data-stu-id="4c7f4-136">ALTER DATABASE *database_name* SET HADR AVAILABILITY GROUP = *group_name*</span></span>  
  
     <span data-ttu-id="4c7f4-137">donde *nombre_BaseDeDatos* es el nombre de la base de datos que se va a unir y *nombre_grupo* es el nombre del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-137">where *database_name* is the name of a database to be joined and *group_name* is the name of the availability group.</span></span>  
  
     <span data-ttu-id="4c7f4-138">En el ejemplo siguiente se une la base de datos secundaria `Db1` a la réplica secundaria local del grupo de disponibilidad `MyAG`.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-138">The following example joins the secondary database, `Db1`, to the local secondary replica of the `MyAG` availability group.</span></span>  
  
    ```sql
    ALTER DATABASE Db1 SET HADR AVAILABILITY GROUP = MyAG;  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c7f4-139">Para ver esta instrucción [!INCLUDE[tsql](../../../includes/tsql-md.md)] usada en contexto, vea [Crear un grupo de disponibilidad &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="4c7f4-139">To see this [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement used in context, see [Create an Availability Group &#40;Transact-SQL&#41;](create-an-availability-group-transact-sql.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="4c7f4-140">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c7f4-140">Using PowerShell</span></span>  
 <span data-ttu-id="4c7f4-141">**Para combinar una base de datos secundaria con un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="4c7f4-141">**To join a secondary database to an availability group**</span></span>  
  
1.  <span data-ttu-id="4c7f4-142">Cambie el directorio (`cd`) a la instancia del servidor que hospeda la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-142">Change directory (`cd`) to the server instance that hosts the secondary replica.</span></span>  
  
2.  <span data-ttu-id="4c7f4-143">Utilice el cmdlet `Add-SqlAvailabilityDatabase` para unir una o más bases de datos secundarias al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-143">Use the `Add-SqlAvailabilityDatabase` cmdlet to join one or more secondary databases to the availability group.</span></span>  
  
     <span data-ttu-id="4c7f4-144">Por ejemplo, el comando siguiente une una base de datos secundaria `Db1`al grupo de disponibilidad `MyAG` en una de las instancias de servidor que hospeda una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-144">For example, the following command joins a secondary database, `Db1`, to the availability group `MyAG` on one of the server instances that hosts a secondary replica.</span></span>  
  
    ```powershell
    Add-SqlAvailabilityDatabase -Path SQLSERVER:\SQL\SecondaryServer\InstanceName\AvailabilityGroups\MyAG -Database "Db1"  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="4c7f4-145">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c7f4-145">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="4c7f4-146">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="4c7f4-146">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="4c7f4-147">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4c7f4-147">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="4c7f4-148">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="4c7f4-148">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="4c7f4-149">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="4c7f4-149">Related Tasks</span></span>  
  
-   [<span data-ttu-id="4c7f4-150">Combinar una réplica secundaria con un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c7f4-150">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="4c7f4-151">Preparar manualmente una base de datos secundaria para un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="4c7f4-151">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c7f4-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c7f4-152">See Also</span></span>  
 <span data-ttu-id="4c7f4-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="4c7f4-153">[ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-availability-group-transact-sql) </span></span>  
 <span data-ttu-id="4c7f4-154">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="4c7f4-154">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="4c7f4-155">Solucionar problemas de Grupos de disponibilidad AlwaysOn &#40;de configuración de SQL Server&#41;eliminado</span><span class="sxs-lookup"><span data-stu-id="4c7f4-155">Troubleshoot AlwaysOn Availability Groups Configuration &#40;SQL Server&#41;deleted</span></span>](troubleshoot-always-on-availability-groups-configuration-sql-server.md)  
