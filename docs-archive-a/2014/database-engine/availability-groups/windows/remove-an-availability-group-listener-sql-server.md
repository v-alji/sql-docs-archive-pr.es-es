---
title: Quitar un agente de escucha del grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygroup.removeaglistener.default.f1
helpviewer_keywords:
- Availability Groups [SQL Server], listeners
ms.assetid: fd9bba9a-d29f-4c23-8ecd-aaa049ed5f1b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 057b9c137cb4d8bbbdd03be61df600f7e59b264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670599"
---
# <a name="remove-an-availability-group-listener-sql-server"></a><span data-ttu-id="89cbf-102">Quitar un agente de escucha del grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="89cbf-102">Remove an Availability Group Listener (SQL Server)</span></span>
  <span data-ttu-id="89cbf-103">En este tema se describe cómo se quita un agente de escucha de un grupo de disponibilidad AlwaysOn utilizando [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89cbf-103">This topic describes how to remove an availability group listener from an AlwaysOn availability group by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
-   <span data-ttu-id="89cbf-104">**Antes de empezar:**</span><span class="sxs-lookup"><span data-stu-id="89cbf-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="89cbf-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="89cbf-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="89cbf-106">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="89cbf-106">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="89cbf-107">Seguridad</span><span class="sxs-lookup"><span data-stu-id="89cbf-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="89cbf-108">**Para quitar un agente de escucha con:**</span><span class="sxs-lookup"><span data-stu-id="89cbf-108">**To remove a listener, using:**</span></span>  
  
     [<span data-ttu-id="89cbf-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89cbf-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="89cbf-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89cbf-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
     [<span data-ttu-id="89cbf-111">PowerShell</span><span class="sxs-lookup"><span data-stu-id="89cbf-111">PowerShell</span></span>](#PowerShellProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="89cbf-112">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="89cbf-112">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="89cbf-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="89cbf-113">Prerequisites</span></span>  
  
-   <span data-ttu-id="89cbf-114">Debe estar conectado a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="89cbf-114">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="89cbf-115">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="89cbf-115">Recommendations</span></span>  
 <span data-ttu-id="89cbf-116">Antes de eliminar un agente de escucha del grupo de disponibilidad, se recomienda asegurarse de que no se está utilizando ninguna aplicación.</span><span class="sxs-lookup"><span data-stu-id="89cbf-116">Before you delete an availability group listener, we recommend that you ensure that no applications are using it.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="89cbf-117">Seguridad</span><span class="sxs-lookup"><span data-stu-id="89cbf-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="89cbf-118">Permisos</span><span class="sxs-lookup"><span data-stu-id="89cbf-118">Permissions</span></span>  
 <span data-ttu-id="89cbf-119">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="89cbf-119">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="89cbf-120">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="89cbf-120">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="89cbf-121">**Para quitar un agente de escucha del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="89cbf-121">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="89cbf-122">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal y haga clic en el nombre del servidor para expandir el árbol.</span><span class="sxs-lookup"><span data-stu-id="89cbf-122">In Object Explorer, connect to the server instance that hosts the primary replica, and click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="89cbf-123">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="89cbf-123">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="89cbf-124">Expanda el nodo del grupo de disponibilidad y expanda el nodo **Agentes de escucha de grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="89cbf-124">Expand the node of the availability group, and expand the **Availability Groups Listeners** node.</span></span>  
  
4.  <span data-ttu-id="89cbf-125">Haga clic con el botón derecho en el agente de escucha que quiere quitar y seleccione el comando **Eliminar** .</span><span class="sxs-lookup"><span data-stu-id="89cbf-125">Right-click the listener to be removed, and select the **Delete** command.</span></span>  
  
5.  <span data-ttu-id="89cbf-126">Se abrirá el cuadro de diálogo de **Quitar agente de escucha del grupo de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="89cbf-126">This opens the **Remove Listener from Availability Group** dialog box.</span></span> <span data-ttu-id="89cbf-127">Para obtener más información, vea [Quitar agente de escucha del grupo de disponibilidad](#AgListenerPropertiesDialog), más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="89cbf-127">For more information, see [Remove Listener from Availability Group](#AgListenerPropertiesDialog), later in this topic.</span></span>  
  
###  <a name="remove-listener-from-availability-group-dialog-box"></a><a name="AgListenerPropertiesDialog"></a><span data-ttu-id="89cbf-128">Quitar el agente de escucha del grupo de disponibilidad (cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="89cbf-128">Remove Listener from Availability Group (Dialog Box)</span></span>  
 <span data-ttu-id="89cbf-129">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="89cbf-129">**Name**</span></span>  
 <span data-ttu-id="89cbf-130">Nombre del agente de escucha que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="89cbf-130">The name of the listener to be removed.</span></span>  
  
 <span data-ttu-id="89cbf-131">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="89cbf-131">**Result**</span></span>  
 <span data-ttu-id="89cbf-132">Muestra un vínculo, **Correcto** o **Error**, en el que se puede hacer clic para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="89cbf-132">Displays a link, either **Success** or **Error**, which you can click for more information.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="89cbf-133">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="89cbf-133">Using Transact-SQL</span></span>  
 <span data-ttu-id="89cbf-134">**Para quitar un agente de escucha del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="89cbf-134">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="89cbf-135">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="89cbf-135">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="89cbf-136">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="89cbf-136">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="89cbf-137">ALTER AVAILABILITY GROUP *group_name* quitar el agente de escucha **' *`dns_name`* '**</span><span class="sxs-lookup"><span data-stu-id="89cbf-137">ALTER AVAILABILITY GROUP *group_name* REMOVE LISTENER **'*`dns_name`*'**</span></span>  
  
     <span data-ttu-id="89cbf-138">donde *nombre_grupo* es el nombre del grupo de disponibilidad y *nombre_DNS* es el nombre DNS del agente de escucha de grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="89cbf-138">where *group_name* is the name of the availability group and *dns_name* is the DNS name of the availability group listener.</span></span>  
  
     <span data-ttu-id="89cbf-139">En el ejemplo siguiente se elimina el agente de escucha del grupo de disponibilidad `AccountsAG` .</span><span class="sxs-lookup"><span data-stu-id="89cbf-139">The following example deletes the listener of the `AccountsAG` availability group.</span></span> <span data-ttu-id="89cbf-140">El nombre DNS es AccountsAG_Listener.</span><span class="sxs-lookup"><span data-stu-id="89cbf-140">The DNS name is AccountsAG_Listener.</span></span>  
  
    ```sql
    ALTER AVAILABILITY GROUP AccountsAG REMOVE LISTENER 'AccountsAG_Listener';  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="89cbf-141">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="89cbf-141">Using PowerShell</span></span>  
 <span data-ttu-id="89cbf-142">**Para quitar un agente de escucha del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="89cbf-142">**To remove an availability group listener**</span></span>  
  
1.  <span data-ttu-id="89cbf-143">Establezca el valor predeterminado (`cd`) en la instancia del servidor que hospeda la réplica de disponibilidad principal.</span><span class="sxs-lookup"><span data-stu-id="89cbf-143">Set default (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="89cbf-144">Utilice el cmdlet integrado `Remove-Item` para quitar un agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="89cbf-144">Use the built in `Remove-Item` cmdlet to remove a listener.</span></span> <span data-ttu-id="89cbf-145">Por ejemplo, el comando siguiente quita un agente de escucha denominado `MyListener` del grupo de disponibilidad `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="89cbf-145">For example, the following command removes a listener named `MyListener` from an availability group named `MyAg`.</span></span>  
  
    ```powershell
    Remove-Item SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AGListeners\MyListener  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="89cbf-146">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89cbf-146">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="89cbf-147">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="89cbf-147">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="89cbf-148">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="89cbf-148">Related Tasks</span></span>  
  
-   [<span data-ttu-id="89cbf-149">Crear o configurar un agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89cbf-149">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="89cbf-150">Ver las propiedades del agente de escucha de grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89cbf-150">View Availability Group Listener Properties &#40;SQL Server&#41;</span></span>](view-availability-group-listener-properties-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="89cbf-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89cbf-151">See Also</span></span>  
 <span data-ttu-id="89cbf-152">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="89cbf-152">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="89cbf-153">Agentes de escucha de grupo de disponibilidad, conectividad de cliente y conmutación por error de una aplicación &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="89cbf-153">Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;</span></span>](../../listeners-client-connectivity-application-failover.md)  
