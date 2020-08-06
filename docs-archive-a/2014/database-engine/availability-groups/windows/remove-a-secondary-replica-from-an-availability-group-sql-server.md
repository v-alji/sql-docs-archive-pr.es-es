---
title: Quitar una réplica secundaria de un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removesecondaryar.f1
helpviewer_keywords:
- Availability Groups [SQL Server], availability replicas
- Availability Groups [SQL Server], configuring
ms.assetid: 35ddc8b6-3e7c-4417-9a0a-d4987a09ddf7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e3f2b35ec9cf27f2f7b23714a41665f2709837a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670595"
---
# <a name="remove-a-secondary-replica-from-an-availability-group-sql-server"></a><span data-ttu-id="ddbfd-102">Quitar una réplica secundaria de un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ddbfd-102">Remove a Secondary Replica from an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="ddbfd-103">En este tema se describe cómo quitar una réplica secundaria de un grupo de disponibilidad AlwaysOn utilizando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddbfd-103">This topic describes how to remove a secondary replica from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="ddbfd-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="ddbfd-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ddbfd-105">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ddbfd-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="ddbfd-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ddbfd-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="ddbfd-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ddbfd-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ddbfd-108">**Para quitar una réplica secundaria, utilizando:**</span><span class="sxs-lookup"><span data-stu-id="ddbfd-108">**To remove a secondary replica, using:**</span></span>  
  
     [<span data-ttu-id="ddbfd-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ddbfd-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ddbfd-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ddbfd-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="ddbfd-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddbfd-111">PowerShell</span></span>](#PowerShellProcedure)  
  
-   <span data-ttu-id="ddbfd-112">**Seguimiento:**  [después de quitar una réplica secundaria](#PostBestPractices)</span><span class="sxs-lookup"><span data-stu-id="ddbfd-112">**Follow Up:**  [After Removing a Secondary Replica](#PostBestPractices)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ddbfd-113">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="ddbfd-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="ddbfd-114">Limitaciones y restricciones</span><span class="sxs-lookup"><span data-stu-id="ddbfd-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="ddbfd-115">Esta tarea solo se admite en la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-115">This task is supported only on the primary replica.</span></span>  
  
-   <span data-ttu-id="ddbfd-116">Solo se puede quitar una réplica secundaria de un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-116">Only a secondary replica can be removed from an availability group.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ddbfd-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ddbfd-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="ddbfd-118">Debe estar conectado a la instancia del servidor que hospeda la réplica principal del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-118">You must be connected to the server instance that hosts the primary replica of the availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ddbfd-119">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ddbfd-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ddbfd-120">Permisos</span><span class="sxs-lookup"><span data-stu-id="ddbfd-120">Permissions</span></span>  
 <span data-ttu-id="ddbfd-121">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-121">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ddbfd-122">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ddbfd-122">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ddbfd-123">**Para quitar una réplica secundaria**</span><span class="sxs-lookup"><span data-stu-id="ddbfd-123">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="ddbfd-124">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-124">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ddbfd-125">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="ddbfd-125">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="ddbfd-126">Seleccione el grupo de disponibilidad y expanda el nodo **Réplicas de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="ddbfd-126">Select the availability group, and expand the **Availability Replicas** node.</span></span>  
  
4.  <span data-ttu-id="ddbfd-127">Este paso depende de si desea quitar varias réplicas o solo una, del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ddbfd-127">This step depends on whether you want to remove multiple replicas or only one replica, as follows:</span></span>  
  
    -   <span data-ttu-id="ddbfd-128">Para quitar varias réplicas, use el panel **Detalles del Explorador de objetos** para ver y seleccionar todas las réplicas que desea quitar.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-128">To remove multiple replicas, use the **Object Explorer Details** pane to view and select all the replicas that you want to remove.</span></span> <span data-ttu-id="ddbfd-129">Para obtener más información, vea [Usar los detalles del Explorador de objetos para supervisar los grupos de disponibilidad &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ddbfd-129">For more information, see [Use the Object Explorer Details to Monitor Availability Groups &#40;SQL Server Management Studio&#41;](use-object-explorer-details-to-monitor-availability-groups.md).</span></span>  
  
    -   <span data-ttu-id="ddbfd-130">Para quitar una sola réplica, selecciónela en el panel **Explorador de objetos** o el panel **Detalles del Explorador de objetos** .</span><span class="sxs-lookup"><span data-stu-id="ddbfd-130">To remove a single replica, select it in either the **Object Explorer** pane or the **Object Explorer Details** pane.</span></span>  
  
5.  <span data-ttu-id="ddbfd-131">Haga clic con el botón derecho en la réplica o réplicas secundarias seleccionadas y seleccione **Quitar del grupo de disponibilidad** en el menú de comandos.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-131">Right-click the selected secondary replica or replicas, and select **Remove from Availability Group** in the command menu.</span></span>  
  
6.  <span data-ttu-id="ddbfd-132">En el cuadro de diálogo **Quitar réplicas secundarias del grupo de disponibilidad** , para quitar todas las réplicas secundarias enumeradas, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-132">In the **Remove Secondary Replicas from Availability Group** dialog box, to remove all the listed secondary replicas, click **OK**.</span></span> <span data-ttu-id="ddbfd-133">Si no desea quitar todas las réplicas enumeradas, haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-133">If you do not want to remove all the listed replicas, click **Cancel**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ddbfd-134">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ddbfd-134">Using Transact-SQL</span></span>  
 <span data-ttu-id="ddbfd-135">**Para quitar una réplica secundaria**</span><span class="sxs-lookup"><span data-stu-id="ddbfd-135">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="ddbfd-136">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-136">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="ddbfd-137">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="ddbfd-137">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="ddbfd-138">ALTER AVAILABILITY GROUP *group_name* REMOVE REPLICA ON '*instance_name*' [,...*n*]</span><span class="sxs-lookup"><span data-stu-id="ddbfd-138">ALTER AVAILABILITY GROUP *group_name* REMOVE REPLICA ON '*instance_name*' [,...*n*]</span></span>  
  
     <span data-ttu-id="ddbfd-139">donde *group_name* es el nombre del grupo de disponibilidad e *instance_name* es la instancia del servidor donde se encuentra la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-139">where *group_name* is the name of the availability group and *instance_name* is the server instance where the secondary replica is located.</span></span>  
  
     <span data-ttu-id="ddbfd-140">En el ejemplo siguiente se quita una réplica secundaria del grupo de disponibilidad *MyAG* .</span><span class="sxs-lookup"><span data-stu-id="ddbfd-140">The following example removes a secondary replica from the *MyAG* availability group.</span></span> <span data-ttu-id="ddbfd-141">La réplica secundaria de destino se encuentra en una instancia del servidor denominada *HADR_INSTANCE* en un equipo denominado *COMPUTER02*.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-141">The target secondary replica is located on a server instance named *HADR_INSTANCE* on a computer named *COMPUTER02*.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP MyAG REMOVE REPLICA ON 'COMPUTER02\HADR_INSTANCE';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="ddbfd-142">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="ddbfd-142">Using PowerShell</span></span>  
 <span data-ttu-id="ddbfd-143">**Para quitar una réplica secundaria**</span><span class="sxs-lookup"><span data-stu-id="ddbfd-143">**To remove a secondary replica**</span></span>  
  
1.  <span data-ttu-id="ddbfd-144">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-144">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="ddbfd-145">Use el cmdlet **Remove-SqlAvailabilityReplica** .</span><span class="sxs-lookup"><span data-stu-id="ddbfd-145">Use the **Remove-SqlAvailabilityReplica** cmdlet.</span></span>  
  
     <span data-ttu-id="ddbfd-146">Por ejemplo, el comando siguiente quita la réplica de disponibilidad en el servidor `MyReplica` del grupo de disponibilidad denominado `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-146">For example, the following command removes the availability replica on the server `MyReplica` from the availability group named `MyAg`.</span></span>  <span data-ttu-id="ddbfd-147">Este comando debe ejecutarse en la instancia del servidor que hospeda la réplica principal del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-147">This command must be run on the server instance that hosts the primary replica of the availability group.</span></span>  
  
    ```powershell
    Remove-SqlAvailabilityReplica -Path SQLSERVER:\SQL\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="ddbfd-148">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-148">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="ddbfd-149">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ddbfd-149">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="ddbfd-150">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="ddbfd-150">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="ddbfd-151">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="ddbfd-151">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="follow-up-after-removing-a-secondary-replica"></a><a name="PostBestPractices"></a> <span data-ttu-id="ddbfd-152">Seguimiento: después de quitar una réplica secundaria</span><span class="sxs-lookup"><span data-stu-id="ddbfd-152">Follow Up: After Removing a Secondary Replica</span></span>  
 <span data-ttu-id="ddbfd-153">Si especifica una réplica que no está actualmente disponible, cuando la réplica se ponga en línea, detectará que se ha quitado.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-153">If you specify a replica that is currently unavailable, when the replica comes online, it will discover that it has been removed.</span></span>  
  
 <span data-ttu-id="ddbfd-154">Quitar una réplica produce la detención de la recepción de datos</span><span class="sxs-lookup"><span data-stu-id="ddbfd-154">Removing a replica causes it to stop receiving data.</span></span> <span data-ttu-id="ddbfd-155">Después de que una réplica secundaria confirma que se ha quitado del almacén global, la réplica quita la configuración del grupo disponibilidad de las bases de datos, que permanecen en la instancia del servidor local en estado RECOVERING.</span><span class="sxs-lookup"><span data-stu-id="ddbfd-155">After a secondary replica confirms that it has been removed from the global store, the replica removes the availability group settings from its databases, which remain on the local server instance in the RECOVERING state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbfd-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddbfd-156">See Also</span></span>  
 <span data-ttu-id="ddbfd-157">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ddbfd-157">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="ddbfd-158">[Agregar una réplica secundaria a un grupo de disponibilidad &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ddbfd-158">[Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;](add-a-secondary-replica-to-an-availability-group-sql-server.md) </span></span>  
 [<span data-ttu-id="ddbfd-159">Quitar un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ddbfd-159">Remove an Availability Group &#40;SQL Server&#41;</span></span>](remove-an-availability-group-sql-server.md)  
