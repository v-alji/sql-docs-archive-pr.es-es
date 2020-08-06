---
title: Usar directivas de AlwaysOn para ver el estado de un grupo de disponibilidad (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], policies
ms.assetid: 6f1bcbc3-1220-4071-8e53-4b957f5d3089
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5c4444afc2348b2407dc19c1c12761ef0251631e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750161"
---
# <a name="use-alwayson-policies-to-view-the-health-of-an-availability-group-sql-server"></a><span data-ttu-id="8b83e-102">Usar directivas de AlwaysOn para ver el estado de un grupo de disponibilidad (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8b83e-102">Use AlwaysOn Policies to View the Health of an Availability Group (SQL Server)</span></span>
  <span data-ttu-id="8b83e-103">En este tema se describe cómo determinar el estado operativo de un grupo de disponibilidad AlwaysOn usando una directiva de AlwaysOn en [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] o PowerShell en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8b83e-103">This topic describes how to determine the operational health of an AlwaysOn availability group by using an AlwaysOn policy in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or PowerShell in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="8b83e-104">Para obtener información sobre la administración basada en directivas de AlwaysOn, vea [directivas de AlwaysOn para problemas operativos con grupos de disponibilidad AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="8b83e-104">For information about AlwaysOn Policy Based Management, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8b83e-105">Para las directivas de AlwaysOn, los nombres de categoría se usan como identificadores.</span><span class="sxs-lookup"><span data-stu-id="8b83e-105">For AlwaysOn policies, the category names are used as IDs.</span></span> <span data-ttu-id="8b83e-106">La acción de cambiar el nombre de una categoría de AlwaysOn interrumpiría la funcionalidad de la evaluación de estado.</span><span class="sxs-lookup"><span data-stu-id="8b83e-106">Changing the name of an AlwaysOn category would break its health-evaluation functionality.</span></span> <span data-ttu-id="8b83e-107">Por consiguiente, los nombres de categoría de AlwaysOn no deben modificarse nunca.</span><span class="sxs-lookup"><span data-stu-id="8b83e-107">Therefore, the names of AlwaysOn category should never be modified.</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8b83e-108">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="8b83e-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8b83e-109">Seguridad</span><span class="sxs-lookup"><span data-stu-id="8b83e-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8b83e-110">Permisos</span><span class="sxs-lookup"><span data-stu-id="8b83e-110">Permissions</span></span>  
 <span data-ttu-id="8b83e-111">Requiere permisos CONNECT TO, VIEW SERVER STATE y VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="8b83e-111">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="using-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="8b83e-112">Usar el panel de AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="8b83e-112">Using the AlwaysOn Dashboard</span></span>  
 <span data-ttu-id="8b83e-113">**Para abrir el panel de AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="8b83e-113">**To open the AlwaysOn Dashboard**</span></span>  
  
1.  <span data-ttu-id="8b83e-114">En el Explorador de objetos, conéctese a la instancia del servidor que hospeda una de las réplicas de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8b83e-114">In Object Explorer, connect to the server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="8b83e-115">Para ver información acerca de todas las réplicas de disponibilidad en un grupo de disponibilidad, use la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="8b83e-115">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="8b83e-116">Haga clic en el nombre del servidor para expandir el árbol.</span><span class="sxs-lookup"><span data-stu-id="8b83e-116">Click the server name to expand the server tree.</span></span>  
  
3.  <span data-ttu-id="8b83e-117">Expanda el nodo **Alta disponibilidad de AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="8b83e-117">Expand the **AlwaysOn High Availability** node.</span></span>  
  
     <span data-ttu-id="8b83e-118">Haga clic con el botón derecho en el nodo **Grupos de disponibilidad** o expanda este nodo y haga clic con el botón derecho en un grupo de disponibilidad específico.</span><span class="sxs-lookup"><span data-stu-id="8b83e-118">Either right-click the **Availability Groups** node or expand this node and right-click a specific availability group.</span></span>  
  
4.  <span data-ttu-id="8b83e-119">Seleccione el comando de **Mostrar panel** .</span><span class="sxs-lookup"><span data-stu-id="8b83e-119">Select the **Show Dashboard** command.</span></span>  
  
 <span data-ttu-id="8b83e-120">Para más información sobre cómo usar el panel AlwaysOn, vea [Usar el panel AlwaysOn &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8b83e-120">For information about how to use the AlwaysOn Dashboard, see [Use the AlwaysOn Dashboard &#40;SQL Server Management Studio&#41;](use-the-always-on-dashboard-sql-server-management-studio.md).</span></span>  
  
##  <a name="using-powershell"></a><a name="PowerShellProcedure"></a> <span data-ttu-id="8b83e-121">Con PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b83e-121">Using PowerShell</span></span>  
 <span data-ttu-id="8b83e-122">**Usar directivas de AlwaysOn para ver el estado de un grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="8b83e-122">**Use AlwaysOn policies to view the health of an availability group**</span></span>  
  
1.  <span data-ttu-id="8b83e-123">Establezca el valor predeterminado (`cd`) en una instancia del servidor que hospeda una de las réplicas de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="8b83e-123">Set default (`cd`) to a server instance that hosts one of the availability replicas.</span></span> <span data-ttu-id="8b83e-124">Para ver información acerca de todas las réplicas de disponibilidad en un grupo de disponibilidad, use la instancia del servidor que hospeda la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="8b83e-124">To view information about all of the availability replicas in an availability group, use to the server instance that hosts the primary replica.</span></span>  
  
2.  <span data-ttu-id="8b83e-125">Use los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8b83e-125">Use the following cmdlets:</span></span>  
  
     `Test-SqlAvailabilityGroup`  
     <span data-ttu-id="8b83e-126">Evalúa el estado de un grupo de disponibilidad mediante la evaluación de las directivas de administración basada en directivas (PBM) de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b83e-126">Assesses the health of an availability group by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="8b83e-127">Debe tener permisos CONNECT, VIEW SERVER STATE, y VIEW ANY DEFINITION para ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8b83e-127">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="8b83e-128">Por ejemplo, el comando siguiente muestra todos los grupos de disponibilidad con el estado de mantenimiento "Error" de la instancia del servidor `Computer\Instance`.</span><span class="sxs-lookup"><span data-stu-id="8b83e-128">For example, the following command shows all availability groups with a health state of "Error" on the server instance `Computer\Instance`.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups |
        Test-SqlAvailabilityGroup |
        Where-Object { $_.HealthState -eq "Error" }  
    ```  
  
     `Test-SqlAvailabilityReplica`  
     <span data-ttu-id="8b83e-129">Evalúa el estado de las réplicas de disponibilidad mediante la evaluación de las directivas de administración basada en directivas (PBM) de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b83e-129">Assesses the health of availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span> <span data-ttu-id="8b83e-130">Debe tener permisos CONNECT, VIEW SERVER STATE, y VIEW ANY DEFINITION para ejecutar este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8b83e-130">You must have CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions to execute this cmdlet.</span></span>  
  
     <span data-ttu-id="8b83e-131">Por ejemplo, el comando siguiente evalúa el estado de la réplica de disponibilidad `MyReplica` del grupo de disponibilidad `MyAg` y genera un breve resumen.</span><span class="sxs-lookup"><span data-stu-id="8b83e-131">For example, the following command evaluates the health of the availability replica named `MyReplica` in the availability group `MyAg` and outputs a brief summary.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityReplica -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\AvailabilityReplicas\MyReplica  
    ```  
  
     `Test-SqlDatabaseReplicaState`  
     <span data-ttu-id="8b83e-132">Evalúa el estado de una base de datos de disponibilidad en todas las réplicas de disponibilidad mediante la evaluación de directivas de administración basada en directivas (PBM) de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8b83e-132">Assesses the health of an availability database on all joined availability replicas by evaluating SQL Server policy based management (PBM) policies.</span></span>  
  
     <span data-ttu-id="8b83e-133">Por ejemplo, el comando siguiente evalúa el estado de todas las bases de datos de disponibilidad del grupo de disponibilidad `MyAg` y genera un breve resumen de cada base de datos.</span><span class="sxs-lookup"><span data-stu-id="8b83e-133">For example, the following command evaluates the health of all availability databases in the availability group `MyAg` and outputs a brief summary for each database.</span></span>  
  
    ```powershell
    Get-ChildItem SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\MyAg\DatabaseReplicaStates |
        Test-SqlDatabaseReplicaState  
    ```  
  
     <span data-ttu-id="8b83e-134">Estos cmdlets aceptan las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="8b83e-134">These cmdlets accept the following options:</span></span>  
  
    |<span data-ttu-id="8b83e-135">Opción</span><span class="sxs-lookup"><span data-stu-id="8b83e-135">Option</span></span>|<span data-ttu-id="8b83e-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b83e-136">Description</span></span>|  
    |------------|-----------------|  
    |`AllowUserPolicies`|<span data-ttu-id="8b83e-137">Ejecuta las directivas de usuario que se encuentran en las categorías de directiva de AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="8b83e-137">Runs user policies found in the AlwaysOn policy categories.</span></span>|  
    |`InputObject`|<span data-ttu-id="8b83e-138">Una colección de objetos que representan grupos de disponibilidad, réplicas de disponibilidad o estados de bases de datos de disponibilidad (dependiendo del cmdlet que esté utilizando).</span><span class="sxs-lookup"><span data-stu-id="8b83e-138">A collection of objects that, represent availability groups, availability replicas, or availability database states (depending on which cmdlet you are using).</span></span> <span data-ttu-id="8b83e-139">El cmdlet calculará el estado de los objetos especificados.</span><span class="sxs-lookup"><span data-stu-id="8b83e-139">The cmdlet will compute the health of the specified objects.</span></span>|  
    |`NoRefresh`|<span data-ttu-id="8b83e-140">Cuando se establece este parámetro, el cmdlet no actualizará manualmente los objetos especificados por el parámetro `-Path` o `-InputObject`.</span><span class="sxs-lookup"><span data-stu-id="8b83e-140">When this parameter is set, the cmdlet will not manually refresh the objects specified by the `-Path` or `-InputObject` parameter.</span></span>|  
    |`Path`|<span data-ttu-id="8b83e-141">La ruta de acceso al grupo de disponibilidad, una o varias réplicas de disponibilidad o el estado del clúster de réplica de la base de datos de disponibilidad (dependiendo del cmdlet que esté utilizando).</span><span class="sxs-lookup"><span data-stu-id="8b83e-141">The path to the availability group, one or more availability replicas, or database replica cluster state of the availability database (depending on which cmdlet you are using).</span></span> <span data-ttu-id="8b83e-142">Se trata de un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="8b83e-142">This is an optional parameter.</span></span> <span data-ttu-id="8b83e-143">Si no se especifica, el valor del valor predeterminado de este parámetro es la ubicación de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="8b83e-143">If not specified, the value of this parameter defaults to the current working location.</span></span>|  
    |`ShowPolicyDetails`|<span data-ttu-id="8b83e-144">Muestra el resultado de cada evaluación de directiva realizada por este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8b83e-144">Shows the result of each policy evaluation performed by this cmdlet.</span></span> <span data-ttu-id="8b83e-145">El cmdlet envía un objeto por evaluación de la directiva, y este objeto tiene campos que describen los resultados de la evaluación (si la directiva se ha superado o no, el nombre y la categoría de la directiva, etc.).</span><span class="sxs-lookup"><span data-stu-id="8b83e-145">The cmdlet outputs one object per policy evaluation, and this object has fields describing the results of evaluation (whether the policy passed or not, the policy name and category, and so forth).</span></span>|  
  
     <span data-ttu-id="8b83e-146">Por ejemplo, el siguiente comando `Test-SqlAvailabilityGroup` especifica el parámetro `-ShowPolicyDetails` para mostrar el resultado de cada evaluación de directiva realizada por este cmdlet en cada directiva de administración basada en directivas (PBM) que se ejecutó en el grupo de disponibilidad `MyAg`.</span><span class="sxs-lookup"><span data-stu-id="8b83e-146">For example, the following `Test-SqlAvailabilityGroup` command specifies the `-ShowPolicyDetails` parameter to show the result of each policy evaluation performed by this cmdlet for each policy-based management (PBM) policy that was executed on the availability group named `MyAg`.</span></span>  
  
    ```powershell
    Test-SqlAvailabilityGroup -Path SQLSERVER:\Sql\Computer\Instance\AvailabilityGroups\AgName -ShowPolicyDetails  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="8b83e-147">Para ver la sintaxis de un cmdlet, use el cmdlet `Get-Help` en el entorno de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b83e-147">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="8b83e-148">Para más información, consulte [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="8b83e-148">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="8b83e-149">**Para configurar y usar el proveedor de SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8b83e-149">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="8b83e-150">Proveedor de SQL Server PowerShell Provider</span><span class="sxs-lookup"><span data-stu-id="8b83e-150">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
-   [<span data-ttu-id="8b83e-151">Obtener ayuda SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="8b83e-151">Get Help SQL Server PowerShell</span></span>](../../../powershell/sql-server-powershell.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="8b83e-152">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="8b83e-152">Related Content</span></span>  
 <span data-ttu-id="8b83e-153">**SQL Server blogs del equipo de AlwaysOn: supervisión del estado de AlwaysOn con PowerShell:**</span><span class="sxs-lookup"><span data-stu-id="8b83e-153">**SQL Server AlwaysOn Team Blogs-Monitoring AlwaysOn Health with PowerShell:**</span></span>  
  
-   [<span data-ttu-id="8b83e-154">Parte 1: información general básica de los cmdlets</span><span class="sxs-lookup"><span data-stu-id="8b83e-154">Part 1: Basic Cmdlet Overview</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-1-basic-cmdlet-overview)  
  
-   [<span data-ttu-id="8b83e-155">Parte 2: uso avanzado de cmdlet</span><span class="sxs-lookup"><span data-stu-id="8b83e-155">Part 2: Advanced Cmdlet Usage</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/the-alwayson-health-model-part-2-extending-the-health-model)  
  
-   [<span data-ttu-id="8b83e-156">Parte 3: una aplicación simple de supervisión</span><span class="sxs-lookup"><span data-stu-id="8b83e-156">Part 3: A Simple Monitoring Application</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-3-a-simple-monitoring-application)  
  
-   [<span data-ttu-id="8b83e-157">Parte 4: integración con el Agente SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b83e-157">Part 4: Integration with SQL Server Agent</span></span>](https://docs.microsoft.com/archive/blogs/sqlalwayson/monitoring-alwayson-health-with-powershell-part-4-integration-with-sql-server-agent)  
  
## <a name="see-also"></a><span data-ttu-id="8b83e-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b83e-158">See Also</span></span>  
 <span data-ttu-id="8b83e-159">[Información general de Grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8b83e-159">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="8b83e-160">[Administración de un grupo de disponibilidad &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8b83e-160">[Administration of an Availability Group &#40;SQL Server&#41;](administration-of-an-availability-group-sql-server.md) </span></span>  
 <span data-ttu-id="8b83e-161">[Supervisión de los grupos de disponibilidad &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8b83e-161">[Monitoring of Availability Groups &#40;SQL Server&#41;](monitoring-of-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="8b83e-162">Directivas de AlwaysOn para problemas operativos con grupos de disponibilidad AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8b83e-162">AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)</span></span>](always-on-policies-for-operational-issues-always-on-availability.md) 
