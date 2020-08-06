---
title: Usar el panel de AlwaysOn (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.agdashboard.f1
helpviewer_keywords:
- Availability Groups [SQL Server], policies
- Availability Groups [SQL Server], dashboard
ms.assetid: c9ba2589-139e-42bc-99e1-94546717c64d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c4ce0072bcd6642dcb4f3ac63e04c98786bd550e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670588"
---
# <a name="use-the-alwayson-dashboard-sql-server-management-studio"></a><span data-ttu-id="7d17c-102">Usar el Panel de AlwaysOn (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7d17c-102">Use the AlwaysOn Dashboard (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7d17c-103">Los administradores de bases de datos utilizan el Panel AlwaysOn para obtener una vista global del estado de un grupo de disponibilidad AlwaysOn y de sus réplicas y bases de datos de disponibilidad en [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d17c-103">Database administrators use the AlwaysOn Dashboard to obtains an at-a-glance view the health of an AlwaysOn availability group and its availability replicas and databases in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="7d17c-104">Algunas de los usos típicos del Panel AlwaysOn son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-104">Some of the typical uses for the AlwaysOn Dashboard are:</span></span>  
  
-   <span data-ttu-id="7d17c-105">Elegir una réplica para una conmutación por error manual.</span><span class="sxs-lookup"><span data-stu-id="7d17c-105">Choosing a replica for a manual failover.</span></span>  
  
-   <span data-ttu-id="7d17c-106">Estimar la pérdida de datos si se fuerza la conmutación por error.</span><span class="sxs-lookup"><span data-stu-id="7d17c-106">Estimating data loss if you force failover.</span></span>  
  
-   <span data-ttu-id="7d17c-107">Evaluar el rendimiento de la sincronización de datos.</span><span class="sxs-lookup"><span data-stu-id="7d17c-107">Evaluating data-synchronization performance.</span></span>  
  
-   <span data-ttu-id="7d17c-108">Evaluar el impacto en el rendimiento de una réplica secundaria de confirmación asincrónica</span><span class="sxs-lookup"><span data-stu-id="7d17c-108">Evaluating the performance impact of a synchronous-commit secondary replica</span></span>  
  
 <span data-ttu-id="7d17c-109">El Panel AlwaysOn proporciona indicadores de rendimiento y estados de grupos de disponibilidad, lo que permite tomar fácilmente decisiones operativas para conseguir una alta disponibilidad utilizando los siguientes tipos de información.</span><span class="sxs-lookup"><span data-stu-id="7d17c-109">The AlwaysOn Dashboard provides key availability group states and performance indicators allowing you to easily make high availability operational decisions using the following types of information.</span></span>  
  
-   <span data-ttu-id="7d17c-110">Estado acumulado de réplica</span><span class="sxs-lookup"><span data-stu-id="7d17c-110">Replica roll-up state</span></span>  
  
-   <span data-ttu-id="7d17c-111">Modo y estado de sincronización</span><span class="sxs-lookup"><span data-stu-id="7d17c-111">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="7d17c-112">Pérdida de datos calculada</span><span class="sxs-lookup"><span data-stu-id="7d17c-112">Estimate Data Loss</span></span>  
  
-   <span data-ttu-id="7d17c-113">Tiempo calculado de recuperación (rehacer puesta al día)</span><span class="sxs-lookup"><span data-stu-id="7d17c-113">Estimated Recovery Time (redo catch up)</span></span>  
  
-   <span data-ttu-id="7d17c-114">Detalles de réplica de base de datos</span><span class="sxs-lookup"><span data-stu-id="7d17c-114">Database Replica details</span></span>  
  
-   <span data-ttu-id="7d17c-115">Modo y estado de sincronización</span><span class="sxs-lookup"><span data-stu-id="7d17c-115">Synchronization mode and state</span></span>  
  
-   <span data-ttu-id="7d17c-116">Tiempo para restaurar registro</span><span class="sxs-lookup"><span data-stu-id="7d17c-116">Time to restore log</span></span>  
  
 
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7d17c-117">Antes de comenzar</span><span class="sxs-lookup"><span data-stu-id="7d17c-117">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="7d17c-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7d17c-118">Prerequisites</span></span>  
 <span data-ttu-id="7d17c-119">Debe estar conectado a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (instancia del servidor) que hospeda la réplica principal o una réplica secundaria de un grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-119">You must be connected to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (server instance) that hosts either the primary replica or a secondary replica of an availability group.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7d17c-120">Seguridad</span><span class="sxs-lookup"><span data-stu-id="7d17c-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7d17c-121">Permisos</span><span class="sxs-lookup"><span data-stu-id="7d17c-121">Permissions</span></span>  
 <span data-ttu-id="7d17c-122">Requiere permisos CONNECT TO, VIEW SERVER STATE y VIEW ANY DEFINITION.</span><span class="sxs-lookup"><span data-stu-id="7d17c-122">Requires CONNECT, VIEW SERVER STATE, and VIEW ANY DEFINITION permissions.</span></span>  
  
##  <a name="to-start-the-alwayson-dashboard"></a><a name="SSMSProcedure"></a><span data-ttu-id="7d17c-123">Para iniciar el panel de AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7d17c-123">To start the AlwaysOn Dashboard</span></span>  
  
1.  <span data-ttu-id="7d17c-124">En el Explorador de objetos, conéctese a la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en la que desea ejecutar el Panel AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="7d17c-124">In Object Explorer, connect to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] on which you want to run the AlwaysOn Dashboard.</span></span>  
  
2.  <span data-ttu-id="7d17c-125">Expanda el nodo **Alta disponibilidad de AlwaysOn** , haga clic con el botón secundario en el nodo **Grupos de disponibilidad** y, a continuación, haga clic en **Mostrar panel**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-125">Expand the **AlwaysOn High Availability** node, right-click the **Availability Groups** node, and then click **Show Dashboard**.</span></span>  
  
###  <a name="to-change-alwayson-dashboard-options"></a><a name="DashboardOptions"></a><span data-ttu-id="7d17c-126">Para cambiar las opciones del panel de AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7d17c-126">To Change AlwaysOn Dashboard Options</span></span>  
 <span data-ttu-id="7d17c-127">Puede usar el cuadro de diálogo **Opciones** de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] para configurar el comportamiento del Panel AlwaysOn de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] respecto a la actualización y habilitación automática de una directiva de AlwaysOn autodefinida.</span><span class="sxs-lookup"><span data-stu-id="7d17c-127">You can use the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]**Options** dialog box to configure the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] AlwaysOn Dashboard behavior for automatic refreshing and enabling an auto-defined AlwaysOn policy.</span></span>  
  
1.  <span data-ttu-id="7d17c-128">En el menú **Herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-128">From the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="7d17c-129">Para actualizar automáticamente el panel, en el cuadro de diálogo **Opciones** , seleccione **Activar actualización automática**, escriba el intervalo de actualización en segundos y especifique el número de veces que desea volver a intentar la conexión.</span><span class="sxs-lookup"><span data-stu-id="7d17c-129">To automatically refresh the dashboard, in the **Options** dialog box, select **Turn on automatic refresh**, enter the refresh interval in seconds, and then enter the number of times you want to retry the connection.</span></span>  
  
3.  <span data-ttu-id="7d17c-130">Para habilitar una directiva definida por el usuario, seleccione **Habilitar la directiva de AlwaysOn definida por el usuario**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-130">To enable a user-defined policy, select **Enable user-defined AlwaysOn policy**.</span></span>  
  
##  <a name="availability-group-summary"></a><a name="AvGroupsView"></a> <span data-ttu-id="7d17c-131">Resumen de grupos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="7d17c-131">Availability Group Summary</span></span>  
 <span data-ttu-id="7d17c-132">La pantalla de grupos de disponibilidad muestra una línea de resumen para cada grupo de disponibilidad para el que la instancia del servidor conectado hospeda una réplica.</span><span class="sxs-lookup"><span data-stu-id="7d17c-132">The availability group screen displays a summary line for each availability group for which the connected server instance hosts a replica.</span></span> <span data-ttu-id="7d17c-133">Este panel muestra las columnas siguientes.</span><span class="sxs-lookup"><span data-stu-id="7d17c-133">This pane displays the following columns.</span></span>  
  
 <span data-ttu-id="7d17c-134">**Nombre del grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="7d17c-134">**Availability Group Name**</span></span>  
 <span data-ttu-id="7d17c-135">El nombre de un grupo de disponibilidad para el que la instancia del servidor conectado hospeda una réplica.</span><span class="sxs-lookup"><span data-stu-id="7d17c-135">The name of an availability group for which the connected server instance hosts a replica.</span></span>  
  
 <span data-ttu-id="7d17c-136">**Instancia principal**</span><span class="sxs-lookup"><span data-stu-id="7d17c-136">**Primary Instance**</span></span>  
 <span data-ttu-id="7d17c-137">Nombre de la instancia de servidor que hospeda la réplica de disponibilidad del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-137">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="7d17c-138">**Modo de conmutación por error**</span><span class="sxs-lookup"><span data-stu-id="7d17c-138">**Failover Mode**</span></span>  
 <span data-ttu-id="7d17c-139">Muestra el modo de conmutación por error para el que se configura la réplica.</span><span class="sxs-lookup"><span data-stu-id="7d17c-139">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="7d17c-140">Los valores de modo de conmutación por error posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-140">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="7d17c-141">**Automática**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-141">**Automatic**.</span></span> <span data-ttu-id="7d17c-142">Indica que una o varias réplicas están en modo de conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="7d17c-142">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="7d17c-143">**Manual**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-143">**Manual**.</span></span> <span data-ttu-id="7d17c-144">Indica que ninguna réplica está en modo de conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="7d17c-144">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="7d17c-145">**Problemas**</span><span class="sxs-lookup"><span data-stu-id="7d17c-145">**Issues**</span></span>  
 <span data-ttu-id="7d17c-146">Haga clic en el vínculo **Problemas** para abrir documentación de solución de problemas relativa a un problema determinado.</span><span class="sxs-lookup"><span data-stu-id="7d17c-146">Click the **Issues** link to open troubleshooting documentation for a given issue.</span></span> <span data-ttu-id="7d17c-147">Para obtener una lista de todos los problemas de directivas de AlwaysOn, vea [directivas de AlwaysOn para problemas operativos con grupos de disponibilidad AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="7d17c-147">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="7d17c-148">Haga clic en los encabezados de columna para ordenar la información de grupos de disponibilidad por nombre de grupo de disponibilidad, instancia principal, modo de conmutación por error o problema.</span><span class="sxs-lookup"><span data-stu-id="7d17c-148">Click the column headings to sort the availability group information by the name of the availability group, primary instance, failover mode, or Issue.</span></span>  
  
##  <a name="availability-group-details"></a><a name="AvGroupDetails"></a> <span data-ttu-id="7d17c-149">Detalles de grupos de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="7d17c-149">Availability Group Details</span></span>  
 <span data-ttu-id="7d17c-150">Se muestra la información detallada siguiente para el grupo de disponibilidad seleccionado de la pantalla de resumen:</span><span class="sxs-lookup"><span data-stu-id="7d17c-150">The following detail information is displayed for the availability group that you select from the summary screen:</span></span>  
  
 <span data-ttu-id="7d17c-151">**Estado de grupo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="7d17c-151">**Availability group state**</span></span>  
 <span data-ttu-id="7d17c-152">Muestra el estado de mantenimiento del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-152">Displays the state of health for the availability group.</span></span>  
  
 <span data-ttu-id="7d17c-153">**Primary instance**</span><span class="sxs-lookup"><span data-stu-id="7d17c-153">**Primary instance**</span></span>  
 <span data-ttu-id="7d17c-154">Nombre de la instancia de servidor que hospeda la réplica de disponibilidad del grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-154">Name of the server instance that is hosting the primary replica of the availability group.</span></span>  
  
 <span data-ttu-id="7d17c-155">**Failover mode**</span><span class="sxs-lookup"><span data-stu-id="7d17c-155">**Failover mode**</span></span>  
 <span data-ttu-id="7d17c-156">Muestra el modo de conmutación por error para el que se configura la réplica.</span><span class="sxs-lookup"><span data-stu-id="7d17c-156">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="7d17c-157">Los valores de modo de conmutación por error posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-157">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="7d17c-158">**Automática**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-158">**Automatic**.</span></span> <span data-ttu-id="7d17c-159">Indica que una o varias réplicas están en modo de conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="7d17c-159">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="7d17c-160">**Manual**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-160">**Manual**.</span></span> <span data-ttu-id="7d17c-161">Indica que ninguna réplica está en modo de conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="7d17c-161">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="7d17c-162">**Estado de clúster**</span><span class="sxs-lookup"><span data-stu-id="7d17c-162">**Cluster state**</span></span>  
 <span data-ttu-id="7d17c-163">Nombre y estado del clúster donde la instancia del servidor conectado y el grupo e disponibilidad es un nodo de miembro.</span><span class="sxs-lookup"><span data-stu-id="7d17c-163">Name and state of the cluster where the instance of the connected server and the availability group is a member node.</span></span>  
  
##  <a name="availability-replica-details"></a><a name="AvReplicaDetails"></a> <span data-ttu-id="7d17c-164">Detalles de la réplica de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="7d17c-164">Availability Replica Details</span></span>  
 <span data-ttu-id="7d17c-165">El panel **Réplica de disponibilidad** muestra las columnas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d17c-165">The **Availability replica** pane displays the following columns:</span></span>  
  
 <span data-ttu-id="7d17c-166">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7d17c-166">**Name**</span></span>  
 <span data-ttu-id="7d17c-167">El nombre de la instancia de servidor que hospeda la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-167">The name of the server instance that hosts the availability replica.</span></span> <span data-ttu-id="7d17c-168">Esta columna se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-168">This column is shown by default.</span></span>  
  
 <span data-ttu-id="7d17c-169">**Rol**</span><span class="sxs-lookup"><span data-stu-id="7d17c-169">**Role**</span></span>  
 <span data-ttu-id="7d17c-170">Indica el rol actual de la réplica de disponibilidad, **Principal** o **Secundaria**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-170">Indicates the current role of the availability replica, either **Primary** or **Secondary**.</span></span> <span data-ttu-id="7d17c-171">Para más información sobre los roles de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)], vea [Información general de los grupos de disponibilidad AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7d17c-171">For information about [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] roles, see [Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md).</span></span> <span data-ttu-id="7d17c-172">Esta columna se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-172">This column is shown by default.</span></span>  
  
 <span data-ttu-id="7d17c-173">**Modo de conmutación por error**</span><span class="sxs-lookup"><span data-stu-id="7d17c-173">**Failover Mode**</span></span>  
 <span data-ttu-id="7d17c-174">Muestra el modo de conmutación por error para el que se configura la réplica.</span><span class="sxs-lookup"><span data-stu-id="7d17c-174">Displays the failover mode for which the replica is configured.</span></span> <span data-ttu-id="7d17c-175">Los valores de modo de conmutación por error posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-175">The possible failover mode values are:</span></span>  
  
-   <span data-ttu-id="7d17c-176">**Automática**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-176">**Automatic**.</span></span> <span data-ttu-id="7d17c-177">Indica que una o varias réplicas están en modo de conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="7d17c-177">Indicates that one or more replicas is in automatic-failover mode.</span></span>  
  
-   <span data-ttu-id="7d17c-178">**Manual**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-178">**Manual**.</span></span> <span data-ttu-id="7d17c-179">Indica que ninguna réplica está en modo de conmutación por error automática.</span><span class="sxs-lookup"><span data-stu-id="7d17c-179">Indicates that no replica is automatic-failover mode.</span></span>  
  
 <span data-ttu-id="7d17c-180">**Estado de sincronización**</span><span class="sxs-lookup"><span data-stu-id="7d17c-180">**Synchronization State**</span></span>  
 <span data-ttu-id="7d17c-181">Indica si una réplica secundaria está sincronizada actualmente con la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-181">Indicates whether a secondary replica is currently synchronized with primary replica.</span></span> <span data-ttu-id="7d17c-182">Esta columna se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-182">This column is shown by default.</span></span> <span data-ttu-id="7d17c-183">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-183">The possible values are:</span></span>  
  
-   <span data-ttu-id="7d17c-184">**No sincronizado**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-184">**Not Synchronized**.</span></span> <span data-ttu-id="7d17c-185">Una o más bases de datos de la réplica no están sincronizadas todavía no se han unido al grupo de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-185">One or more databases in the replica are not synchronized or have not yet been joined to the availability group.</span></span>  
  
-   <span data-ttu-id="7d17c-186">**Sincronizando**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-186">**Synchronizing**.</span></span> <span data-ttu-id="7d17c-187">Una o más bases de datos de la réplica se están sincronizando.</span><span class="sxs-lookup"><span data-stu-id="7d17c-187">One or more databases in the replica are being synchronized.</span></span>  
  
-   <span data-ttu-id="7d17c-188">**Sincronizado**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-188">**Synchronized**.</span></span> <span data-ttu-id="7d17c-189">Todas las bases de datos de la réplica secundaria están sincronizadas con las bases de datos principales correspondientes en la réplica principal actual, si hay alguna, o en la última réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-189">All databases in the secondary replica are synchronized with the corresponding primary databases on the current primary replica, if any, or on the last primary replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d17c-190">En modo de rendimiento, la base de datos nunca está en estado sincronizado.</span><span class="sxs-lookup"><span data-stu-id="7d17c-190">In performance mode, the database is never in the synchronized state.</span></span>  
  
-   <span data-ttu-id="7d17c-191">**Null**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-191">**NULL**.</span></span> <span data-ttu-id="7d17c-192">Estado desconocido.</span><span class="sxs-lookup"><span data-stu-id="7d17c-192">Unknown state.</span></span> <span data-ttu-id="7d17c-193">Este valor aparece cuando la instancia del servidor local no puede comunicarse con el clúster de conmutación por error de WSFC (es decir, el nodo local no forma parte del quórum de WSFC).</span><span class="sxs-lookup"><span data-stu-id="7d17c-193">This value occurs when the local server instance cannot communicate with the WSFC failover cluster (that is the local node is not part of WSFC quorum).</span></span>  
  
 <span data-ttu-id="7d17c-194">**Problemas**</span><span class="sxs-lookup"><span data-stu-id="7d17c-194">**Issues**</span></span>  
 <span data-ttu-id="7d17c-195">Muestra el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="7d17c-195">Lists the issue name.</span></span> <span data-ttu-id="7d17c-196">Este valor se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-196">This value is shown by default.</span></span> <span data-ttu-id="7d17c-197">Para obtener una lista de todos los problemas de directivas de AlwaysOn, vea [directivas de AlwaysOn para problemas operativos con grupos de disponibilidad AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="7d17c-197">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="7d17c-198">**Modo de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="7d17c-198">**Availability Mode**</span></span>  
 <span data-ttu-id="7d17c-199">Indica la propiedad de réplica que se establece por separado para cada réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-199">Indicates the replica property that you set separately for each availability replica.</span></span> <span data-ttu-id="7d17c-200">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-200">This value is hidden by default.</span></span> <span data-ttu-id="7d17c-201">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-201">The possible values are:</span></span>  
  
-   <span data-ttu-id="7d17c-202">**Asincrónica**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-202">**Asynchronous**.</span></span> <span data-ttu-id="7d17c-203">La réplica secundaria nunca se sincroniza con la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-203">The secondary replica never becomes synchronized with the primary replica.</span></span>  
  
-   <span data-ttu-id="7d17c-204">**Sincrónicos**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-204">**Synchronous**.</span></span> <span data-ttu-id="7d17c-205">En la puesta al día de la base de datos principal, una base de datos secundaria entra en este estado permanece al día mientras continúe la sincronización de datos para la base de datos.</span><span class="sxs-lookup"><span data-stu-id="7d17c-205">When catching up to the primary database, a secondary database enters this state, and it remains caught up as long as data synchronization continues for the database.</span></span>  
  
 <span data-ttu-id="7d17c-206">**Modo de conexión principal**</span><span class="sxs-lookup"><span data-stu-id="7d17c-206">**Primary Connection Mode**</span></span>  
 <span data-ttu-id="7d17c-207">Indica el modo que se usa para conectarse a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-207">Indicates the mode that is used to connect to the primary replica.</span></span>  <span data-ttu-id="7d17c-208">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-208">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-209">**Modo de conexión secundaria**</span><span class="sxs-lookup"><span data-stu-id="7d17c-209">**Secondary Connection Mode**</span></span>  
 <span data-ttu-id="7d17c-210">Indica el modo que se usa para conectarse a la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-210">Indicates the mode that is used to connect to the secondary replica.</span></span>  <span data-ttu-id="7d17c-211">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-211">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-212">**Estado de conexión**</span><span class="sxs-lookup"><span data-stu-id="7d17c-212">**Connection State**</span></span>  
 <span data-ttu-id="7d17c-213">Indica si la réplica secundaria está conectada actualmente a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-213">Indicates whether a secondary replica is currently connected to the primary replica.</span></span> <span data-ttu-id="7d17c-214">Esta columna está oculta de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-214">This column is hidden by default.</span></span> <span data-ttu-id="7d17c-215">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-215">The possible values are:</span></span>  
  
-   <span data-ttu-id="7d17c-216">**Desconectado**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-216">**Disconnected**.</span></span> <span data-ttu-id="7d17c-217">En el caso de una réplica de disponibilidad remota, indica que está desconectada de la réplica de disponibilidad local.</span><span class="sxs-lookup"><span data-stu-id="7d17c-217">For a remote availability replica, indicates that it is disconnected from the local availability replica.</span></span> <span data-ttu-id="7d17c-218">La respuesta de la réplica local al estado Desconectado depende de su rol, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="7d17c-218">The response of the local replica to the Disconnected state depends on its role, as follows:</span></span>  
  
    -   <span data-ttu-id="7d17c-219">En la réplica principal, si una réplica secundaria está desconectada, las bases de datos secundarias se marcan como **No sincronizadas** en la réplica principal y la réplica principal espera a que la réplica secundaria vuelva a conectarse.</span><span class="sxs-lookup"><span data-stu-id="7d17c-219">On the primary replica, if a secondary replica is disconnected, the secondary databases are marked as **Not Synchronized** on the primary replica, and the primary replica waits for the secondary to reconnect.</span></span>  
  
    -   <span data-ttu-id="7d17c-220">En la réplica secundaria, cuando detecta que está desconectada, intenta volver a conectarse a la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-220">On the secondary replica, upon detecting that it is disconnected, the secondary replica attempts to reconnect to the primary replica.</span></span>  
  
-   <span data-ttu-id="7d17c-221">**Conectado**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-221">**Connected**.</span></span> <span data-ttu-id="7d17c-222">Una réplica de disponibilidad remota que está conectada actualmente a la réplica local.</span><span class="sxs-lookup"><span data-stu-id="7d17c-222">A remote availability replica that is currently connected to the local replica.</span></span>  
  
 <span data-ttu-id="7d17c-223">**Estado operativo**</span><span class="sxs-lookup"><span data-stu-id="7d17c-223">**Operational State**</span></span>  
 <span data-ttu-id="7d17c-224">Indica el estado operativo actual de la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-224">Indicates the current operational state of the secondary replica.</span></span> <span data-ttu-id="7d17c-225">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-225">This value is hidden by default.</span></span> <span data-ttu-id="7d17c-226">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-226">The possible values are:</span></span>  
  
 <span data-ttu-id="7d17c-227">**0**. Conmutación por error pendiente</span><span class="sxs-lookup"><span data-stu-id="7d17c-227">**0**. Pending failover</span></span>  
  
 <span data-ttu-id="7d17c-228">**1**. Pendiente</span><span class="sxs-lookup"><span data-stu-id="7d17c-228">**1**. Pending</span></span>  
  
 <span data-ttu-id="7d17c-229">**2**. En línea</span><span class="sxs-lookup"><span data-stu-id="7d17c-229">**2**. Online</span></span>  
  
 <span data-ttu-id="7d17c-230">**3**. Sin conexión</span><span class="sxs-lookup"><span data-stu-id="7d17c-230">**3**. Offline</span></span>  
  
 <span data-ttu-id="7d17c-231">**4**. Error</span><span class="sxs-lookup"><span data-stu-id="7d17c-231">**4**. Failed</span></span>  
  
 <span data-ttu-id="7d17c-232">**5**. No se pudo establecer quórum</span><span class="sxs-lookup"><span data-stu-id="7d17c-232">**5**. Failed, no quorum</span></span>  
  
 <span data-ttu-id="7d17c-233">**Null**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-233">**NULL**.</span></span> <span data-ttu-id="7d17c-234">La réplica no es local</span><span class="sxs-lookup"><span data-stu-id="7d17c-234">Replica is not local</span></span>  
  
 <span data-ttu-id="7d17c-235">**Nº del último error de conexión**</span><span class="sxs-lookup"><span data-stu-id="7d17c-235">**Last Connection Error No.**</span></span>  
 <span data-ttu-id="7d17c-236">Número del último error de conexión.</span><span class="sxs-lookup"><span data-stu-id="7d17c-236">Number of the last connection error.</span></span>  <span data-ttu-id="7d17c-237">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-237">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-238">**Descripción del último error de conexión**</span><span class="sxs-lookup"><span data-stu-id="7d17c-238">**Last Connection Error Description**</span></span>  
 <span data-ttu-id="7d17c-239">Descripción del último error de conexión.</span><span class="sxs-lookup"><span data-stu-id="7d17c-239">Description of the last connection error.</span></span>  <span data-ttu-id="7d17c-240">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-240">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-241">**Marca de tiempo del último error de conexión**</span><span class="sxs-lookup"><span data-stu-id="7d17c-241">**Last Connection Error Timestamp**</span></span>  
 <span data-ttu-id="7d17c-242">Marca de tiempo del último error de conexión.</span><span class="sxs-lookup"><span data-stu-id="7d17c-242">Timestamp of the last connection error.</span></span> <span data-ttu-id="7d17c-243">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-243">This value is hidden by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d17c-244">Para obtener más información sobre los contadores de rendimiento para réplicas de disponibilidad, vea [SQL Server, réplica de disponibilidad](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span><span class="sxs-lookup"><span data-stu-id="7d17c-244">For information about performance counters for availability replicas, see [SQL Server, Availability Replica](../../../relational-databases/performance-monitor/sql-server-availability-replica.md).</span></span>  
  
##  <a name="to-group-availability-group-information"></a><a name="AvDbDetails"></a> <span data-ttu-id="7d17c-245">Para agrupar la información del grupo de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="7d17c-245">To Group Availability Group Information</span></span>  
 <span data-ttu-id="7d17c-246">Para agrupar la información, haga clic en **Agrupar por**y seleccione una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d17c-246">To group the information, click **Group by**, and select one of the following:</span></span>  
  
-   <span data-ttu-id="7d17c-247">**Réplicas de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="7d17c-247">**Availability replicas**</span></span>  
  
-   <span data-ttu-id="7d17c-248">**Bases de datos de disponibilidad**</span><span class="sxs-lookup"><span data-stu-id="7d17c-248">**Availability databases**</span></span>  
  
-   <span data-ttu-id="7d17c-249">**Estado de sincronización**</span><span class="sxs-lookup"><span data-stu-id="7d17c-249">**Synchronization state**</span></span>  
  
-   <span data-ttu-id="7d17c-250">**Preparación para la conmutación por error**</span><span class="sxs-lookup"><span data-stu-id="7d17c-250">**Failover readiness**</span></span>  
  
-   <span data-ttu-id="7d17c-251">**Problemas**</span><span class="sxs-lookup"><span data-stu-id="7d17c-251">**Issues**</span></span>  
  
 <span data-ttu-id="7d17c-252">El panel que muestra que muestra la información agrupada tiene las siguientes columnas:</span><span class="sxs-lookup"><span data-stu-id="7d17c-252">The pane that displays the grouped information displays the following columns:</span></span>  
  
 <span data-ttu-id="7d17c-253">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="7d17c-253">**Name**</span></span>  
 <span data-ttu-id="7d17c-254">El nombre de la base de datos de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-254">The name of the availability database.</span></span> <span data-ttu-id="7d17c-255">Este valor se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-255">This value is shown by default.</span></span>  
  
 <span data-ttu-id="7d17c-256">**Réplica**</span><span class="sxs-lookup"><span data-stu-id="7d17c-256">**Replica**</span></span>  
 <span data-ttu-id="7d17c-257">El nombre de la instancia de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que hospeda la réplica de disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="7d17c-257">The name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosts the availability replica.</span></span> <span data-ttu-id="7d17c-258">Este valor se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-258">This value is shown by default.</span></span>  
  
 <span data-ttu-id="7d17c-259">**Estado de sincronización**</span><span class="sxs-lookup"><span data-stu-id="7d17c-259">**Synchronization State**</span></span>  
 <span data-ttu-id="7d17c-260">Indica si la base de datos de disponibilidad está sincronizada actualmente con la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-260">Indicates whether the availability database is currently synchronized with primary replica.</span></span> <span data-ttu-id="7d17c-261">Este valor se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-261">This value is shown by default.</span></span> <span data-ttu-id="7d17c-262">Los posibles estados de sincronización son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d17c-262">The possible synchronization states are:</span></span>  
  
-   <span data-ttu-id="7d17c-263">**No se están sincronizando**</span><span class="sxs-lookup"><span data-stu-id="7d17c-263">**Not synchronizing**.</span></span>  
  
    -   <span data-ttu-id="7d17c-264">En el rol principal, indica que la base de datos no está lista para sincronizar su registro de transacciones con las bases de datos secundarias correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7d17c-264">For the primary role, indicates that the database is not ready to synchronize its transaction log with the corresponding secondary databases.</span></span>  
  
    -   <span data-ttu-id="7d17c-265">En una base de datos secundaria, indica que la base de datos no ha iniciado la sincronización del registro debido a un problema de conexión, se está suspendiendo o está pasando por estados de transición durante el inicio o en una conmutación de roles.</span><span class="sxs-lookup"><span data-stu-id="7d17c-265">For a secondary database, indicates that the database has not started log synchronization because of a connection issue, is being suspended, or is going through transition states during startup or a role switch.</span></span>  
  
-   <span data-ttu-id="7d17c-266">**Sincronizando**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-266">**Synchronizing**.</span></span>  
  
     <span data-ttu-id="7d17c-267">En una réplica principal:</span><span class="sxs-lookup"><span data-stu-id="7d17c-267">On a primary replica:</span></span>  
  
    -   <span data-ttu-id="7d17c-268">En una base de datos principal, indica que esta base de datos está lista para aceptar una solicitud de examen de una base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-268">For a primary database, indicates that this database is ready to accept a scan request from a secondary database.</span></span>  
  
    -   <span data-ttu-id="7d17c-269">En una réplica secundaria, indica que hay en curso un movimiento de datos activo para esa base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-269">On a secondary replica, indicates that there is active data movement going on for that secondary database.</span></span>  
  
     <span data-ttu-id="7d17c-270">En una réplica secundaria, indica que hay en curso un movimiento de datos activo para esa réplica.</span><span class="sxs-lookup"><span data-stu-id="7d17c-270">On a secondary replica, indicates that there is active data movement going on for that replica.</span></span>  
  
-   <span data-ttu-id="7d17c-271">**Sincronizado**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-271">**Synchronized**.</span></span>  
  
     <span data-ttu-id="7d17c-272">Para una base de datos principal, indica que al menos una base de datos secundaria está sincronizada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-272">For a primary database, indicates that at least one secondary database is synchronized.</span></span>  
  
     <span data-ttu-id="7d17c-273">Para una base de datos secundaria, indica que la base de datos está sincronizada con la base de datos principal correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7d17c-273">For a secondary database, indicates that the database is synchronized with the corresponding primary database.</span></span>  
  
-   <span data-ttu-id="7d17c-274">**Revirtiendo**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-274">**Reverting**.</span></span>  
  
     <span data-ttu-id="7d17c-275">Indica la fase en el proceso de reversión cuando una base de datos secundaria está obteniendo activamente páginas de la base de datos principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-275">Indicates the phase in the undo process when a secondary database is actively getting pages from the primary database.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="7d17c-276">Cuando una base de datos está en estado REVERTING, la acción de forzar una conmutación por error a la réplica secundaria puede dejar esa base de datos en un estado en el que no se pueda iniciar.</span><span class="sxs-lookup"><span data-stu-id="7d17c-276">When a database is in the REVERTING state, forcing failover to the secondary replica can leave that database in a state in which it cannot be started.</span></span>  
  
-   <span data-ttu-id="7d17c-277">**Inicializando**</span><span class="sxs-lookup"><span data-stu-id="7d17c-277">**Initializing**.</span></span>  
  
     <span data-ttu-id="7d17c-278">Indica la fase de reversión cuando el registro de transacciones necesario para la puesta al día de una base de datos secundaria respecto al LSN de reversión se envía y se protege en una réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-278">Indicates the phase of undo when the transaction log required for a secondary database to catch up to the undo LSN is being shipped and hardened on a secondary replica.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="7d17c-279">Cuando una base de datos está en estado INITIALIZING, la acción de forzar una conmutación por error a la réplica secundaria dejará siempre esa base de datos en un estado en el que no se podrá iniciar.</span><span class="sxs-lookup"><span data-stu-id="7d17c-279">When a database is in the INITIALIZING state, forcing failover to the secondary replica will always leave that database in a state in which it cannot be started.</span></span>  
  
 <span data-ttu-id="7d17c-280">**Preparación para la conmutación por error**</span><span class="sxs-lookup"><span data-stu-id="7d17c-280">**Failover Readiness**</span></span>  
 <span data-ttu-id="7d17c-281">Indica qué réplica de disponibilidad puede ser objeto de conmutación por error con o sin pérdida potencial de datos.</span><span class="sxs-lookup"><span data-stu-id="7d17c-281">Indicates which availability replica can be failed over with or without potential data loss.</span></span> <span data-ttu-id="7d17c-282">Esta columna se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-282">This column is shown by default.</span></span> <span data-ttu-id="7d17c-283">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-283">The possible values are:</span></span>  
  
-   <span data-ttu-id="7d17c-284">**Pérdida de datos**</span><span class="sxs-lookup"><span data-stu-id="7d17c-284">**Data Loss**</span></span>  
  
-   <span data-ttu-id="7d17c-285">**No se produce pérdida de datos**</span><span class="sxs-lookup"><span data-stu-id="7d17c-285">**No Data Loss**</span></span>  
  
 <span data-ttu-id="7d17c-286">**Issues**</span><span class="sxs-lookup"><span data-stu-id="7d17c-286">**Issues**</span></span>  
 <span data-ttu-id="7d17c-287">Muestra el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="7d17c-287">Lists the issue name.</span></span> <span data-ttu-id="7d17c-288">Esta columna se muestra de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-288">This column is shown by default.</span></span> <span data-ttu-id="7d17c-289">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7d17c-289">The possible values are:</span></span>  
  
-   <span data-ttu-id="7d17c-290">**Advertencias**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-290">**Warnings**.</span></span> <span data-ttu-id="7d17c-291">Haga clic para mostrar los umbrales y problemas de advertencias.</span><span class="sxs-lookup"><span data-stu-id="7d17c-291">Click to display the thresholds and warnings issues.</span></span>  
  
-   <span data-ttu-id="7d17c-292">**Crítico**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-292">**Critical**.</span></span> <span data-ttu-id="7d17c-293">Haga clic para mostrar los problemas críticos.</span><span class="sxs-lookup"><span data-stu-id="7d17c-293">Click to display the critical issues.</span></span>  
  
 <span data-ttu-id="7d17c-294">Para obtener una lista de todos los problemas de directivas de AlwaysOn, vea [directivas de AlwaysOn para problemas operativos con grupos de disponibilidad AlwaysOn (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="7d17c-294">For a list of all the AlwaysOn policy issues, see [AlwaysOn Policies for Operational Issues with AlwaysOn Availability Groups (SQL Server)](always-on-policies-for-operational-issues-always-on-availability.md).</span></span>  
  
 <span data-ttu-id="7d17c-295">**Suspendido**</span><span class="sxs-lookup"><span data-stu-id="7d17c-295">**Suspended**</span></span>  
 <span data-ttu-id="7d17c-296">Indica si la base de datos está **Suspendida** o se ha **Reanudado**.</span><span class="sxs-lookup"><span data-stu-id="7d17c-296">Indicates whether the database is **Suspended** or has been **Resumed**.</span></span> <span data-ttu-id="7d17c-297">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-297">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-298">**Motivo de suspensión**</span><span class="sxs-lookup"><span data-stu-id="7d17c-298">**Suspend Reason**</span></span>  
 <span data-ttu-id="7d17c-299">Indica la razón del estado suspendido.</span><span class="sxs-lookup"><span data-stu-id="7d17c-299">Indicates the reason for the suspended state.</span></span> <span data-ttu-id="7d17c-300">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-300">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-301">**Pérdida de datos calculada (segundos)**</span><span class="sxs-lookup"><span data-stu-id="7d17c-301">**Estimate Data Loss (seconds)**</span></span>  
 <span data-ttu-id="7d17c-302">Indica la diferencia de tiempo de la última entrada del registro de transacciones de la réplica principal y la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-302">Indicates the time difference of the last transaction log record in the primary replica and secondary replica.</span></span> <span data-ttu-id="7d17c-303">Si se produce un error en la réplica principal, se perderán todas las entradas del registro de transacciones de la ventana de tiempo.</span><span class="sxs-lookup"><span data-stu-id="7d17c-303">If the primary replica fails, all transaction log records within the time window will be lost.</span></span> <span data-ttu-id="7d17c-304">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-304">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-305">**Tiempo de recuperación calculado (segundos)**</span><span class="sxs-lookup"><span data-stu-id="7d17c-305">**Estimated Recovery Time (seconds)**</span></span>  
 <span data-ttu-id="7d17c-306">Indica el tiempo en segundos necesario para rehacer el tiempo de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="7d17c-306">Indicates the time in seconds it takes to redo the catch-up time.</span></span> <span data-ttu-id="7d17c-307">El *tiempo de puesta al día* es el tiempo que tardará la réplica secundaria en realizar la puesta la día con la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-307">The *catch-up time* is the time it will take for the secondary replica to catch up with the primary replica.</span></span> <span data-ttu-id="7d17c-308">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-308">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-309">**Rendimiento de sincronización (segundos)**</span><span class="sxs-lookup"><span data-stu-id="7d17c-309">**Synchronization Performance (seconds)**</span></span>  
 <span data-ttu-id="7d17c-310">Indica el tiempo en segundos necesario para la sincronización entre las réplicas principal y secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-310">Indicates the time in seconds it takes to synchronize between the primary and secondary replicas.</span></span> <span data-ttu-id="7d17c-311">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-311">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-312">**Rendimiento de sincronización (KB)**</span><span class="sxs-lookup"><span data-stu-id="7d17c-312">**Log Send Queue Size (KB)**</span></span>  
 <span data-ttu-id="7d17c-313">Indica la cantidad de entradas de registro en los archivos de registro de la base de datos principal que no se han enviado a la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-313">Indicates the amount of log records in the log files of the primary database that have not been sent to the secondary replica.</span></span> <span data-ttu-id="7d17c-314">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-314">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-315">**Tasa de envío del registro (KB/seg)**</span><span class="sxs-lookup"><span data-stu-id="7d17c-315">**Log Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="7d17c-316">Indica la velocidad en KB por segundo a la que las entradas de registro se envían a la réplica secundaria. Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-316">Indicates the rate in KB per second at which log records are being sent to the secondary replica This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-317">**Tamaño de la cola Rehacer (KB)**</span><span class="sxs-lookup"><span data-stu-id="7d17c-317">**Redo Queue Size (KB)**</span></span>  
 <span data-ttu-id="7d17c-318">Indica la cantidad de entradas de registro en los archivos de registro de la réplica secundaria que no se han rehecho todavía.</span><span class="sxs-lookup"><span data-stu-id="7d17c-318">Indicates the amount of log records in the log files of the secondary replica that have not yet been redone.</span></span> <span data-ttu-id="7d17c-319">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-319">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-320">**Tasa de puesta al día (KB/seg)**</span><span class="sxs-lookup"><span data-stu-id="7d17c-320">**Redo Rate (KB/sec)**</span></span>  
 <span data-ttu-id="7d17c-321">Indica la velocidad en KB por segundo a la que las entradas de registro se están rehaciendo.</span><span class="sxs-lookup"><span data-stu-id="7d17c-321">Indicates the rate in KB per second at which the log records are being redone.</span></span> <span data-ttu-id="7d17c-322">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-322">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-323">**Tasa de envío de secuencia de archivos (KB/seg)**</span><span class="sxs-lookup"><span data-stu-id="7d17c-323">**FileStream Send Rate (KB/sec)**</span></span>  
 <span data-ttu-id="7d17c-324">Indica la velocidad de la secuencia de archivos en KB por segundo a la se envían las transacciones a la réplica.</span><span class="sxs-lookup"><span data-stu-id="7d17c-324">Indicates the rate of the FileStream in KB per second at which transactions are being sent to the replica.</span></span> <span data-ttu-id="7d17c-325">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-325">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-326">**LSN de fin de registro**</span><span class="sxs-lookup"><span data-stu-id="7d17c-326">**End of Log LSN**</span></span>  
 <span data-ttu-id="7d17c-327">Indica el número de secuencia de registro (LSN) real que corresponde a la última entrada de registro en la memoria caché del registro en las réplicas principal y secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-327">Indicates the actual log sequence number (LSN) that corresponds to the last log record in the log cache on the primary and secondary replicas.</span></span> <span data-ttu-id="7d17c-328">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-328">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-329">**LSN de recuperación**</span><span class="sxs-lookup"><span data-stu-id="7d17c-329">**Recovery LSN**</span></span>  
 <span data-ttu-id="7d17c-330">Indica el final del registro de transacciones antes de que la réplica escriba nuevas entradas de registro después de la recuperación o la conmutación por error de la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-330">Indicates the end of the transaction log before the replica writes any new log records after recovery or failover on the primary replica.</span></span> <span data-ttu-id="7d17c-331">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-331">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-332">**LSN de truncamiento**</span><span class="sxs-lookup"><span data-stu-id="7d17c-332">**Truncation LSN**</span></span>  
 <span data-ttu-id="7d17c-333">Indica el valor mínimo de truncamiento del registro para la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-333">Indicates the minimum log truncation value for the primary replica.</span></span> <span data-ttu-id="7d17c-334">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-334">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-335">**LSN de última confirmación**</span><span class="sxs-lookup"><span data-stu-id="7d17c-335">**Last Commit LSN**</span></span>  
 <span data-ttu-id="7d17c-336">Indica el LSN real correspondiente al último registro de confirmación del registro de transacciones.</span><span class="sxs-lookup"><span data-stu-id="7d17c-336">Indicates the actual LSN corresponding to the last commit record in the transaction log.</span></span> <span data-ttu-id="7d17c-337">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-337">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-338">**Última hora de confirmación**</span><span class="sxs-lookup"><span data-stu-id="7d17c-338">**Last Commit Time**</span></span>  
 <span data-ttu-id="7d17c-339">Indica la hora correspondiente al último registro de confirmación.</span><span class="sxs-lookup"><span data-stu-id="7d17c-339">Indicates the time corresponding to the last commit record.</span></span> <span data-ttu-id="7d17c-340">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-340">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-341">**Último LSN enviado**</span><span class="sxs-lookup"><span data-stu-id="7d17c-341">**Last Sent LSN**</span></span>  
 <span data-ttu-id="7d17c-342">Indica el punto en el que todos los bloques de registro han sido enviados por la réplica principal.</span><span class="sxs-lookup"><span data-stu-id="7d17c-342">Indicates the point up to which all log blocks have been sent by the primary replica.</span></span> <span data-ttu-id="7d17c-343">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-343">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-344">**Última hora de envío**</span><span class="sxs-lookup"><span data-stu-id="7d17c-344">**Last Sent Time**</span></span>  
 <span data-ttu-id="7d17c-345">Indica la hora a la que se envió el último bloque de registro.</span><span class="sxs-lookup"><span data-stu-id="7d17c-345">Indicates the time when the last log block was sent.</span></span> <span data-ttu-id="7d17c-346">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-346">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-347">**Último LSN recibido**</span><span class="sxs-lookup"><span data-stu-id="7d17c-347">**Last Received LSN**</span></span>  
 <span data-ttu-id="7d17c-348">Indica el punto en el que todos los bloques de registro han sido recibidos por la réplica secundaria que hospeda la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-348">Indicates the point up to which all log blocks have been received by the secondary replica that hosts the secondary database.</span></span> <span data-ttu-id="7d17c-349">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-349">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-350">**Última hora de recepción**</span><span class="sxs-lookup"><span data-stu-id="7d17c-350">**Last Received Time**</span></span>  
 <span data-ttu-id="7d17c-351">Indica el momento en que el identificador del bloque de registro del último mensaje recibido se leyó en la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-351">Indicates the time when the log block identifier in last message received was read on the secondary replica.</span></span> <span data-ttu-id="7d17c-352">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-352">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-353">**Último LSN protegido**</span><span class="sxs-lookup"><span data-stu-id="7d17c-353">**Last Hardened LSN**</span></span>  
 <span data-ttu-id="7d17c-354">Indica el punto en el que todas las entradas de registro se han vaciado en el disco de la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-354">Indicates the point up to which all log records have been flushed to disk on the secondary replica.</span></span> <span data-ttu-id="7d17c-355">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-355">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-356">**Última hora de protección**</span><span class="sxs-lookup"><span data-stu-id="7d17c-356">**Last Hardened Time**</span></span>  
 <span data-ttu-id="7d17c-357">Indica la hora a la que el identificador de bloque de registro se recibió para el último LSN protegido en la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-357">Indicates the time when the log-block identifier was received for the last hardened LSN on the secondary replica.</span></span> <span data-ttu-id="7d17c-358">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-358">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-359">**Último LSN rehecho**</span><span class="sxs-lookup"><span data-stu-id="7d17c-359">**Last Redone LSN**</span></span>  
 <span data-ttu-id="7d17c-360">Indica el LSN real de la entrada de registro que se ha rehecho por última vez en la réplica secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-360">Indicates the actual LSN of the log record that was redone last on the secondary replica.</span></span> <span data-ttu-id="7d17c-361">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-361">This value is hidden by default.</span></span>  
  
 <span data-ttu-id="7d17c-362">**Última hora de rehacer**</span><span class="sxs-lookup"><span data-stu-id="7d17c-362">**Last Redone Time**</span></span>  
 <span data-ttu-id="7d17c-363">Indica la hora en que la última entrada de registro se rehízo en la base de datos secundaria.</span><span class="sxs-lookup"><span data-stu-id="7d17c-363">Indicates the time when the last log record was redone on the secondary database.</span></span> <span data-ttu-id="7d17c-364">Este valor está oculto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7d17c-364">This value is hidden by default.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7d17c-365">Tareas relacionadas</span><span class="sxs-lookup"><span data-stu-id="7d17c-365">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7d17c-366">Usar directivas de AlwaysOn para ver el estado de un grupo de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7d17c-366">Use AlwaysOn Policies to View the Health of an Availability Group &#40;SQL Server&#41;</span></span>](use-always-on-policies-to-view-the-health-of-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7d17c-367">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d17c-367">See Also</span></span>  
 <span data-ttu-id="7d17c-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7d17c-368">[sys.dm_os_performance_counters &#40;Transact-SQL&#41;](/sql/relational-databases/system-dynamic-management-views/sys-dm-os-performance-counters-transact-sql) </span></span>  
 [<span data-ttu-id="7d17c-369">Supervisión de los grupos de disponibilidad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7d17c-369">Monitoring of Availability Groups &#40;SQL Server&#41;</span></span>](monitoring-of-availability-groups-sql-server.md)  
  
  
