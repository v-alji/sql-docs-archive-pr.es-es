---
title: Cambiar el modo de disponibilidad de una réplica de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], configuring
- Availability Groups [SQL Server], availability modes
ms.assetid: c4da8f25-fb1b-45a4-8bf2-195df6df634c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1636f3ea86e083e47276423b120dbc8d3744d387
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750226"
---
# <a name="change-the-availability-mode-of-an-availability-replica-sql-server"></a><span data-ttu-id="18035-102">Cambiar el modo de disponibilidad de una réplica de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="18035-102">Change the Availability Mode of an Availability Replica (SQL Server)</span></span>
  <span data-ttu-id="18035-103">En este tema se describe cómo cambiar el modo de disponibilidad de una réplica de disponibilidad de un grupo de disponibilidad AlwaysOn en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)]o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18035-103">This topic describes how to change the availability mode of an availability replica in an AlwaysOn availability group in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or PowerShell.</span></span> <span data-ttu-id="18035-104">El modo de disponibilidad es una propiedad de réplica que controla si la réplica se confirma asincrónica o sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="18035-104">The availability mode is a replica property that controls the whether the replica commits asynchronously or synchronously.</span></span> <span data-ttu-id="18035-105">El*modo confirmación asincrónica* maximiza el rendimiento a costa de la alta disponibilidad y solo admite la conmutación por error manual forzada (con posible pérdida de datos), que suele denominarse *conmutación por error forzada*.</span><span class="sxs-lookup"><span data-stu-id="18035-105">*Asynchronous-commit mode* maximizes performance at the expense of high availability and supports only forced manual failover (with possible data loss), typically called *forced failover*.</span></span> <span data-ttu-id="18035-106">El*modo confirmación sincrónica* da prioridad a la alta disponibilidad sobre el rendimiento y, una vez sincronizada la réplica secundaria, admite la conmutación por error manual y, opcionalmente, la conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="18035-106">*Synchronous-commit mode* emphasizes high availability over performance and, once the secondary replica is synchronized, supports manual failover and, optionally, automatic failover.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="18035-107">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="18035-107">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="18035-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="18035-108">Prerequisites</span></span>  
  
-   <span data-ttu-id="18035-109">Debe estar conectado a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="18035-109">You must be connected to the server instance that hosts the primary replica.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="18035-110">Seguridad</span><span class="sxs-lookup"><span data-stu-id="18035-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="18035-111">Permisos</span><span class="sxs-lookup"><span data-stu-id="18035-111">Permissions</span></span>  
 <span data-ttu-id="18035-112">Se requiere el permiso ALTER AVAILABILITY GROUP en el grupo de disponibilidad, el permiso CONTROL AVAILABILITY GROUP, el permiso ALTER ANY AVAILABILITY GROUP o el permiso CONTROL SERVER.</span><span class="sxs-lookup"><span data-stu-id="18035-112">Requires ALTER AVAILABILITY GROUP permission on the availability group, CONTROL AVAILABILITY GROUP permission, ALTER ANY AVAILABILITY GROUP permission, or CONTROL SERVER permission.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="18035-113">Uso de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="18035-113">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="18035-114">**Para cambiar el modo de disponibilidad de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="18035-114">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="18035-115">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda la réplica principal y expanda el árbol.</span><span class="sxs-lookup"><span data-stu-id="18035-115">In Object Explorer, connect to the server instance that hosts the primary replica, and expand the server tree.</span></span>  
  
2.  <span data-ttu-id="18035-116">Expanda los nodos **Alta disponibilidad de AlwaysOn** y **Grupos de disponibilidad** .</span><span class="sxs-lookup"><span data-stu-id="18035-116">Expand the **AlwaysOn High Availability** node and the **Availability Groups** node.</span></span>  
  
3.  <span data-ttu-id="18035-117">Haga clic en el grupo de disponibilidad cuya réplica desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="18035-117">Click the availability group whose replica you want to change.</span></span>  
  
4.  <span data-ttu-id="18035-118">Haga clic con el botón derecho en la réplica y haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="18035-118">Right-click the replica, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="18035-119">En el cuadro de diálogo **Propiedades de réplica de disponibilidad** , use la lista desplegable **Modo de disponibilidad** para cambiar el modo de disponibilidad de esta réplica.</span><span class="sxs-lookup"><span data-stu-id="18035-119">In the **Availability Replica Properties** dialog box, use the **Availability mode** drop list to change the availability mode of this replica.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="18035-120">Usar Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="18035-120">Using Transact-SQL</span></span>  
 <span data-ttu-id="18035-121">**Para cambiar el modo de disponibilidad de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="18035-121">**To change the availability mode of an availability group**</span></span>  
  
1.  <span data-ttu-id="18035-122">Conéctese a la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="18035-122">Connect to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="18035-123">Use la instrucción [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="18035-123">Use the [ALTER AVAILABILITY GROUP](/sql/t-sql/statements/alter-availability-group-transact-sql) statement, as follows:</span></span>  
  
     <span data-ttu-id="18035-124">ALTER AVAILABILITY GROUP *nombre_grupo* MODIFY REPLICA ON '*nombre_servidor*'</span><span class="sxs-lookup"><span data-stu-id="18035-124">ALTER AVAILABILITY GROUP *group_name* MODIFY REPLICA ON '*server_name*'</span></span>  
  
     <span data-ttu-id="18035-125">WITH ( {</span><span class="sxs-lookup"><span data-stu-id="18035-125">WITH ( {</span></span>  
  
     <span data-ttu-id="18035-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span><span class="sxs-lookup"><span data-stu-id="18035-126">AVAILABILITY_MODE = { SYNCHRONOUS_COMMIT | ASYNCHRONOUS_COMMIT }</span></span>  
  
     <span data-ttu-id="18035-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span><span class="sxs-lookup"><span data-stu-id="18035-127">| FAILOVER_MODE = { AUTOMATIC | MANUAL }</span></span>  
  
     <span data-ttu-id="18035-128">} )</span><span class="sxs-lookup"><span data-stu-id="18035-128">} )</span></span>  
  
     <span data-ttu-id="18035-129">donde *group_name* es el nombre del grupo de disponibilidad y *SERVER_NAME* es el nombre de la instancia del servidor que hospeda la réplica que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="18035-129">where *group_name* is the name of the availability group and *server_name* is the name of the server instance that hosts the replica to be modified.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="18035-130">FAILOVER_MODE = AUTOMATIC solo se admite si se especifica también AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span><span class="sxs-lookup"><span data-stu-id="18035-130">FAILOVER_MODE = AUTOMATIC is supported only if you also specify AVAILABILITY_MODE = SYNCHRONOUS_COMMIT.</span></span>  
  
     <span data-ttu-id="18035-131">En el ejemplo siguiente, escrito en la réplica principal del grupo de disponibilidad `AccountsAG` , se cambian los modos de disponibilidad y de conmutación por error por confirmación sincrónica y conmutación automática por error, respectivamente, en la réplica que se hospeda en la instancia del servidor `INSTANCE09` .</span><span class="sxs-lookup"><span data-stu-id="18035-131">The following example, entered on the primary replica of the `AccountsAG` availability group, changes the availability and failover modes to synchronous commit and automatic failover, respectively, for the replica hosted by the `INSTANCE09` server instance.</span></span>  
  
    ```  
  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (AVAILABILITY_MODE = SYNCHRONOUS_COMMIT);  
    ALTER AVAILABILITY GROUP AccountsAG MODIFY REPLICA ON 'INSTANCE09'  
       WITH (FAILOVER_MODE = AUTOMATIC);  
    ```  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="18035-132">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="18035-132">Using PowerShell</span></span>

### <a name="to-change-the-availability-mode-of-an-availability-group"></a><span data-ttu-id="18035-133">Para cambiar el modo de disponibilidad de un grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="18035-133">To change the availability mode of an availability group</span></span>
  
1.  <span data-ttu-id="18035-134">Cambie el directorio (`cd`) a la instancia de servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="18035-134">Change directory (`cd`) to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="18035-135">Utilice el cmdlet `Set-SqlAvailabilityReplica` con el parámetro `AvailabilityMode` y, opcionalmente, el parámetro `FailoverMode`.</span><span class="sxs-lookup"><span data-stu-id="18035-135">Use the `Set-SqlAvailabilityReplica` cmdlet with the `AvailabilityMode` parameter and, optionally, the `FailoverMode` parameter.</span></span>  
  
     <span data-ttu-id="18035-136">Por ejemplo, el comando siguiente modifica la réplica `MyReplica` en el grupo de disponibilidad `MyAg` para utilizar el modo de disponibilidad de confirmación sincrónica y admitir la conmutación automática por error.</span><span class="sxs-lookup"><span data-stu-id="18035-136">For example, the following command modifies the replica `MyReplica` in the availability group `MyAg` to use synchronous-commit availability mode and to support automatic failover.</span></span>  
  
    ```powershell
    Set-SqlAvailabilityReplica -AvailabilityMode "SynchronousCommit" -FailoverMode "Automatic" `   
     -Path SQLSERVER:\Sql\PrimaryServer\InstanceName\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="18035-137">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18035-137">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="18035-138">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="18035-138">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
<span data-ttu-id="18035-139">Para configurar y usar el proveedor de SQL Server PowerShell, vea [proveedor de SQL Server PowerShell](../../../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="18035-139">To set up and use the SQL Server PowerShell provider, see [SQL Server PowerShell Provider](../../../powershell/sql-server-powershell-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="18035-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18035-140">See Also</span></span>  
 <span data-ttu-id="18035-141">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="18035-141">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="18035-142">[Modos de disponibilidad (Grupos de disponibilidad AlwaysOn)](availability-modes-always-on-availability-groups.md) </span><span class="sxs-lookup"><span data-stu-id="18035-142">[Availability Modes (AlwaysOn Availability Groups)](availability-modes-always-on-availability-groups.md) </span></span>  
 [<span data-ttu-id="18035-143">Conmutación por error y modos de conmutación por error &#40;Grupos de disponibilidad AlwaysOn&#41;</span><span class="sxs-lookup"><span data-stu-id="18035-143">Failover and Failover Modes &#40;AlwaysOn Availability Groups&#41;</span></span>](failover-and-failover-modes-always-on-availability-groups.md)  