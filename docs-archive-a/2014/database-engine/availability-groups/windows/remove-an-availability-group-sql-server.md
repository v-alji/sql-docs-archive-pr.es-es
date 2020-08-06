---
title: Quitar un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.deleteag.f1
helpviewer_keywords:
- Availability Groups [SQL Server], removing
- Availability Groups [SQL Server], dropping
ms.assetid: 4b7f7f62-43a3-49db-a72e-22d4d7c2ddbb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c17b7d5b362d8b4030d66ebf7ba0e425495410e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670593"
---
# <a name="remove-an-availability-group-sql-server"></a><span data-ttu-id="39b6d-102">Quitar un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="39b6d-102">Remove an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="39b6d-103">En este tema se describe cómo eliminar (quitar) un grupo de disponibilidad de AlwaysOn mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39b6d-103">This topic describes how to delete (drop) an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="39b6d-104">Si una instancia del servidor que hospeda una de las réplicas de disponibilidad está sin conexión al eliminar un grupo de disponibilidad, después de ponerse en línea, la instancia del servidor quitará la réplica de disponibilidad local.</span><span class="sxs-lookup"><span data-stu-id="39b6d-104">If a server instance that hosts one of the availability replicas is offline when you delete an availability group, after coming online, the server instance will drop the local availability replica.</span></span> <span data-ttu-id="39b6d-105">Quitar una disponibilidad del grupo elimina cualquier escucha de grupo de disponibilidad asociada.</span><span class="sxs-lookup"><span data-stu-id="39b6d-105">Dropping an availability group deletes any associated availability group listener.</span></span>  
  
 <span data-ttu-id="39b6d-106">Observe que, si es necesario, puede quitar un grupo de disponibilidad de cualquier nodo de clústeres de conmutación por error de Windows Server (WSFC) que posea las credenciales de seguridad correctas para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="39b6d-106">Note that, if necessary, you can drop an availability group from any Windows Server Failover Clustering (WSFC) node that possesses the correct security credentials for the availability group.</span></span> <span data-ttu-id="39b6d-107">Esto permite eliminar un grupo de disponibilidad cuando ninguna de sus réplicas de disponibilidad permanece.</span><span class="sxs-lookup"><span data-stu-id="39b6d-107">This enables you to delete an availability group when none of its availability replicas remain.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="39b6d-108">Si es posible, quite el grupo de disponibilidad solo mientras esté conectado a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="39b6d-108">If possible, remove the availability group only while connected to the server instance that hosts the primary replica.</span></span> <span data-ttu-id="39b6d-109">Cuando el grupo de disponibilidad se quita de la réplica principal, se permiten cambios en las bases de datos principales anteriores (sin protección de alta disponibilidad).</span><span class="sxs-lookup"><span data-stu-id="39b6d-109">When the availability group is dropped from the primary replica, changes are allowed in the former primary databases (without high availability protection).</span></span> <span data-ttu-id="39b6d-110">Al eliminar un grupo de disponibilidad de una réplica secundaria, la réplica principal queda en el estado RESTORING y no se permiten cambios en las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="39b6d-110">Deleting an availability group from a secondary replica leaves the primary replica in the RESTORING state, and changes are not allowed on the databases.</span></span>  
  
-   <span data-ttu-id="39b6d-111">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="39b6d-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="39b6d-112">Limitaciones y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="39b6d-112">Limitations and Recommendations</span></span>](#Restrictions)  
  
     [<span data-ttu-id="39b6d-113">Seguridad</span><span class="sxs-lookup"><span data-stu-id="39b6d-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="39b6d-114">**Para eliminar un grupo de disponibilidad, use:**</span><span class="sxs-lookup"><span data-stu-id="39b6d-114">**To delete an availability group, using:**</span></span>  
  
     [<span data-ttu-id="39b6d-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39b6d-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="39b6d-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39b6d-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="39b6d-117">PowerShell</span><span class="sxs-lookup"><span data-stu-id="39b6d-117">PowerShell</span></span>](#PowerShellProcedure)  
  
-   [<span data-ttu-id="39b6d-118">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="39b6d-118">Related Content</span></span>](#RelatedContent)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="39b6d-119">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="39b6d-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-recommendations"></a><a name="Restrictions"></a><span data-ttu-id="39b6d-120">Limitaciones y recomendaciones</span><span class="sxs-lookup"><span data-stu-id="39b6d-120">Limitations and Recommendations</span></span>  
  
-   <span data-ttu-id="39b6d-121">Cuando el grupo de disponibilidad está en línea, su eliminación de una réplica secundaria hace que la réplica principal pase al estado RESTORING.</span><span class="sxs-lookup"><span data-stu-id="39b6d-121">When the availability group is online, deleting it from a secondary replica causes the primary replica to transition to the RESTORING state.</span></span> <span data-ttu-id="39b6d-122">Por lo tanto, si es posible, quite el grupo de disponibilidad solo de la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="39b6d-122">Therefore, if possible, remove the availability group only from the server instance that hosts the primary replica.</span></span>  
  
-   <span data-ttu-id="39b6d-123">Si elimina un grupo de disponibilidad de un equipo que se ha quitado o desalojado del clúster de conmutación por error de WSFC, el grupo de disponibilidad se elimina solo localmente.</span><span class="sxs-lookup"><span data-stu-id="39b6d-123">If you delete an availability group from a computer that has been removed or evicted from the WSFC failover cluster, the availability group is only deleted locally.</span></span>  
  
-   <span data-ttu-id="39b6d-124">Evite quitar un grupo de disponibilidad cuando el clúster de Clústeres de conmutación por error de Windows Server (WSFC) no tiene quórum.</span><span class="sxs-lookup"><span data-stu-id="39b6d-124">Avoid dropping an availability group when the Windows Server Failover Clustering (WSFC) cluster has no quorum.</span></span> <span data-ttu-id="39b6d-125">Si debe quitar un grupo de disponibilidad mientras el clúster no tiene quórum, el grupo de disponibilidad de metadatos que se almacena en el clúster no se quita.</span><span class="sxs-lookup"><span data-stu-id="39b6d-125">If you must drop an availability group while the cluster lacks quorum, the metadata availability group that is stored in the cluster is not removed.</span></span> <span data-ttu-id="39b6d-126">Cuando el clúster recupere el quórum, necesitará volver a quitar el grupo de disponibilidad para quitarlo del clúster de WSFC.</span><span class="sxs-lookup"><span data-stu-id="39b6d-126">After the cluster regains quorum, you will need to drop the availability group again to remove it from the WSFC cluster.</span></span>  
  
-   <span data-ttu-id="39b6d-127">En una réplica secundaria, DROP AVAILABILITY GROUP solo se debe usar en caso de emergencia.</span><span class="sxs-lookup"><span data-stu-id="39b6d-127">On a secondary replica, DROP AVAILABILITY GROUP should only be used only for emergency purposes.</span></span> <span data-ttu-id="39b6d-128">Esto se debe a que al quitar un grupo de disponibilidad este se queda sin conexión.</span><span class="sxs-lookup"><span data-stu-id="39b6d-128">This is because dropping an availability group takes the availability group offline.</span></span> <span data-ttu-id="39b6d-129">Si quita el grupo de disponibilidad de una réplica secundaria, la réplica principal no puede determinar si el estado OFFLINE se debió a la pérdida del quórum, a una conmutación por error forzada o a un comando DROP AVAILABILITY GROUP.</span><span class="sxs-lookup"><span data-stu-id="39b6d-129">If you drop the availability group from a secondary replica, the primary replica cannot determine whether the OFFLINE state occurred because of quorum loss, a forced failover, or a DROP AVAILABILITY GROUP command.</span></span> <span data-ttu-id="39b6d-130">La réplica principal cambia al estado RESTORING para impedir una posible situación de división de cerebro.</span><span class="sxs-lookup"><span data-stu-id="39b6d-130">The primary replica transitions to the RESTORING state to prevent a possible split-brain situation.</span></span> <span data-ttu-id="39b6d-131">Para obtener más información, vea [How It Works: DROP AVAILABILITY GROUP Behaviors (Cómo funciona: comportamientos de DROP AVAILABILITY GROUP)](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (blog de los ingenieros de SQL Server de CSS).</span><span class="sxs-lookup"><span data-stu-id="39b6d-131">For more information, see [How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="39b6d-132">Seguridad</span><span class="sxs-lookup"><span data-stu-id="39b6d-132">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="39b6d-133">Permisos</span><span class="sxs-lookup"><span data-stu-id="39b6d-133">Permissions</span></span>  
 <span data-ttu-id="39b6d-134">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="39b6d-134">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span> <span data-ttu-id="39b6d-135">Para quitar un grupo de disponibilidad que no se encuentre hospedado en la instancia del servidor local se necesita el permiso CONTROL SERVER o el permiso CONTROL en ese grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="39b6d-135">To drop an availability group that is not hosted by the local server instance you need CONTROL SERVER permission or CONTROL permission on that Availability Group.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="39b6d-136">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="39b6d-136">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="39b6d-137">**Para eliminar un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="39b6d-137">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="39b6d-138">En el Explorador de objetos, conéctese a la instancia de servidor que hospeda la réplica principal, si es posible, o conéctese a otra instancia de servidor habilitada para los grupos de disponibilidad de AlwaysOn en un nodo de WSFC propietario de las credenciales de seguridad correctas para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="39b6d-138">In Object Explorer, connect to the server instance that hosts primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span> <span data-ttu-id="39b6d-139">Expanda el árbol de servidores.</span><span class="sxs-lookup"><span data-stu-id="39b6d-139">Expand the server tree.</span></span>  
  
2.  <span data-ttu-id="39b6d-140">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="39b6d-140">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="39b6d-141">Este paso depende de si desea eliminar varios grupos de disponibilidad o solo un grupo de disponibilidad, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="39b6d-141">This step depends on whether you want to delete multiple availability groups or only one availability group, as follows:</span></span>  
  
    -   <span data-ttu-id="39b6d-142">Para eliminar varios grupos de disponibilidad (cuyas réplicas principales están en la instancia de servidor conectada), use el panel **Detalles del Explorador de objetos** para ver y seleccionar todos los grupos de disponibilidad que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="39b6d-142">To delete multiple availability groups (whose primary replicas are on the connected server instance), use the **Object Explorer Details** pane to view and select all the availability groups that you want to delete.</span></span> <span data-ttu-id="39b6d-143">Para obtener más información, vea [Usar los detalles del Explorador de objetos para supervisar los grupos de disponibilidad &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="39b6d-143">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="39b6d-144">Para eliminar un solo grupo de disponibilidad, selecciónelo en el panel **Explorador de objetos** o **Detalles del Explorador de objetos** .</span><span class="sxs-lookup"><span data-stu-id="39b6d-144">To delete a single availability group, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
4.  <span data-ttu-id="39b6d-145">Haga clic con el botón derecho en el grupo o grupos de disponibilidad seleccionados y seleccione el comando **Eliminar** .</span><span class="sxs-lookup"><span data-stu-id="39b6d-145">Right-click the selected availability group or groups, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="39b6d-146">En el cuadro de diálogo **Quitar grupo de disponibilidad** , para eliminar todos los grupos de disponibilidad de la lista, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="39b6d-146">In the **Remove Availability Group** dialog box, to delete all the listed availability groups, click **OK**.</span></span> <span data-ttu-id="39b6d-147">Si no desea quitar todos los grupos de disponibilidad de la lista, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="39b6d-147">If you do not want to remove all the listed availability groups, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="39b6d-148">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="39b6d-148">Using Transact-SQL</span></span>  
 <span data-ttu-id="39b6d-149">**Para eliminar un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="39b6d-149">**To delete an availability group**</span></span>  
  
1.  <span data-ttu-id="39b6d-150">Conéctese a la instancia de servidor que hospeda la réplica principal, si es posible, o conéctese a otra instancia de servidor habilitada para los grupos de disponibilidad de AlwaysOn en un nodo de WSFC propietario de las credenciales de seguridad correctas para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="39b6d-150">Connect to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="39b6d-151">Use la instrucción [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) del siguiente modo</span><span class="sxs-lookup"><span data-stu-id="39b6d-151">Use the [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql) statement, as follows</span></span>  
  
     <span data-ttu-id="39b6d-152">DROP AVAILABILITY GROUP *group_name*</span><span class="sxs-lookup"><span data-stu-id="39b6d-152">DROP AVAILABILITY GROUP *group_name*</span></span>  
  
     <span data-ttu-id="39b6d-153">donde *group_name* es el nombre del grupo de disponibilidad que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="39b6d-153">where *group_name* is the name of the availability group to be dropped.</span></span>  
  
     <span data-ttu-id="39b6d-154">En el ejemplo siguiente se elimina el grupo de disponibilidad `MyAG` .</span><span class="sxs-lookup"><span data-stu-id="39b6d-154">The following example deletes the `MyAG` availability group.</span></span>  
  
    ```sql
    DROP AVAILABILITY GROUP MyAG;  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="39b6d-155">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="39b6d-155">Using PowerShell</span></span>  
 <span data-ttu-id="39b6d-156">**Para eliminar un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="39b6d-156">**To delete an availability group**</span></span>  
  
 <span data-ttu-id="39b6d-157">En el proveedor de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell:</span><span class="sxs-lookup"><span data-stu-id="39b6d-157">In the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell provider:</span></span>  
  
1.  <span data-ttu-id="39b6d-158">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica principal, si es posible, o conéctese a otra instancia de servidor habilitada para los grupos de disponibilidad de AlwaysOn en un nodo de WSFC propietario de las credenciales de seguridad correctas para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="39b6d-158">Change directory (`cd`) to the server instance that hosts the primary replica, if possible, or connect to another server instance that is enabled for AlwaysOn Availability Groups on a WSFC node that possess the correct security credentials for the availability group.</span></span>  
  
2.  <span data-ttu-id="39b6d-159">Use el cmdlet **Remove-SqlAvailabilityGroup** .</span><span class="sxs-lookup"><span data-stu-id="39b6d-159">Use the **Remove-SqlAvailabilityGroup** cmdlet.</span></span>  
  
     <span data-ttu-id="39b6d-160">Por ejemplo, el comando siguiente quita el grupo de disponibilidad denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="39b6d-160">For example, the following command removes the availability group named `MyAg`.</span></span> <span data-ttu-id="39b6d-161">Este comando se puede ejecutar en cualquier instancia de servidor que hospede una réplica de disponibilidad para el grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="39b6d-161">This command can be executed on any server instance that hosts an availability replica for the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="39b6d-162">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39b6d-162">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="39b6d-163">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="39b6d-163">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="39b6d-164">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="39b6d-164">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="39b6d-165">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="39b6d-165">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="39b6d-166">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="39b6d-166">Related Content</span></span>  
  
-   <span data-ttu-id="39b6d-167">[How It Works: DROP AVAILABILITY GROUP Behaviors (Cómo funciona: comportamientos de DROP AVAILABILITY GROUP)](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (blog de los ingenieros de SQL Server de CSS)</span><span class="sxs-lookup"><span data-stu-id="39b6d-167">[How It Works: DROP AVAILABILITY GROUP Behaviors](https://blogs.msdn.com/b/psssql/archive/2012/06/13/how-it-works-drop-availability-group-behaviors.aspx) (CSS SQL Server Engineers blog)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39b6d-168">Consulte también</span><span class="sxs-lookup"><span data-stu-id="39b6d-168">See Also</span></span>  
 <span data-ttu-id="39b6d-169">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="39b6d-169">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="39b6d-170">Creación y configuración de grupos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="39b6d-170">Creation and Configuration of Availability Groups &#40;SQL Server&#41;</span></span>](creation-and-configuration-of-availability-groups-sql-server.md)  
